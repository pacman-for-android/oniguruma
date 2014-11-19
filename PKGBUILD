# Maintainer: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Contributor: Andreas Wagner <Andreas dot Wagner at em dot uni-frankfurt dot de>

pkgname=oniguruma
pkgver=5.9.5
pkgrel=2
pkgdesc="a regular expressions library"
arch=('i686' 'x86_64')
url="http://www.geocities.jp/kosako3/oniguruma/"
license=('BSD')
options=(!libtool)
source=("http://www.geocities.jp/kosako3/oniguruma/archive/onig-$pkgver.tar.gz")
sha256sums=('9f49ae7819a5f47e25449d0e4b010d479f7868a24a7b9884b47041b49a76438a')

build() {
	cd "$srcdir/onig-$pkgver"
	./configure --prefix=/usr
	make
}

package() {
	cd "$srcdir/onig-$pkgver"
	make DESTDIR="$pkgdir" install
}
