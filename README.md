#PHP SOAP with NU_SOAP and Laravel 5.*
1. WSDL 
2. nu_soap plugins
	2. configure to Laravel
		
#how 
## nu_soap plugins	
	- URL download : 
		https://sourceforge.net/projects/nusoap/
	- Configure : 
		1. extract file downloaded to lavarel controller directory.
		2. include class and file nusoap directory in controller class 
			- include 'Soap/nusoap.php';
			- use nusoap_client;
			
	- example : 
		$client = new nusoap_client('htttps://WS.tws?WSDL', true);
		$error  = $client->getError();
		 
		if ($error) {
			echo "<h2>Constructor error</h2><pre>" . $error . "</pre>";
		}
		 
		$result = $client->call("start", array("id" => 1, "pkk" =>1));
		 
		if ($client->fault) {
			echo "<h2>Fault</h2><pre>";
			print_r($result);
			echo "</pre>";
		} else {
			$error = $client->getError();
			if ($error) {
				echo "<h2>Error</h2><pre>" . $error . "</pre>";
			} else {
				echo "<h2>Main</h2>";
				echo $result;
			}
		}
		 
		// show soap request and response
		echo "<h2>Request</h2>";
		echo "<pre>" . htmlspecialchars($client->request, ENT_QUOTES) . "</pre>";
		echo "<h2>Response</h2>";
		echo "<pre>" . htmlspecialchars($client->response, ENT_QUOTES) . "</pre>";
		echo "=========== response ============ ";
		echo "<pre>";
			var_dump($result);
		echo "</pre>";
	
		
##Reference
	- https://github.com/deviservi/nusoap