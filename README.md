- - -
UPDATED 4/5/2012: Now works with Twitter Bootstrap 2 and its new control-group css class. 

Should still work with earlier versions of Bootstrap, as long as the error_container_class option parameter is passed in (default value is for Bootstrap v2). Other option is just to clone the revision 10f0dd18f0e648fa2e8a69256e4a850654d97a7b from Jan 22, 2012.
- - - 

## About
This is an adaptation of the jQuery Live Form Validation found [here](http://www.geektantra.com/2009/09/jquery-live-form-validation/) for Twitter Bootstrap. The modified script will allow for live form validation using the Twitter Bootstrap HTML pattern for forms.

The scripts in this repository do not make use of Rails model validation helpers. If you wish to see a solution that utilizes Rails validations helpers to do live validation with Twitter Bootstrap, please checkout my [blog post](http://www.ddarrensmith.com/blog/2012/05/17/ruby-on-rails-client-side-validation-with-validation-helpers-and-twitter-bootstrap/).

The main script is jquery.validate.js. This has a validate method that you can call on any jQuery input object. The changes for Twitter Bootstrap are the names of couple of the parameters, and using a container div w/ class=control-group instead of the input field to highlight a validation error.

The jquery.validation.functions.js file has not been modified in anyway and simply provides helper methods for date and radio button validation.

## Instructions

1. Copy the jquery.validate.js and jquery.validation.js files to your javascripts folder.

2. Create your form using the formatted needed by Twitter Bootstrap. If you are using the twitter-bootstrap-rails gem, you can run "rails g bootstrap:themed [RESOURCE_NAME]" to create Twitter Bootstrap compatible scaffold views.

3. Now add script that will validate your form inputs. This script will need to get executed after the page loads.

Example in CoffeeScript:

    $(document).ready ->
      $("#car_make").validate
        expression: "if(VAL != '') return true; else return false;"
        message: "Make is required."

      $("#car_model").validate
        expression: "if(VAL != '') return true; else return false;"
        message: "Model is required."

      $("#car_year").validate
        expression: "if(VAL != '') return true; else return false;"
        message: "Year is required."

      $("#car_year").validate
        expression: "if(VAL.match(/^\\d\\d\\d\\d$/)) return true; else return false;"
        message: "Invalid format."

For above the validate call you may also pass in additional parameters to override the defaults: error_message_class, error_container_class, live (true/false). The first two parameters are CSS classes for errors and the live parameter is if you want validation when an input goes out of focus (true) or only when the submit button is clicked (false). The default for the live parameter is true.

## Example Project
That's it! To view an example project head click [here](https://github.com/ddarren/jQuery-Live-Form-Validation-For-Twitter-Bootstrap-Example). 


- - -

Original Script License: http://www.apache.org/licenses/LICENSE-2.0

Original Script Copyright:
@author GeekTantra
@date 20 September 2009

 



