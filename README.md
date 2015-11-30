# Proposal: dockerbuild
Docker Build - written in nodejs  is able to build dockerimages based on conditions supplyed via Dockerbuild file.


this is the answer to https://github.com/docker/docker/blob/master/ROADMAP.md#22-dockerfile-syntax

we create a single executeable for linux-x86 and x64 called dockerbuild
### Futures
- Build a Chain of Dockerimages Based on Each other 
- Remove Volumes and Place New
- Respect DOCKER_HOST env use a remote dockerhost for building and commiting the image
- Unset and Reset ENV Variables
- flatten down the image


Syntax: Dockerbuild

Accepts:
gitrepos filehandler tar.gz

options : replace-env, remove-env, remove-vol, replace-vol, remove-maintainer, replace-maintainer, Remove-expose, replace-expose, replace-matchline, image-tags, auto-push.



~~~
{
  "layername"
  
~~~

# Build Modificator ismaybe better we call it final build
it can Replace ENV and Volumes and Maintainer Instruction and flatten to single layer

takes dockerimage inspect output and exports all files via running container and file export to tar 
then Creates new Image with the Files and Applys changes viadocker build with the files and new instructions for maintainer and that
dockerbuild-change
builds or pulls a Image and From that adds canges that are in own Dockerfile
  
