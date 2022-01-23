# Maintainer: James Stronz <comrumino@archstrike.org>

_pkgname=custom-certbot
pkgname="${_pkgname}-git"
pkgver=v2.0.0.r8.g95fe464
pkgrel=1
pkgdesc="custom certbot"
arch=('x86_64')
url="https://github.com/comrumino/$_pkgname"
license=('GPL3')
depends=('certbot')
makedepends=('git')
conflicts=()
source=("${_pkgname}::git+$url")
sha512sums=('SKIP')

pkgver() {
  cd "$srcdir/${_pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}


package() {
  cd "$srcdir/${_pkgname}"
  install -Dm644 "${_pkgname}.service" "${pkgdir}/etc/systemd/system/${_pkgname}.service"
  install -Dm644 "${_pkgname}.timer" "${pkgdir}/etc/systemd/system/${_pkgname}.timer"
  install -Dm644 "${_pkgname}.timer" "${pkgdir}/etc/systemd/system/${_pkgname}.timer"
  install -Dm644 "nginx.conf" "${pkgdir}/usr/share/${_pkgname}/nginx.conf"
  install -Dm644 "nginx-http.conf" "${pkgdir}/usr/share/${_pkgname}/nginx-http.conf"
}

# vim:se ts=2 sw=2 sts=2 et:
