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

# install CASA
wget https://casa.nrao.edu/download/distro/linux/release/el7/casa-release-5.4.1-31.el7.tar.gz
tar xf casa-release-5.4.1-31.el7.tar.gz
cd casa-release-5.4.1-31.el7/bin
PATH='pwd':$PATH

%environment
PATH='pwd':$PATH

%runscript
echo "Hello world!"
casa-config --version
