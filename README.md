# jbrowse_docker
A repo for JBrowse-dedicated dockerfiles.

These Docker files were created to provide a starting build environment
that will result in an nginx server running either JBrowse 1 or 
JBrowse 2. These containers do not however provide a working instance
in either case. Rather, they provide nginx, a suitable version of 
NodeJS and several useful build tools, like Debian's `build-essential`
package (gcc, make, etc), wget, curl and git. In the case of 
`Dockerfile.jb2_env` it also provides the jbrowse command line
tool.

Both of these containers were developed for other projects and provide 
usage examples.

# JBrowse 1

The JBrowse 1 container was developed for use at WormBase
(https://wormbase.org) and the Alliance of Genome Resources
(https://alliancegenome.org/) where they are still in use. An example 
of how this container is used is in the fairly simple JBrowse instance
used by AGR, which can be found in this GitHub repo:
https://github.com/alliance-genome/agr_jbrowse_container.  Starting
from `gmod/jbrowse-buildenv`, the Docker file pulls in the dev
branch of JBrowse, the config files from another AGR repo, several
plugins and then builds JBrowse and moves a bunch of files around.
JBrowse is built in this container since including plugins in JBrowse 1
requires a fresh build.  Because this container makes use of 
* Staged builds
* Data files stored elsewhere (AWS S3)
the resulting Docker image is generally quite small (~200kb or less).

# JBrowse 2

This is still under active development and not in a stable git branch
that I can point at; this will be updated soon.

