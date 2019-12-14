# Maintainer: aereaux <aidan@jmad.org>
_pkgname=meli
pkgname=${_pkgname}-git
pkgver=alpha.0.4.2.r43.g17a0f31
pkgrel=1
pkgdesc="Experimental terminal mail client aiming for configurability and extensibility with sane defaults."
arch=("x86_64")
url="https://meli.delivery/"
license=('GPL3')
depends=()
makedepends=("git" "rust")
optdepends=()
provides=("$_pkgname")
conflicts=("$_pkgname")
source=("git+https://git.meli.delivery/meli/meli.git")
md5sums=("SKIP")

pkgver() {
  cd "$_pkgname"

  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "$_pkgname"

  make
}

# TODO: Right now the makefile does not have a check target
#check() {
#  cd "$_pkgname"
#
#  cargo test --release --locked
#}

package() {
  cd "$_pkgname"

  make PREFIX=/usr DESTDIR="$pkgdir/" install
}
