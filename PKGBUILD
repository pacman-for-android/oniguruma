# Maintainer: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Contributor: Andreas Wagner <Andreas dot Wagner at em dot uni-frankfurt dot de>

pkgname=oniguruma
pkgver=6.0.0
pkgrel=1
pkgdesc="a regular expressions library"
arch=('i686' 'x86_64')
url="https://github.com/kkos/oniguruma"
license=('BSD')
options=(!libtool)
source=("https://github.com/kkos/oniguruma/releases/download/v$pkgver/onig-$pkgver.tar.gz")
sha256sums=('0cd75738a938faff4a48c403fb171e128eb9bbd396621237716dbe98c3ecd1af')

build() {
	cd "$srcdir"/onig-$pkgver
	./configure --prefix=/usr
	make
}

package() {
	cd "$srcdir"/onig-$pkgver
	make DESTDIR="$pkgdir" install
	install -dm755 "$pkgdir"/usr/share/doc
	cp -r doc "$pkgdir"/usr/share/doc/$pkgname
	for licfile in COPYING INSTALL; do
		install -Dm644 $licfile "$pkgdir"/usr/share/licenses/$pkgname/$licfile
	done
}
