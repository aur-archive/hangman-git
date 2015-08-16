# Maintainer: Michael Plotke <bdjnks@gmail.com>

_pkgname=hangman
pkgname=${_pkgname}-git
pkgver=20140801.5986b07
pkgrel=1
pkgdesc='A simple command line hangman game'
url='https://github.com/bdjnk/hangman'
arch=('i686' 'x86_64' 'armv7h' 'armv6h')
license=('GPL2')
makedepends=('git')
source=("${_pkgname}::git+https://github.com/bdjnk/hangman.git")
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${srcdir}/${_pkgname}"
	git log -1 --format='%cd.%h' --date=short | tr -d -
}

build() {
	cd "${srcdir}/${_pkgname}"
	make
}

check() {
	cd "${srcdir}/${_pkgname}"
	#./hangman test
}

package() {
	cd "${srcdir}/${_pkgname}"
	install -Dm755 hangman "${pkgdir}/usr/bin/hangman"
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 wordlist "${pkgdir}/usr/share/wordlist"
}

