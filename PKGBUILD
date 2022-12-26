pkgname=gaming-glyphs-git
pkgver=1r.
pkgrel=1
pkgdesc="Funny gaming-related glyphs"
arch=(any)
url="https://github.com/gregthemadmonk/gaming-glyphs.git"
makedepends=(git fontforge)
source=("git+$url")
md5sums=('SKIP')

pkgver() {
	cd gaming-glyphs
	printf "1r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd gaming-glyphs
	fontforge -lang ff -c 'Open($1); Generate($2);' 'gaming-glyphs.sfd' 'gaming-glyphs.ttf'
}

package() {
	DEST="$pkgdir/usr/share/fonts/ttf"
	mkdir -p "$DEST"
	cp 'gaming-glyphs/gaming-glyphs.ttf' "$DEST/"
}
