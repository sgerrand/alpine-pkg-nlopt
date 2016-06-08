# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=nlopt
pkgver=2.4.2
pkgrel=1
pkgdesc="NLopt is a free/open-source library for nonlinear optimization"
url="http://ab-initio.mit.edu/wiki/index.php/NLopt"
arch="all"
license="LGPL"
depends=""
depends_dev=""
makedepends="$depends_dev autoconf gcc gzip make"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source="http://ab-initio.mit.edu/$pkgname/$pkgname-$pkgver.tar.gz"

_builddir="$srcdir/$pkgname-$pkgver"

prepare() {
	local i
	cd "$_builddir"
	for i in $source; do
		case $i in
		*.patch) msg $i; patch -p1 -i "$srcdir"/$i || return 1;;
		esac
	done
}

build() {
	cd "$_builddir"
	./configure --prefix=/usr --with-pic
	make
}

package() {
	cd "$_builddir"
	make install DESTDIR="$pkgdir"
}

doc() {
	arch="noarch"
	cd "$pkgdir"
	mkdir -p "$subpkgdir"/usr/share/man
	mv "$pkgdir"/usr/share/man/man3 "$subpkgdir"/usr/share/man/
	gzip -9 "$subpkgdir"/usr/share/man/man3/nlopt.3
}

md5sums="d0b8f139a4acf29b76dbae69ade8ac54  nlopt-2.4.2.tar.gz"
sha256sums="8099633de9d71cbc06cd435da993eb424bbcdbded8f803cdaa9fb8c6e09c8e89  nlopt-2.4.2.tar.gz"
sha512sums="136aacc00a69f77e8a7ce5dc26a5f3f027bc8c01b97aa1f43919462e0a412154eabfb01be258e082dffe61f9b554bb2bfbb550a7b82c7c77c7b22874a64a9703  nlopt-2.4.2.tar.gz"
