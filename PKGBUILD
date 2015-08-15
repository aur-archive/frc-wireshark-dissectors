#Maintainer: Alex Brinister (alex_brinister at yahoo dot com)
pkgname=frc-wireshark-dissectors
pkgver=0.1
pkgrel=2
pkgdesc="Wireshark dissectors to handle data from the cRIO"
arch=(any)
provides=('frc-wireshark-dissectors')
url="http://firstforge.wpi.edu/sf/projects/c--11_toochain"
license=('GPL')
depends=('wireshark-cli')
options=('!strip' 'libtool' '!zipman')
source=(https://www.dropbox.com/s/mj3co468tr0g6il/$pkgname-$pkgver.tar.xz)
sha512sums=('c9025445719d6a6f007fc72f16c75469c5b23d9513e8d8d4419a9387d049c2eed44cf1ab637cb2959559228513570899b6269651929583cd220e632bef5f0ce4')

_ver=`pacman -Qs wireshark-svn`
package() {
  	cd "$srcdir/$pkgname-$pkgver"
  	if [[ -n "$_ver" ]]; then
  		install -Dm755 wdb.so "$pkgdir/usr/lib/wireshark/plugins/1.9.1/wdb.so"
		install -Dm755 frcds.so "$pkgdir/usr/lib/wireshark/plugins/1.9.1/frcds.so"
	else
		install -Dm755 wdb.so "$pkgdir/usr/lib/wireshark/plugins/1.8.6/wdb.so"
		install -Dm755 frcds.so "$pkgdir/usr/lib/wireshark/plugins/1.8.6/frcds.so"
	fi
}
