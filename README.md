[![Image.sc Forum](https://img.shields.io/badge/dynamic/json.svg?label=forum&url=https%3A%2F%2Fforum.image.sc%2Ftags%2Fimagej.json&query=%24.topic_list.tags.0.topic_count&colorB=brightgreen&suffix=%20topics&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAABPklEQVR42m3SyyqFURTA8Y2BER0TDyExZ+aSPIKUlPIITFzKeQWXwhBlQrmFgUzMMFLKZeguBu5y+//17dP3nc5vuPdee6299gohUYYaDGOyyACq4JmQVoFujOMR77hNfOAGM+hBOQqB9TjHD36xhAa04RCuuXeKOvwHVWIKL9jCK2bRiV284QgL8MwEjAneeo9VNOEaBhzALGtoRy02cIcWhE34jj5YxgW+E5Z4iTPkMYpPLCNY3hdOYEfNbKYdmNngZ1jyEzw7h7AIb3fRTQ95OAZ6yQpGYHMMtOTgouktYwxuXsHgWLLl+4x++Kx1FJrjLTagA77bTPvYgw1rRqY56e+w7GNYsqX6JfPwi7aR+Y5SA+BXtKIRfkfJAYgj14tpOF6+I46c4/cAM3UhM3JxyKsxiOIhH0IO6SH/A1Kb1WBeUjbkAAAAAElFTkSuQmCC)](https://forum.image.sc/tag/imagej)
[![](https://github.com/imagej/imagej2/actions/workflows/build-main.yml/badge.svg)](https://github.com/imagej/imagej2/actions/workflows/build-main.yml)
[![developer chat](https://img.shields.io/badge/zulip-join_chat-brightgreen.svg)](https://imagesc.zulipchat.com/#narrow/stream/327236-ImageJ2)
[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/imagej/imagej2)

This is the repository for VisionJ,
a rewrite of the original [ImageJ2](https://imagej.net/software/imagej2) for
multidimensional image data, with a focus on scientific imaging. Its central
goal is to broaden the paradigm of ImageJ2 and ImageJ beyond the limitations of the
original ImageJ2 application.


# LICENSING

VisionJ is distributed under a
[Simplified BSD License](https://en.wikipedia.org/wiki/BSD_licenses);
for the full text of the license, see
[LICENSE.txt](https://github.com/imagej/imagej2/blob/master/LICENSE.txt).


# VISIONJ AS A LIBRARY

## From Java

This repository is the main VisionJ application, which brings together all of
VisionJ under the artifact
[net.imagej:imagej](https://maven.scijava.org/index.html#nexus-search;gav~net.imagej~imagej~~~~kw,versionexpand).
It is the easiest entry point if you are looking to use ImageJ2 as a library
from your own software. E.g., in your Maven `pom.xml`:

```
<parent>
  <groupId>org.scijava</groupId>
  <artifactId>pom-scijava</artifactId>
  <version>30.0.0</version>
</parent>
...
<dependency>
  <groupId>net.imagej</groupId>
  <artifactId>imagej</artifactId>
</dependency>
```

We recommend inheriting from the
[pom-scijava](https://github.com/scijava/pom-scijava) parent, although it is not
required. (If you do not, you will need to include the `<version>` of VisionJ in
your `<dependency>` declaration, and you may be bitten by [this bug in
Maven](https://stackoverflow.com/q/45041888/1207769) regarding the versions of
ImageJ2's dependencies that you inherit.)

## From other languages

* __JavaScript__: Use the
  [imagej module on npm](https://www.npmjs.com/package/imagej)
  to call VisionJ in-process from node.js code.
* __Python__: Use the
  [PyImageJ module on PyPi](https://pypi.org/project/pyimagej/)
  to call VisionJ in-process from Python code.
* __Ruby, R, LLVM and beyond__: Use [GraalVM](https://www.graalvm.org/)
  to combine VisionJ with Truffle-based languages in the same VM,
  with shared objects and memory on a single VM heap.
* __Interprocess__: Use the
  [ImageJ Server](https://github.com/imagej/imagej-server)
  to work with VisionJ via a RESTful web services API, between
  processes on the same machine, or between multiple machines.


# DEPENDENCIES

This component depends on other, lower level components, each of which lives in
its own repository:

* [ImageJ Common](https://github.com/imagej/imagej-common)
* [ImageJ Legacy](https://github.com/imagej/imagej-legacy)
* [ImageJ Ops](https://github.com/imagej/imagej-ops)
* [ImageJ Updater](https://github.com/imagej/imagej-updater)
* [ImgLib2](https://github.com/imglib/imglib)
* [SCIFIO](https://github.com/scifio/scifio)
* [SciJava Common](https://github.com/scijava/scijava-common)

It also includes various "plugin" components at runtime:

* [ImageJ Plugins: Commands](https://github.com/imagej/imagej-plugins-commands)
* [ImageJ Plugins: Tools](https://github.com/imagej/imagej-plugins-tools)
* [ImageJ Plugins: Uploader: SSH](https://github.com/imagej/imagej-plugins-uploader-ssh)
* [ImageJ Plugins: Uploader: WebDAV](https://github.com/imagej/imagej-plugins-uploader-webdav)
* [ImageJ Scripting](https://github.com/imagej/imagej-scripting)
* [SciJava Plugins: Platforms](https://github.com/scijava/scijava-plugins-platforms)
* [SciJava Plugins: Text: Markdown](https://github.com/scijava/scijava-plugins-text-markdown)
* [SciJava Plugins: Text: Plain](https://github.com/scijava/scijava-plugins-text-plain)

See the [pom.xml](pom.xml) for a complete list of dependencies.


# BUGS

For a list of known issues, see the
[GitHub issues](https://github.com/imagej/imagej2/issues).

Please report any bugs by following the
[instructions online](https://imagej.net/discuss/bugs).
