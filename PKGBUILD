# Contributor: kj_sh604 <43.splash@gmail.com>

pkgname=libglademm
pkgver=2.6.7
pkgrel=604
pkgdesc="A C++ wrapper for libglade."
arch=('x86_64')
url="http://gtkmm.sourceforge.net/"
license=('LGPL')
depends=('libglade' 'gtkmm')
makedepends=('pkgconfig')

# use this source when PKGBUILD breaks in the future:
# source=(https://aedrielkylejavier.me/assets/${pkgname}/2.6/${pkgname}-${pkgver}.tar.bz2)

source=(https://download.gnome.org/sources/${pkgname}/2.6/${pkgname}-${pkgver}.tar.bz2)

build() {
  cd ${pkgname}-${pkgver}
  CXXFLAGS+=' -std=c++11'
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var

  sed -i -e 's/ -shared / -Wl,-O1,--as-needed\0/g' libtool

  make
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
}
