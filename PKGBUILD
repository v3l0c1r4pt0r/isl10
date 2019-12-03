# Maintainer: Liam Greenough (beacon515@gmail.com)
#Substantially adapted from the PKGBUILD of isl-git

pkgname=isl10
pkgver=0.10
pkgrel=1
pkgdesc="Library for manipulating sets and relations of integer points bounded by linear constraints"
arch=('i686' 'x86_64' 'armv7h')
url="http://isl.gforge.inria.fr/"
depends=('gmp')
license=('MIT')
options=('!libtool')
provides=("isl=${pkgver}")
conflicts=('isl-git' 'isl')
source=('http://isl.gforge.inria.fr/isl-0.10.tar.bz2')
md5sums=('c1ece653891bb2a5f55ca25e3f4e8f35')

build() {
  cd isl-${pkgver}
#  ./autogen.sh
  ./configure --prefix=/usr
  make
}

check() {
  cd isl-${pkgver}
  make check
}

package() {
  cd isl-${pkgver}
  make DESTDIR="$pkgdir" install

  install -dm755 "$pkgdir"/usr/share/gdb/auto-load/usr/lib/
  mv "$pkgdir"/usr/lib/libisl.so.*-gdb.py "$pkgdir"/usr/share/gdb/auto-load/usr/lib/
}
