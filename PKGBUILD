# Maintainer: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Contributor: Andreas Wagner <Andreas dot Wagner at em dot uni-frankfurt dot de>

pkgname=oniguruma
pkgver=6.9.0
pkgrel=1
pkgdesc="a regular expressions library"
arch=('x86_64')
url="https://github.com/kkos/oniguruma"
license=('BSD')
source=("https://github.com/kkos/oniguruma/releases/download/v$pkgver/onig-$pkgver.tar.gz")
sha256sums=('91bfb25e050ce3c301483204dd3f0d03a7c05472e20d48fe227a383d4534e7c9')

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
