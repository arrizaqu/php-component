#Installing Oracle Driver and Laravel
	1. Installing to Laravel
	2. Oracle Configuration
#how 
##Installing to Laravel
	- version 5.3: composer require yajra/laravel-oci8:"5.3.*"  
	- version 5.2: composer require yajra/laravel-oci8:"5.2.*"
	- version 5.1: composer require yajra/laravel-oci8:"5.1.*"
##Oracle Configuration 
	1. Service Provider : 
		- Yajra\Oci8\Oci8ServiceProvider::class,
	2. Optional Conf 
		- php artisan vendor:publish --tag=oracle
	3. PHP config file configuration : 
		example : 
			'oracle' => [
				'driver'        => 'oracle',
				'tns'           => env('DB_TNS', ''),
				'host'          => env('DB_HOST', ''),
				'port'          => env('DB_PORT', '1521'),
				'database'      => env('DB_DATABASE', ''),
				'username'      => env('DB_USERNAME', ''),
				'password'      => env('DB_PASSWORD', ''),
				'charset'       => env('DB_CHARSET', 'AL32UTF8'),
				'prefix'        => env('DB_PREFIX', ''),
				'prefix_schema' => env('DB_SCHEMA_PREFIX', ''),
			],
			
##Reference
	- https://github.com/yajra/laravel-oci8