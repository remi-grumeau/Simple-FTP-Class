#Simple FTP Class

Simple FTP is a simple yet useful class to make FTP and sFTP interactions easy.
It's a fork of [Shay Anderson](http://www.shayanderson.com/php/simple-ftp-class-for-php.htm)'s work. 
I've just added a few features and did this documentation. Nothing fancy.

##How to use

####Connect to a server
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

Note that you can specify a different port and timeout. Defaults are `21` and `90`.
```php
$ftp = new SFTP(FTP_HOSTNAME, FTP_USERNAME, FTP_PASSWORD, PORT, TIMEOUT);
```

##Methods

**$ftp->cd( *directory* )**
Changes the current directory to the specified one (aka 'navigate' to it)

**$ftp->chmod( *permission*, *remote file* )**
Change permission of the remote file or directory

**$ftp->close()**
Close the FTP connection

**$ftp->connect()**
Open an FTP connection with the remote server.
You can activate SSL by setting `$ftp->_ssl` to `true`.

**$ftp->delete( *remote file* )**
Delete a remote file.

**$ftp->get( *remote file* , *local file* , *mode* )**
Downloads a file from the FTP server and saves it into a local file.
Default mode is `FTP_ASCII`.

**$ftp->ls( *remote directory* )**
Returns a list of files in the given remote directory.

**$ftp->mkdir( *remote directory* , *chmod* )**
Creates a remote directory. 
If chmod is not set, default server configuration is used.

**$ftp->put( *local file* , *remote file* , *mode* )**
Uploads a local file to the FTP server.
Default mode is `FTP_BINARY`.

**$ftp->pwd()**
Returns the current directory.

**$ftp->rename( *old name* , *new name* )**
Rename a file on the server.

**$ftp->rmdir( *old name* , *new name* )**
Remove a directory on the server.

**$ftp->isdir( *remote directory* )**
Returns `true` or `false` is the remote directory exists. 

**$ftp->deltree( *remote directory* )**
Remove all files inside the given remote directory before it deletes the directory itself.

**$ftp->fileexists( *remote file* )**
Returns `true` or `false` is the remote file exists.

##Contribution:  PR accepted!
Any contribution is always welcome, so feel free to fork and send a pull request !

##Thanks
Of course, thanks [Shay Anderson](http://www.shayanderson.com/php/simple-ftp-class-for-php.htm) for this little yet useful class.

##License
As the initial code, this code is release under the [GPL License](https://gnu.org/licenses/gpl.html), without any warranty.