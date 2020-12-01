# Solución de errores

The idea of this repo is to recopilate of the common errors that can appear and how solve them. All this information is obtained from discord's dappnode and forum.

## Prysm 


### Error 1

~~~
Http failure response for
http://prysm.dappnode/api/v2/validator/acccount?pageSize=5:500 
Internal Server Error
~~~

The error's window would be like:
![Error 1](../img/error_prysm_1.png "Prysm Error 1")

Para solucionar este error tan solo hay que eliminar los datos del validador, solamente el "validator data" e importar las keys una vez más. En la siguiente imagen se muestra claramente qué es lo que hay que eliminar.

![Delete only de validator data](../img/error_prysm_1_2.png "Prysm Error 1")

Después de eliminar los datos del validador, importa de nuevo solamente el archivo json "keystore-(...).json", no toda la carpeta.


## IPFS