# Conributor: Kyle Keen <keenerd@gmail.com>
# Contributor: thotypous <matiasΘarchlinux-br·org>
# Contributor: Jaroslaw Swierczynski <swiergotΘaur·archlinux·org>

pkgname=skype-oss
pkgver=2.0.0.72
pkgrel=4
arch=('i686')
pkgdesc="P2P software for high-quality voice communication (OSS-compatible version)"
url="http://www.skype.com/"
license=('custom')
# Don't ask me why, but skype is dinamically linked to libasound.so.2,
# so this package really depends on alsa-lib, even if it doesn't use it.
depends=('fontconfig' 'libxinerama' 'libxi' 'libxcursor' 'libsm' 'libxrandr' 'gcc-libs' 'libxv' 'libxss' 'alsa-lib' 'oss' 'xdg-utils')
provides=("skype=${pkgver}")
conflicts=('skype' 'skype-staticqt')
install=skype-oss.install
#source=("http://download.skype.com/linux/skype_static-$pkgver-oss.tar.bz2" PERMISSION)
# todo: find a real mirror
source=("http://kmkeen.com/tmp/skype_static-$pkgver-oss.tar.bz2" PERMISSION)
md5sums=('ff41dd31906484863884ee0a7da441c1'
         '26e1772379d4d4df9471b6ed660a6d97')

package() {
  cd "$srcdir/skype_static-$pkgver-oss"
  install -m 755 -d "$pkgdir/usr/share/skype"/{avatars,lang,sounds}
  install -m 644 avatars/* "$pkgdir/usr/share/skype/avatars"
  install -m 644 lang/* "$pkgdir/usr/share/skype/lang"
  install -m 644 sounds/* "$pkgdir/usr/share/skype/sounds"
  install -m 755 -D skype "$pkgdir/usr/bin/skype"
  install -m 644 -D skype.conf "$pkgdir/etc/dbus-1/system.d/skype.conf"
  install -m 644 -D icons/SkypeBlue_16x16.png "$pkgdir/usr/share/icons/hicolor/16x16/skype.png"
  install -m 644 -D icons/SkypeBlue_32x32.png "$pkgdir/usr/share/icons/hicolor/32x32/skype.png"
  install -m 644 -D icons/SkypeBlue_48x48.png "$pkgdir/usr/share/icons/hicolor/48x48/skype.png"
  install -m 644 -D icons/SkypeBlue_48x48.png "$pkgdir/usr/share/pixmaps/skype.png"
  install -m 644 -D skype.desktop "$pkgdir/usr/share/applications/skype.desktop"
  install -m 644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m 644 -D "$srcdir/PERMISSION" "$pkgdir/usr/share/licenses/$pkgname/PERMISSION"
}
