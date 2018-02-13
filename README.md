# ImageMagick-MAESC
A repo for building an ImageMagick microservice Docker image.

## Build

Build the image with `build.sh`. Pass in your hostname as an argument (i.e. <hostname>/ffmpeg)

## Running

You can run the image with the following command (replace HOST_PORT & HOST_DIR):

`docker run -itd -p HOST_PORT:80 -v HOST_DIR:/var/www/tmp sregistry.academic.systems/ffmpeg`

## Usage

/upload/(.+) - send original files here

/service - this will run your ffmpeg conversion commands and respond with the converted file
```
{
  "cmd": array, the ffmpeg commands. Should include "INPUT" and "OUTPUT" as separate elements.
  "input": string, the file name to convert.
}
```
