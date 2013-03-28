sun-jdk6-rpm
============

This is an updated JPackage version of the non-free Sun (now Oracle) JDK.

JPackage no longer provides updates to the non-free section but I still
need an updated version of this package so here it is sans source.

Note that I've removed the nosrc directives but am not distributing the
source so you will still need to download those, and your SRPM will be
very large. To build the packages you will need to download the JDK and
the demos. Also I've only tested this on x86_64, so I'm sure i?86 is
broken.

I have tested this build on a CentOS5.x86_64 system with mock from EPEL:

<download the sources from Oracle>
mock -r epel-5-x86_64 --init
<copy stuff into mock chroot, set perms appropriately>
mock -r epel-5-x86_64 --shell
  cd /builddir/build/SPECS
  rpmbuild -bs --nodeps java-1.6.0-sun.spec
<copy out srpm>
mock -r epel-5-x86_64 <srpm>

