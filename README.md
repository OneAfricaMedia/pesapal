Pesapal package for Laravel
=======
<h2>Introduction</h2>
This is a Laravel 5 pesapal package.
I provided this package as to help since pesapal do not have a package for Laravel.
Pesapal do not have a way to test this so I guess you will have to send money
payments to test
<h2>Installation</h2>
add <pre>"ericmuigai/pesapal": "2.*@dev"</pre> to your composer.json and then <pre>composer update</pre>
this will install the package
Once the package is installed add <pre>'Ericmuigai\Pesapal\PesapalServiceProvider',</pre> to the providers.
after this publish the config file by <pre>php artisan config:publish ericmuigai/pesapal</pre>
then migrate the package table by using <pre>php artisan migrate --package=ericmuigai/pesapal</pre>
Go to your pesapal account and in the ipn url enter <pre>yoursite.com/listenipn</pre> or or the url to your public path/listenipn<br/>
You should now find the config.php in the <pre>app/packages/ericmuigai/pesapal </pre>

<h2>How to use</h2>
Now you should be able to call the <pre>Pesapal::Iframe($array)</pre>
from any view you would like the iframe to appear.
The array should have this info in the <pre>$array</pre>
  <pre>/**
     * generates the iframe from the given details
     * @param array $values this array should contain the fields required by pesapal
     * description - description of the item or service
     * currency - if set will override the config settings you have of currency
     * user -which should be your client user id if you have a system of users
     * first_name- the first name of the user that is paying
     * last_name - the last name of the user that is paying
     * email - this should be a valid email or pesapal will throw an error
     * phone_number -which is optional if you have the email
     * amount - the total amount to be posted to pesapal
     * reference Please <em>Make sure this is a unique key to the transaction</em>. <em>An example is the id of the item or something</em>
     * type - default is MERCHANT
     * frame_height- this is the height of the iframe please provide integers as in 900 without the px
     *
     */'
     </pre>
