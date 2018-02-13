# ImageMagick-MAESC
A repo for building an ImageMagick microservice Docker image.

## Build

Build the image with `build.sh`. Pass in your hostname as an argument (i.e. HOSTNAME/imagemagick)

## Running

You can run the image with the following command (replace HOST_PORT,HOST_DIR,HOST_NAME):

`docker run -itd -p HOST_PORT:80 -v HOST_DIR:/var/www/tmp HOST_NAME/imagemagick`

## Usage

/upload/(.+) - send original files here

/service - this will run your imagemagick conversion commands and respond with the converted file
```
{
  "cmd": array, the imagemagick commands. Should include "INPUT" and "OUTPUT" as separate elements.
  "input": string, the file name to convert. It will be inserted into the "INPUT" location of your commands.
}
```
