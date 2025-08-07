# Maintainer: Harshith Goka <harshith9399@gmail.com>
pkgname=allthenticate-service-bin
_pkgname=allthenticate-service
_channel=stable
pkgver=2.2.16
pkgrel=1
epoch=
pkgdesc="Go passwordless and manage your SSH keys with your phone. The Allthenticate Passwordless Service lets you unlock and lock your computer with your smartphone using Bluetooth Low-Energy (BLE) technology as well as use a secure SSH key that's stored on your phone as your primary SSH key across computers."
arch=('x86_64')
url="https://www.allthenticate.com"
license=('unknown')
groups=()
depends=('alsa-lib' 'at-spi2-core' 'bash-completion' 'cairo' 'dbus' 'expat' 'gcc-libs' 'gdk-pixbuf2' 'glib2' 'glibc' 'gtk3' 'libcups' 'libdrm' 'libx11' 'libxcb' 'libxcomposite' 'libxdamage' 'libxext' 'libxfixes' 'libxkbcommon' 'libxrandr' 'libxshmfence' 'linux' 'mesa' 'nspr' 'nss' 'pam' 'pango' 'zlib')
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=('etc/apparmor.d/allthenticate' 'etc/xdg/autostart/allthenticate-gui.desktop')
options=()
install='.INSTALL'
changelog=
source=("https://debian.allthenticate.com/${_channel}/ubuntu/pool/noble/main/${_pkgname}_${pkgver}_amd64.deb")
noextract=()
sha256sums=("8458e3b3d3c7133a4c3ef2de6babe2203fda30674f1be6a963388d30677be22d")
validpgpkeys=()

package() {
    bsdtar -xf data.tar.xz -C "$pkgdir/"
    mv $pkgdir/lib $pkgdir/usr/lib

    sed -i '/\[Service\]/aEnvironment="SSL_CERT_DIR=/etc/ssl/certs/"' "$pkgdir"/usr/lib/systemd/system/sda-service.service
	chmod +x "$pkgdir"/usr/lib/security/libsda_desktop_pam.so
    rm "$pkgdir"/usr/share/pam-configs/allthenticate
}
