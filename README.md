# PKGBUILD-for-Linux-xianomai

it is PKGBUILD for build Arch packages: kernel Linux-evl (xianomai4) from prefetched  repository (git with option --depth=1 )

from branch 5.13-evl-rebase currently

cd "where PKGBUILD unpacked is"
  
mkdir src
  
cd src
  
git clone --depth=1 https://source.denx.de/Xenomai/xenomai4/linux-evl.git --branch v5.13-evl-rebase

or

git clone -b dovetail/master --depth=1  git://git.evlproject.org/linux-evl.git

./scripts/prepare-kernel.sh --linux=linux-evl --arch=x86_64 --dovetail=0001-null-patch.patch

  
after cloned
  
cd ..
  
makepkg -si --skipinteg --skipchecksums --skippgpcheck PKGBUILD
