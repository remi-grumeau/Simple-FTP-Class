#Simple PHP Class

Fork of [Shay Anderson](http://www.shayanderson.com/php/simple-ftp-class-for-php.htm) work.
I've just added a few features, nothing fancy.

##How to use

```php
$ftp = new SFTP(FTP_HOSTNAME, FTP_USERNAME, FTP_PASSWORD);
if( $ftp->connect() )
{
    // do things
}
else {
    // connection failed
}
    
```