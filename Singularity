BootStrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/$basearch/
Include: yum wget

%post
  yum -y update
  yum -y install yum-utils
  yum -y groupinstall development
  yum -y install https://centos7.iuscommunity.org/ius-release.rpm
  yum -y install nano
  yum -y install build-essential curl git man vim autoconf libtool debootstrap squashfs-tools
  yum -y install qt-x11
  yum -y install libXft

# install CASA
  wget https://casa.nrao.edu/download/distro/linux/release/el7/casa-release-5.4.1-31.el7.tar.gz
  tar xf casa-release-5.4.1-31.el7.tar.gz
  cd casa-release-5.4.1-31.el7/bin
  PATH=/casa-release-5.4.1-31.el7/bin:$PATH

%environment
  PATH=/casa-release-5.4.1-31.el7/bin:$PATH

%runscript
  echo "Hello world!"
  casa-config --version
# to run a casa script provided as an argument:
# singularity run <container> <script> <args>
  exec casa -c "$@"
