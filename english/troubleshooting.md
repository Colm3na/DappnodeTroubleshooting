# Troubleshooting

The idea of this repo is to recopilate of the common errors that can appear and how solve them. All this information is obtained from discord's dappnode and forum.

https://medium.com/dappnode/step-by-step-staking-for-dappnode-users-92fdf7db0d0d

## Prysm 


### Error 1

~~~
Http failure response for
http://prysm.dappnode/api/v2/validator/acccount?pageSize=5:500 
Internal Server Error
~~~

The error's window would be like:
![Error 1](../img/error_prysm_1.png "Prysm Error 1")

The way to solve this error is deleting the data from the validator, only the validator data and importing the keys again. In the next image we show what you have to delete, you have to be very careful with this.

![Delete only de validator data](../img/error_prysm_1_2.png "Prysm Error 1")

After deleting the data, import again only the keystore-(...).json, NOT the entire folder.

#### Error 1.1

After doing the steps of Error 1, its possible that appears this problem along the installation:

![Error in the installation of dappmanager](../img/error_prysm_1_2.png "Prysm Error 1.1")

~~~
Ports have to be opened and there is no UPnP device available
    If you are capable of opening ports manually, please ignore this error
    Your router may have UPnP but it is not turned on yet. Please research if your specific router has UPnP and turn it on

Core DAppNode Packages dappmanager.dnp.dappnode.eth, vpndnp.dappnode.eth, ipfs.dnp.dappnode.eth, bind.dnp.dappnode.eth, wifi.dnp.dappnode.eth are not found
    Make sure the disk is not too full. If so DAppNode automatically stops the IPFS package to prevent it from becoming un-usable
    Go to the System tab and restart each stopped DAppNode Package. Please inspect the logs to understand cause and report it if it was not expected.
~~~

It would correct to ensure that the open configuration is correct in your router, after that, check the state of the disk and go to the system tab and restart every package that DAppNode has stopped.

### Error 2

After installing Prysm, this error appears: 

~~~
"Call to packageInstall
Reply: Error verifying the image: image tarball must contain strictly one image"
~~~

You need to update your DAppNode! Could you go to system > auto updates and force an update.
You'll force it by untoggling the auto updates from the system packages and a banner will appear prompting you to update now
But then remember to toggle it again!


## IPFS

There is an error with some kind of routers that does not support well the protocol, they are working on it!


## Connecting using SSH

### Connecting using ssh being in a different network(LAN)

Try the command:

~~~
ssh dappnode@172.33.0.1
~~~

## Updates


### Auto-updates

DAppNode recommends to activate the auto-updates. You can activate them, toggling the bottón in the top right, in the tab system.


### Manually updates

In the case that you prefer to update manually, you have type in the search bar of the DAppStore, in the case of updating the last version of dappnode, we would type:

~~~
core.dnp.dappnode.eth
~~~

## Dappmanager

### Dappmanager permanently reseting

It's possible that you see something like this:

![Reseting dappmanager](../img/dappmannager_reseting.jpg "Reseting")

Its not an error, the only thing that you have to do is refresh the web. Dappmaner is showing the UI, and it does not advice you when it restarted, then, the UI is like before of restarting.


## VPN

### ¿How to generate a new VPN file?

In the case you want to reset the vpn conection, follow the next steps. Firstly, from the DAppNode's admin pannel, go to the tab "Devices", and you will see the next image:

![Devices Window](../img/creating_vpn_1.png " ")

In this section, we have several options:

* **Credentials**: we can obtain the file of the current vpn conection, by a link or a QR code.
* **Admin**: Give admin permits of the dappnode to the device.
* **Reset**: Create a new vpn file. (.ovpn)
* **Remove**: Delete the device configuration.

In this case, we want create a new file, and access with a vpn which uses different credentials. Then, click on **Reset**.
![Warning Message](../img/creating_vpn_2.png " ")

When we were sure, click on the button Reset. The next step is to select the opción **Credentials** (get link).

In the next window, we have 2 options:

* **Show QR Code**: Doing this will show the QR code. Using the QR scan of our mobile we will obtain the link where we can download the configuration file of the new vpn.
* Copy the link which appears, or use the righ icon which it will open a window with the link.

Remember, stop using the current vpn to access to the link, if you dont stop using the vpn, it's probablyl that appears a error message in that link. After accesing to the link, the next windows appears:


![Download windows](../img/creating_vpn_3.png " ")

Click on the button **Download** and download the file. Set our new vpn connection with this new file and we go the direction [DAppNpde Admin Panel](http://my.dappnode/#/dashboard)

