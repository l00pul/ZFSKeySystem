# SimpleZFSKeySystem

You can use this with keylocation in a ZFS volume to create and retrieve keys.
Read more about this stuff here:

https://blog.jeanbruenn.info/2023/11/11/encryption-of-zfs-volumes-using-a-remote-external-key-system-written-in-php/

## requirements

Download the sqlite version or RedBeanPHP: https://www.redbeanphp.com/ and
store it in the same folder in which you store the keys.php. 

## nginx

just forward all to keys.php for example like this. Also block all access
to the folder the sqlite database containing the keys is in

>  location / {  
>    try_files $uri $uri/ /keys.php?$args;  
>  }  
>  location ~ /\. {  
>    deny all;  
>  }  
