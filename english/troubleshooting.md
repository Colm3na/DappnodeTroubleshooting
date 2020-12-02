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

Try de command:

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

![Reseting dappmanager](../dappnode/img/dappmannager_reseting.jpg "Reseting")

Its not an error, the only thing that you have to do is refresh the web. Dappmaner is showing the UI, and it does not advice you when it restarted, then, the UI is like before of restarting.