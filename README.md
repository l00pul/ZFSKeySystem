# SimpleZFSKeySystem

You can use this with keylocation in a ZFS volume to create and retrieve keys. 

## requirements

Download the sqlite version or RedBeanPHP: https://www.redbeanphp.com/ and
store it in the same folder in which you store the keys.php. 

## nginx

just forward all to keys.php for example like this:

>  location / {
>    try_files $uri $uri/ /keys.php?$args;
>  }
