#SoftLayer Object Store

Softlayer Object Storage is a redundant and highly scalable cloud storage service that allows users to easily store, search, and retrieve data across the Internet, with optional CDN connectivity, or across SoftLayer’s global private network. It is based on the OpenStack Swift platform. ITX Softlayer Object Store adapter allows user to read and write from Softlayer Object Store. Listen is not supported on the Adapter. 

##Minimum Requirements :

ITX v9.0.0.x

###Command Alias :

Adapter commands can be specified by using a command string on the command line or creating a command file that contains adapter commands. The execution command syntax is:

-IM[alias] card_num

-OM[alias] card_num where

-IM is the Input Source Override execution command

-OM is the Output Target Override execution command

alias is the adapter alias

and card_num is the number of the input or output card.

The following table shows the adapter alias and its execution command.

###Adapter : SoftLayer Object Store

Alias : SLOS

As Input : -IMSLOScard_num

As Output : -OMSLOScard_num

###SoftLayer Object Store Adapter commands

The following table lists valid commands for the Soft Layer Object Store  Adapter.

User Name (-U) : Object Store User Name - String (required)

Password  (-P) : Password - String (required)

URL       (-U) : Location URL - String (required)

Container Name (-C ) : Container Name - String (required)

Object Name (-O) : Object names - String (required)

Now (-N) : Commit the object immidiately -  (optional)

Properties File  (-P) : Location of the credential properites file - String (optional, if username and password are not provided , argument is required)

Softlayer Object Store Adapter Command Line Examples

###Inbound Adapter :

Adapter Command Line : = -U *** -P *** -URL location_url -T -C mywtx -O myobject

GET RULE : GET("SLOS", "-U *** -P ***  -URL location_url -T -C mywtx -O trace")

###Outbound Adapter :

Line : -U *** -P *** -URL location_url-T -C mywtx -O trace

PUT RULE : =VALID(PUT("SLOS", "-U *** -P *** -URL location_url-T -C mywtx -O trace -NOW", input), LASTERRORMSG())

example location_url can be like https://dal05.objectstorage.softlayer.net/auth/v1.0/ 



###SoftLayer Object Store Adapter Installation Instructions

a) create a folder com.ibm.itx.softlayer.objectstorage under WTX INSTALL/jars directory

b) Drop m4slayerobj.jar and slobjectapi.jar in to WTX INSTALL/jars/com.ibm.itx.softlayer.objectstorage

c) Edit adapters.xml and add the following line

M4Adapter name="Softlayer Object Storage" alias="SLOS" id="185" type="app" class="com/ibm/itx/softlayer/objectstorage"

d) Invoke cleanextenderstudio.bat to invoke Design Studio

Note : For any defects or usage concerns, please open an issue ticket and shall be addressed.
