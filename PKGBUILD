#Maintainer Erik Inkinen <erik.inkinen@gmail.com>
pkgname=libgbinder-radio
provides=('libgbinder-radio')
_pkgbase=libgbinder-radio
pkgver=72.6a9a0b7
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/libgbinder-radio"
license=('BSD')
depends=('libgbinder' 'libglibutil')
makedepends=('git' 'pkgconfig')
source=("libgbinder-radio::git+https://github.com/mer-hybris/libgbinder-radio.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib KEEP_SYMBOLS=1 release pkgconfig
}

package() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib DESTDIR="$pkgdir/" install-dev
}

