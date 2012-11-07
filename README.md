#Appcelerator ACS PHP SDK  
This is a port of the Javascript SDK to PHP  
  

##Usage
Simply instantiate the library and call the API
  
	// Get a user's statuses
	$app_key  = '123';
	$email    = 'ben.edmunds@gmail.com';
	$password = '12345678';

	$appcelerator = new Appcelerator($app_key, $email, $password);

	$data = array(
		'where' => json_encode(array('user_id' => '4f9eb57a0020440def0056d3')),	
	);

	$output = $appcelerator->send_request('statuses/query.json', 'GET', $data);

	print_r($output);
	exit;


	//create a new status
	$app_key  = '123';
	$email    = 'ben.edmunds@gmail.com';
	$password = '12345678';
	
	$appcelerator = new Appcelerator($app_key, $email, $password);

	$data = array(
		'message' => 'api test message',	
	);

	$output = $appcelerator->send_request('statuses/create.json', 'POST', $data);
		
	print_r($output);
	exit;


	//custom data object
	$app_key  = '123';
	$email    = 'ben.edmunds@gmail.com';
	$password = '12345678';

	$appcelerator = new Appcelerator($app_key, $email, $password);
    	$data = 'fields='.json_encode(array(
	        'make'  => 'toyota', 
        	'model' => 'tacoma', 
        	'year'  => 2007, 
        	'color' => 'blue'
    	));
 
    	$output = $appcelerator->send_request('objects/cars/create.json', 'POST', $data);
 
    	print_r($output);
    	exit;



See [the Appcelerator documentation](http://cloud.appcelerator.com/docs/api/v1/statuses/info) for API details.

Class created by [Ben Edmunds](http://benedmunds.com) and [Shealan Foreshaw](http://twitter.com/#!/shealan) for [Swipe & Tap](http://twitter.com/#!/swipeandtap).