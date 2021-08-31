# Maintainer: Greedwolf DSS <greedwolf.dss@gmail.com>
pkgname=rtags
pkgver=2.40
pkgrel=1
epoch=
pkgdesc="A client/server application that indexes C/C++ code"
arch=('i686' 'x86_64')
license=('GPL')
groups=()
depends=()
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
# source=($pkgname-$pkgver.tar.gz
# 	$pkgname-$pkgver.patch)
noextract=()
md5sums=()

# prepare() {
#   # cd "$srcdir/$pkgname-$pkgver"

#   # patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
# }

build() {
  cd ..
  cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=1 -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr .
  make
}

# check() {
#   # cd "$srcdir/$pkgname-$pkgver"

#   # make -k check
# }

package() {
  cd ..
  make DESTDIR="${pkgdir}/" install
  install -D --mode=644 share/etc/services/system/rdm.service "${pkgdir}"/usr/lib/systemd/user/rdm.service
  install -D --mode=644 share/etc/services/system/rdm.socket "${pkgdir}"/usr/lib/systemd/user/rdm.socket

  install -D --mode=644 LICENSE.txt  "${pkgdir}"/usr/share/licenses/"${pkgname}"/LICENSE
}

# vim:set ts=2 sw=2 et:
