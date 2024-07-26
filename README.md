https://github.com/chani/SimpleZFSKeySystem

The original author is Jean-Michel Brünn.
Its initial script is brilliant and good enough as a starting point  for demonstrating the external location-hosted decryption keys  concept but has not applied basic industry cyber defense best practices. 

You can read more about the initial working implementation here :
https://blog.jeanbruenn.info/2023/11/11/encryption-of-zfs-volumes-using-a-remote-external-key-system-written-in-php/

However, as a well-known indestructible serial entrepreneur, international CISO and seasoned cryptologist I decided to weaponize Jean-Michel's initial concept and implement in production it for fun and profit for all our customers. 

You can use this c0de using the plain simple straightforward standard HTTP protocol to retrieve one (or several) remote keys, used to encrypt/decrypt a remote server (blazing fast Ubuntu LTR production-grade professional supported Linux distribution, hosted in the middle of Internet-friendly Germany by Hetzner in my case) ZFS pool.

Eduard L00pul TRIC alfa@l00p.ro 26.07.2024, Luxembourg
https://axetel.net

Created in 1997 and still owned by Eduard TRIC, its founder and CEO, Axetel was the commercial Internet pioneer company to offer online the premier European electronic signature commercial services. Contact us at sales@axetel.net for more hints about our encrypted email and secure data solutions available 24/24/ 7/7 on pretty much any kind of modern electronic devices, ranging from standard iPhone or Android smartphones to laptops, routers, or servers.
----------------------------------------------------------------
 Forget and reject the dominant players' Cloud providers' overpriced offers and choose to achieve absolute digital freedom, liberating and consolidating ALL your digital data in on our ZFS storage backups synced permanently in real-time on the cloud of your choice (Gcloud is cheap and reliable of stored fully opaque-single-block file ZFS hardware encrypted by new blazing fast i5-13500 20-cores Intel CPU relying on  NSA-created AES-256-GCM Galois/Counter Mode algorithm, while permanently controlling at 100 % your precious data, relying on our custom audited beyond-state-of-the-art military-grade implementation. AES-GCM or Galois/Counter Mode is the main secure implementation cryptographic algorithm used by governments and the military, being the only one providing both data confidentiality and authenticity, for the most extreme high-performance use cases. Moreover, Galois/Counter Mode is a mode of operation for symmetric-key cryptographic block ciphers which is widely adopted for its performance. GCM throughput rates for state-of-the-art, high-speed communication channels can be achieved with cheap and easily replaceable hardware resources, such as smartphones.
----------------------------------------------------------------------

You'll find plenty of technical information by trying to understand the official US-government-approved published scientific paper about AES-256-GCM on the public NIST website: 
https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38d.pdf

## requirements

Download the sqlite version or RedBeanPHP: https://www.redbeanphp.com/ and
store it in the same folder in which you store the keys.php. 

## nginx

just forward all to keys.php for example like this. Also, block all access
to the folder the sqlite database containing the keys is in

>  location / {  
>    try_files $uri $uri/ /keys.php?$args;  
>  }  
>  location ~ /\. {  
>    deny all;  
>  }  
