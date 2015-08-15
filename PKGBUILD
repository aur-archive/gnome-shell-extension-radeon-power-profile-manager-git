# Maintainer: Alucryd <alucryd at gmail dot com>

pkgname=gnome-shell-extension-radeon-power-profile-manager-git
pkgver=34
pkgrel=1
pkgdesc="Radeon Power Profile Manager"
arch=('any')
url="https://github.com/StuntsPT/shell-extension-radeon-power-profile-manager"
license=('GPL2')
depends=('gnome-shell' 'polkit' 'systemd')
makedepends=('git')
source=("${pkgname%-*}::git+https://github.com/StuntsPT/shell-extension-radeon-power-profile-manager.git"
        'radeon.conf')
sha256sums=('SKIP'
            '03a5d708940bf68ee19b040e781b42d4e4144aa2ada145a5027f3939ec3e4e68')

pkgver() {
  cd ${pkgname%-*}

  git rev-list --count HEAD
}

package() {
  cd ${pkgname%-*}

  mkdir -p "${pkgdir}"/usr/{lib/tmpfiles.d,share/gnome-shell/extensions/RadeonPowerProfileManager@StuntsPT.github.com}
  cp -dr --no-preserve=ownership * "${pkgdir}"/usr/share/gnome-shell/extensions/RadeonPowerProfileManager@StuntsPT.github.com/
  cp --no-preserve=ownership ../radeon.conf "${pkgdir}"/usr/lib/tmpfiles.d/

# Fix permissions
  find "${pkgdir}" -type d -exec chmod 755 {} +
  find "${pkgdir}" -type f -exec chmod 644 {} +
}

# vim: ts=2 sw=2 et:
