# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=qsystemd-git
pkgver=31.e8d10ad
pkgrel=1
pkgdesc='A simple Systemd service manager with a Qt interface'
arch=('i686' 'x86_64')
url='https://github.com/ilpianista/qsystemd'
license=('GPL')
depends=('libsystemd-qt-git' 'qt5-quickcontrols')
makedepends=('git')
provides=('qsystemd')
conflicts=('qsystemd')
source=('git://github.com/ilpianista/qsystemd')
md5sums=('SKIP')

pkgver() {
  cd qsystemd
  printf "%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../qsystemd \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
