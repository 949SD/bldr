# Maintainer: David K david.dk949@gmail.com
pkgname=bldr
pkgver="unknown"
pkgrel=0
pkgdesc="Execute build commands from anywhere in the project."
arch=('x86_64')
url="https://github.com/dk949/$pkgname"
license=('MIT')
makedepends=('go')
optdepends=()
provides=('bldr')
source=("git+$url")
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
