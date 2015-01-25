## About this image
This installer is meant to create a simple, transparent copy of Ubuntu 12.04 for Vagrant.

I worried that community Vagrant images could have been altered or rooted. You really don't have a good way of knowing. Just have a look over at www.vagrantbox.es. Hundreds of vagrant images to choose from. Who knows what the heck is on them.

With these configurations you can build your own image from official sources.

## Goals
1. As close to an original installation of Ubuntu as possible.
  - No additional software installed.
  - Minimal changes.
2. Reproducible and safe
  - Build the image yourself with these scripts and be sure of its safety
3. Extensible
  - You can use Packer to expand on the image and create something more interesting

### Requimentes
You'll need Packer and virtualbox to build these images.

## Building the image
The whole process is automated. To build a vagrant image, simply run:
```
# To create a box called "precise64"
./create_box

# To use a custom box name
./create_box my_box
```

Once the installer starts running, it will fire up virtualbox and take care of everything for you.

![Packer installing Ubuntu via Virtualbox](http://i.imgur.com/wpanrAt.png)

The installer will download the image, bootstrap it, then export a virtualbox image. This last box file is what you can share with others or use yourself. It will even install a specific version of virtualbox guest additions.

The preseed.cfg and scripts will do everything in an automated and predictable way.
 Feel free to fork and make whatever changes you want.
