How to implement it in CI- Restserver into your Codeigniter 3.2.xx ?


Steps are followed:

1. Download this folder in your desktop.
2. Extract it in to your desktop.
3. Open your project/application folder in CI platform.
4. copy and paste this files (REST_Controller.php (mostly you get it in src/RestController.php in downloaded files) and paste it into "application/libraries" in your project.
5. do the same for Format.php (mostly you get it in src/Format.php in downloaded files) and paste it into "application/libraries" in your project.
6. Now copy and paste this files rest.php (mostly you get it in src/rest.php in downloaded files) and paste it into "application/config" in your project.
7. Now copy and paste language folder and paste it into "application/language" in your project.
8. Now all done.
9. ohhh...! I forgot :( Please do not forgot to rename Restcontroller.php to REST_Controller.php
10. Now create a controller and named anything you want. i.e. follows :)

<?php
defined('BASEPATH') OR exit('No direct script access allowed');
// bring rest server connection //
require(APPPATH.'/libraries/REST_Controller.php');
require(APPPATH . '/libraries/Format.php');
use Restserver\Libraries\REST_Controller;

class Api extends REST_Controller{
	
	function __construct($config = 'rest') {
		parent::__construct($config);
		} 
		
		function index_post() {
    //get post data from url submitions
			$username = $this->post('username');
			$password = $this->post('password');
	  //display results back into json format
		    $this->response($result);
		}
		
		function index_put() {
	 //get post data from url submitions
			$username = $this->put('username');
			$password = $this->put('password');
	  //display results back into json format
		    $this->response($result);
		}
	
/////////////////////////////////////////////////////////////////
//                                                             //
//      ////////                 //////////                    //
//      //                       //     //                     //
//      //                       //     //                     //
//      ////////                 ////////                      //
//           //                  //  //                        //
//   	    //                   //    //                      //
//    ///////                    //      //                    //
//                                                             //
/////////////////////////////////////////////////////////////////

}
