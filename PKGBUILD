# Maintainer: josephgbr <rafael.f.f1 at gmail.com>

_pkgbase=libtasn1
pkgname=lib32-${_pkgbase}
pkgver=2.13
pkgrel=1
pkgdesc="The ASN.1 library used in GNUTLS (32 bit)"
arch=('x86_64')
license=('GPL3' 'LGPL')
url="http://www.gnu.org/software/libtasn1/"
depends=('lib32-glibc' ${_pkgbase})
makedepends=('gcc-multilib')
options=('!libtool')
source=("http://ftp.gnu.org/gnu/libtasn1/${_pkgbase}-${pkgver}.tar.gz")
sha1sums=('89120584bfedd244dab92df99e955a174c481851')

build() {
  export CC='gcc -m32'
  export CXX='g++ -m32'
  export PKG_CONFIG_PATH='/usr/lib32/pkgconfig'
  
  cd ${_pkgbase}-${pkgver}
  ./configure --prefix=/usr --libdir=/usr/lib32
  make
}

package() {
  cd ${_pkgbase}-${pkgver}
  make DESTDIR="${pkgdir}" install
  rm -rf "${pkgdir}/usr/"{bin,include,share}
}
