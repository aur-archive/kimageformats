# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kimageformats
pkgver=4.99.0
pkgrel=1
pkgdesc='KImageFormats'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kimageformats'
license=('LGPL')
depends=('qt5-base' 'jasper' 'openexr')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('d8ee2764901c7d9575eb71c92dc5f48f')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
