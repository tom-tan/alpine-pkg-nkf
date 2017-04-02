# Contributor: Tomoya Tanjo <ttanjo@gmail.com>
# Maintainer: Tomoya Tanjo <ttanjo@gmail.com>
pkgname=nkf
pkgver=2.1.4
pkgrel=0
pkgdesc="A yet another kanji code converter among networks, hosts and terminals"
url="https://ja.osdn.net/projects/nkf/"
arch="x86_64"
license="zlib"
depends=""
makedepends=""
subpackages="$pkgname-doc"
source="http://iij.dl.osdn.jp/nkf/64158/${pkgname}-${pkgver}.tar.gz"

build() {
        cd "$builddir"
        make || return 1
}

package() {
        cd "$builddir"
        make MKDIR="mkdir -p" prefix="$pkgdir"/usr install-main || return 1
}

doc() {
        cd "$builddir"
        make MKDIR="mkdir -p" prefix="$subpkgdir"/usr/share install-man install-man-ja || return 1
        for f in $(find "$subpkgdir"/usr/share/man -type f)
        do
            gzip $f
        done
}
