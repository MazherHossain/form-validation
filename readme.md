## Form validation with file uplaod 
This is a tutorial for form validation with file uploading system. 


## Form Isset with validation

```php
/**
		 * Student Data Form
		 */
		 if( isset($_POST['insert']) ){
				
			// Form value get
			$name = $_POST['name'];
			$email = $_POST['email'];
			$cell = $_POST['cell'];
			$roll = $_POST['roll'];


			if( empty($name) ){
					$err['name'] = "<p style=\" color:red; \"> * Required </p>";
			}

			if( empty($email) ){
				$err['email'] = "<p style=\" color:red; \"> * Required </p>";
			}

			if( empty($cell) ){
				$err['cell'] = "<p style=\" color:red; \"> * Required </p>";
			}

			if( empty($roll) ){
				$err['roll'] = "<p style=\" color:red; \"> * Required </p>";
			}



			
			/**
			 * Form validation 
			 */
			if( empty($name) || empty($email) || empty($cell) || empty($roll)  ){
					
				$msg =  "<p class=\" alert alert-danger \"> All fields are required ! <button class=\"close\" data-dismiss=\"alert\">&times;</button> </p>";

			}else if( filter_var($email, FILTER_VALIDATE_EMAIL) == false ){

				$msg =  "<p class=\" alert alert-warning \"> Invalid email address ! <button class=\"close\" data-dismiss=\"alert\">&times;</button> </p>";
				
			}else {

				$msg =  "<p class=\" alert alert-success \">Data stable <button class=\"close\" data-dismiss=\"alert\">&times;</button></p>";

			}



		 }
```

## Error message Show 

```php

    if( isset($msg) ){
      echo $msg;
    }


    
    if( isset($err['name']) ){
      echo $err['name'];
    }

```
