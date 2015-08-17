# Contributor: Skunnyk <skunnyk@archlinux.fr>
pkgname=playonlinux
pkgver=4.1.3
pkgrel=1
pkgdesc="GUI for managing Windows and DOS programs under linux"
url="http://www.playonlinux.com/"
license="GPL"
depends=('wine' 'imagemagick' 'xterm' 'wxpython' 'cabextract' 'unzip' 'mesa-demos' 'gnupg' 'icoutils' 'xdg-user-dirs' 'libxmu')
arch=('any')
source=(http://www.playonlinux.com/script_files/PlayOnLinux/$pkgver/PlayOnLinux_$pkgver.tar.gz PlayOnLinux.desktop use-python2.patch)
options=(!strip)
build() {
  cd "$srcdir/$pkgname"
#  rm bin/amd64.darwin.check bin/x86.darwin.check
  patch -p1  < ../use-python2.patch
  install -d $pkgdir/usr/share/$pkgname
  install -d $pkgdir/usr/bin 
}
package(){
  cp -r $srcdir/$pkgname/ $pkgdir/usr/share/
  echo "#!/bin/bash" > $pkgdir/usr/bin/$pkgname 
  echo "/usr/share/$pkgname/$pkgname \"\$@\"" >> $pkgdir/usr/bin/$pkgname
  chmod +x  $pkgdir/usr/bin/$pkgname
  install -D -m644 $srcdir/$pkgname/etc/playonlinux32.png $pkgdir/usr/share/pixmaps/playonlinux32.png 
  install -D -m644 $srcdir/PlayOnLinux.desktop $pkgdir/usr/share/applications/playonlinux.desktop 

}
md5sums=('f72f76a832a0e1ecf94d35951d3217f9'
         'c35b61fb168c4ef7740ad113996ea359'
         'b702ee262b2c894338896b40a277dc86')
