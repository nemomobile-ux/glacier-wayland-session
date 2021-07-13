## $Id$
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey (NeoChapay) <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=glacier-wayland-session
pkgver=0.3
pkgrel=1
pkgdesc="Glacier Wayland session"
arch=('x86_64' 'aarch64')
url="https://github.com/nemo-packaging/glacier-wayland-session"
license=('GPL-3.0-or-later')
depends=('lipstick-glacier-home-git' 'lightdm')
makedepends=()
optdepends=()
source=("nemomobile.desktop" "nemomobile-session" "run-systemd-session" "dbus-env.service")
sha512sums=('SKIP' 'SKIP' 'SKIP' 'SKIP')

prepare(){
    mkdir -p "${pkgdir}/usr/bin"
    mkdir -p "${pkgdir}/usr/share/nemomobile-session"
    mkdir -p "${pkgdir}/usr/share/lightdm/sessions"
}

package() {
    install -Dm755 "${srcdir}/run-systemd-session" -t "${pkgdir}/usr/share/nemomobile-session/"
    install -Dm755 "${srcdir}/nemomobile-session" -t "${pkgdir}/usr/bin"
    install -Dm644 "${srcdir}/nemomobile.desktop" -t "${pkgdir}/usr/share/lightdm/sessions/"
    mkdir -p "${pkgdir}/usr/lib/systemd/user/graphical-session.target.wants"
    install -Dm644 "${srcdir}/dbus-env.service" -t "${pkgdir}/usr/lib/systemd/user/"
    ln -s ../dbus-env.service "${pkgdir}/usr/lib/systemd/user/graphical-session.target.wants/"
}
