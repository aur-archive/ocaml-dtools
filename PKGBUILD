# Maintainer: Charles E Hawkins <charlesthehawk at yahoo dot com>
# Contributor: Thomas S Hatch <thatch45 at gmail dot com>
# Contributor: Luciano A. Ferrer <laferrer@gmail.com>
pkgname=ocaml-dtools
pkgver=0.3.1
pkgrel=1
arch=('i686' 'x86_64')
license=('GPL')
pkgdesc="OCaml daemon tools library."
url="http://savonet.sourceforge.net/"
depends=()
makedepends=('ocaml' 'ocaml-findlib')
source=("http://downloads.sourceforge.net/savonet/${pkgname}-${pkgver}.tar.gz")
md5sums=('85dfc59a50169eedbc8289f553ad36ef')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make all
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  mkdir -p ${pkgdir}$(ocamlfind printconf destdir)
  mkdir -p ${pkgdir}/usr/share/doc/${pkgname}
  cp -r doc/html ${pkgdir}/usr/share/doc/${pkgname}
  make OCAMLFIND_DESTDIR=${pkgdir}$(ocamlfind printconf destdir) install
}
