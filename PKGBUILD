# Maintainer: alucryd <alucryd at gmail dot com>
# Contributor: Balló György <ballogyor+arch at gmail dot com>

pkgname=bamf
pkgver=0.5.0
pkgrel=1
pkgdesc="Application matching framework"
arch=('i686' 'x86_64')
url="https://launchpad.net/bamf"
license=('GPL')
depends=('libgtop' 'libwnck3')
makedepends=('gobject-introspection' 'python2-lxml' 'vala')
options=('!libtool')
source=("http://launchpad.net/${pkgname}/${pkgver%.*}/${pkgver}/+download/${pkgname}-${pkgver}.tar.gz")
sha256sums=('93b1acced96d32b36270cf18feb2761014ce2226814303c632448f717a8f9113')

build() {
  cd ${pkgname}-${pkgver}

  export PYTHON='/usr/bin/python2'
  ./configure --prefix='/usr' --sysconfdir='/etc' --localstatedir='/var' --libexecdir="/usr/lib/${pkgname}" --disable-{static,webapps}
  make
}

package() {
  cd ${pkgbase}-${pkgver}

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
