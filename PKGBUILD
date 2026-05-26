pkgname=keskos-installer-debug-log
pkgver=0.1.0
pkgrel=1
pkgdesc="KeskOS installer debug log viewer helper"
arch=(any)
url="https://github.com/memegeko/keskos"
license=(GPL-3.0-or-later)
depends=(
  konsole
)
optdepends=('keskos-calamares-branding: installs the Calamares launcher and debug log producer used by this viewer')
source=()
sha256sums=()

package() {
  local srcroot="${startdir}/files"

  install -D -m 755 "${srcroot}/airootfs/usr/local/bin/keskos-open-installer-log" "${pkgdir}/usr/local/bin/keskos-open-installer-log"
  install -D -m 644 "${srcroot}/airootfs/usr/share/applications/install-keskos-debug.desktop" "${pkgdir}/usr/share/applications/install-keskos-debug.desktop"
}
