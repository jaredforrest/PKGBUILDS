# $Id$
# Maintainer: Jared Forrest <jared_forrest@mailbox.org>

pkgname=dwm-jared
pkgver=6.2.r
pkgrel=1
pkgdesc="A dynamic window manager for X"
url="https://github.com/jaredforrest/dwm.git"
arch=('i686' 'x86_64')
license=('MIT')
options=()
depends=('libx11' 'libxinerama' 'libxft' 'freetype2' 'st' 'dmenu' 'ttf-dejavu')
makedepends=(make)
provides=(dwm)
conflicts=(dwm)
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "6.2.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd dwm
  make
}


package() {
  cd dwm  
  mkdir -p ${pkgdir}/opt/${pkgname}
  mkdir -p ${pkgdir}/usr/share/xsessions
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/dwm-jared/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/dwm-jared/README.md"
}
