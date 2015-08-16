# Author: Jonahtan Schaeffer <joschaeffer@gmail.com>
# Maintainer: Drake Arconis <lightdrake@gmail.com>

pkgname=jsoncpp
pkgver=0.5.0
pkgrel=3
pkgdesc="A JSON C++ library"
url="http://jsoncpp.sourceforge.net/"
license="Public"
arch=('i686' 'x86_64')
makedepends=('scons' 'gcc')
depends=('gcc-libs')
source=("http://sourceforge.net/projects/jsoncpp/files/jsoncpp/0.5.0/jsoncpp-src-${pkgver}.tar.gz/download")
md5sums=('24482b67c1cb17aac1ed1814288a3a8f')

build() {
  cd ${srcdir}/${pkgname}-src-${pkgver}
  scons platform=linux-gcc
}

package() {
  cd ${srcdir}/${pkgname}-src-${pkgver}
  
  mkdir -p ${pkgdir}/usr/include/jsoncpp
  cp -r include/json ${pkgdir}/usr/include/jsoncpp/json

  mkdir -p ${pkgdir}/usr/lib
  cp buildscons/linux-gcc-*/src/lib_json/libjson_linux-gcc*libmt.so ${pkgdir}/usr/lib/
  cd ${pkgdir}/usr/lib/ 
  ln -sf libjson_linux-gcc-*_libmt.so libjsoncpp.so
}

