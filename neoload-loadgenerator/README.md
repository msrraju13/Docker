What is NeoLoad Load Generator?
--------------------------
[NeoLoad](http://www.neotys.com/neoload/overview) is a load testing solution developed by [Neotys](http://www.neotys.com). NeoLoad realistically simulates user activity and monitors infrastructure behavior so you can eliminate bottlenecks in all your web and mobile applications.

NeoLoad Controller uses one or many Load Generators to generate the load against the server under test.

A NeoLoad Load Generator can be used on NeoLoad Web by specifying parameters (NeoLoad Web API URL, token...).

How to use this image
--------------------------
Start a NeoLoad Load Generator instance
=================

    docker run -p 7100:7100 neotys/neoload-loadgenerator

Since NeoLoad 6.5, the NeoLoad Load Generator files are located in /home/neoload/neoload
Before NeoLoad 6.5, the NeoLoad Load Generator files are located in /neoload<VERSION>/ (eg: /neoload6.4/)

Start a NeoLoad Load Generator instance connecting to NeoLoad Web (since NeoLoad 6.6)
=================

    docker run -p 7100:7100 \
            -e NEOLOADWEB_URL={nlweb-onpremise-apiurl:port} \
            -e NEOLOADWEB_TOKEN={nlweb-token} \
            -e ZONE={zone-id} \
            -e LG_HOST={load-generator-host} \
            -e LG_PORT=7100 \
            neotys/neoload-loadgenerator


| Env | Comment | Example |
| ------------------------ |: ---------------------------------------------: | :----------------: |
| NEOLOADWEB_URL (Optional) | The NeoLoad Web API URL | http://neoloadweb.mycompany.com:1081 |
| NEOLOADWEB_TOKEN | The NeoLoad Web access token | myToken |
| NEOLOADWEB_PROXY | The proxy URL to access to NeoLoad Web | http://login:password@myproxy |
| ZONE (Optional) | The Zone ID of the Load Generator | myZoneId |
| LG_HOST | The host where the Load Generator can be reached (IP of the machine where the container is deployed) | lg.mycompany |
| LG_PORT | The port on the host where the LG can be reached | 7100 |
| LOADGENERATOR_XMX (Since 6.6 / Optional) | Max memory of the Load Generator | -Xmx2048m |

If no NeoLoad Web API URL is specified it will try to connect to NeoLoad Web SAAS.


Once the connection is established it will be available on NeoLoad Web.
The Load Generator Agent will be available in the Zone associated with its Zone ID in NeoLoad Web.

The NeoLoad Load Generator files are located in /home/neoload/neoload

License
---------
NeoLoad is licensed under the following [License Agreement](http://www.neotys.com/documents/legal/eula/neoload/eula_en.html). You must agree to this license agreement to download and use the image.

Note: This license does not permit further distribution.

Supported Docker versions
--------------------------------
This image is officially supported on Docker version 1.11.0.
Support for older versions (down to 1.6) is provided on a best-effort basis.
Please see [the Docker installation documentation](https://docs.docker.com/installation/) for details on how to upgrade your Docker Deamon.

User Feedback
------------------
For general issues relating to NeoLoad you can get help from [Neotys Support](https://www.neotys.com/community/?from=%2Faccountarea%2Fcasecreate.php) or [Neotys Community](http://answers.neotys.com/).