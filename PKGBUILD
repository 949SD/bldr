# Maintainer: David K david.dk949@gmail.com
_pkgname=bldr
pkgname="${_pkgname}-949sd"
pkgver="unknown"
pkgrel=0
pkgdesc="Execute build commands from anywhere in the project."
arch=('x86_64')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
makedepends=('go')
optdepends=()
provides=('bldr')
source=("$pkgname::git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
