===========
nVidia Grid drivers
===========

This element builds dkms driver for the vgpu in the image

A DIB_NVGRID_DRIVER_URL or DIB_NVGRID_DRIVER_FILE must be set. URL has higher
priority than a local file. So if both are defined, then URL will be used.

DIB_NVGRID_DRIVER_URL - defines url to download a driver from. Last part of the
url will be used as a filename idenifier.

DIB_NVGRID_DRIVER_FILE - defines path on the local filesystem to the driver file
which will be copied to the image.

In order to put a license token, use variable DIB_NVGRID_CLIENT_TOKEN or
DIB_NVGRID_CLIENT_TOKEN_URL. Set it to the file path on the local filesystem or
to remote URL and it will be copied to /etc/nvidia/ClientConfigToken/ inside
the image.

DIB_NVGRID_CLIENT_TOKEN_MODE - defines mode that will be set for client token
file inside the image. Some versions of GRID require it to be readable for
all users.

To override hosts records we have two options. The first one is to set
DIB_NVGRID_HOSTS_FILE which defines path to the text file. It's content will be
added to /etc/hosts on the image as is. The second one is a env VAR DIB_HOSTS_ADD
It's syntax is "ip/hostname:ip/hostname" it will be parsed and added to the
/etc/hosts file

There is a way to verify downloaded images. Define DIB_NVGRID_SHA variable and
set it to the path with sha256sum file for downloaded from URL files. It can be
either a driver or token or both of them. Verification will be passed only for
files downloaded from URL.
