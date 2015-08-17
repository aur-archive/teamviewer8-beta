pkgname=teamviewer8-beta
_pkgname=teamviewer
pkgver=8.0.16675
pkgrel=1
pkgdesc="All-in-one solution for accessing PC's using the internet"
arch=('i686' 'x86_64')
url="http://www.teamviewer.com"
license="nonfree"
makedepends=('binutils')


if [ $CARCH == 'i686' ]; then
  source=("teamviewer_linux-${pkgver}.deb::http://www.teamviewer.com/download/version_8x/teamviewer_linux.deb" "teamviewer.desktop") 
  md5sums=('8615365b444eb3927cefbbf3dbed6ffa' 'ccff88e83d219c623872c9be23a50e7d')
  depends=('libsm' 'libxext' 'freetype2' 'libxtst')
elif [ $CARCH == 'x86_64' ]; then
  source=("teamviewer_linux_x64-${pkgver}.deb::http://www.teamviewer.com/download/version_8x/teamviewer_linux_x64.deb" "teamviewer.desktop")
  md5sums=('4f718ad52ea9091fab4218968a3c1fd7' 'ccff88e83d219c623872c9be23a50e7d')
  depends=('lib32-libsm' 'lib32-libxext' 'lib32-glibc' 'lib32-freetype2' 'lib32-gcc-libs' \
  'lib32-alsa-lib' 'lib32-libx11' 'lib32-libxtst' 'lib32-libxdamage' 'lib32-libxfixes' \
  'lib32-libxcb' 'lib32-libxi' 'lib32-libxau' 'lib32-libxdmcp')
fi


package() {
	cd $srcdir
	[ $CARCH == "i686" ] && ar x ${_pkgname}_linux-${pkgver}*
  	[ $CARCH == "x86_64" ] && ar x ${_pkgname}_linux_x64-${pkgver}*
	tar xvf data.tar.gz
	cp -R opt $pkgdir
	cp -R usr $pkgdir
	install -Dm644 $_pkgname.desktop $pkgdir/usr/share/applications/$_pkgname.desktop
}
