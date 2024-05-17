# mimeDecode
mimeDecode patched for PHP 8 (fixed)

mimeDecode.php is part of library provided by https://pear.php.net/manual/en/package.mail.mail-mimedecode.php and stopped working for me when i upgraded my PHP to version 8.
Several code amenedments between PHP5, PHP7 and PHP8 meant the code stopped working.  It was just easier that i fix/patch the file instead of rewriting my app.

Only mimeDecode.php has been patched. PEAR.php is provided only for completeness and mimeDecode-rm.php is the orginal file.

How to use it.

1)  copy the mimeDecode.php file in your PHP directory or replace the mimeDecode.php.

if you used to use 

$params['include_bodies'] = true;
$params['decode_bodies']  = true;
$params['decode_headers'] = true;
$params['input']          = $string;   //this is the minmecontents
$params['crlf']           = "\r\n";
$structure = Mail_mimeDecode::decode($params);

change it to 

$params['include_bodies'] = true;
$params['decode_bodies']  = true;
$params['decode_headers'] = true;
$params['input']          = $string;   //this is the minmecontents
$params['crlf']           = "\r\n";
$Decoder  = new Mail_mimeDecode($string);
$structure = $Decoder->decode($params);

PS: im not a PHP programmer, just in a past life ivve programmed a bunch of OOP code. 

:-) 




