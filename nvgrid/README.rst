===========
nVidia Grid drivers
===========

This element builds dkms driver for the vgpu in the image

Set variable DIB_DRIVER_URL to the desired url to download actual driver for the
installation. To deine a toked use variable DIB_CLIENT_TOKEN and define a file
name which contains actual token. It has to be put into the drivers directory.
It might be a good idea to use it as separate element with all tokens for all 
locations. 