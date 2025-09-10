# Maintainer: Nino K. <aur@assyt.fi>

pkgname=flumi-bin
_pkgname=Flumi-linux.x86_64

pkgver=1.0.1
pkgrel=1
epoch=1
pkgdesc='The wayfinder (browser) for Gurted, a "web ecosystem".'
arch=('x86_64')
url="https://github.com/outpoot/gurted"
license=('CC BY-NC 4.0')
depends=('glibc')

provides=()
conflicts=()
replaces=()

source=("https://github.com/outpoot/gurted/releases/download/v$pkgver/Flumi_Linux.tar.gz" "$pkgname.desktop")
sha256sums=("6912cd396d0ff1f8e6e2278f147a86050c3b96011bf6ca0e0f4a1843f3716c26" "e65085bd5504ee003365207ff20547cc0c6b7ff313979fbc25dcd164c4b548f5")

package() {
	mkdir -p "$pkgdir"/usr/bin
	mkdir -p "$pkgdir"/usr/share/applications
	mkdir -p "$pkgdir"/opt

	cp -r . "$pkgdir"/opt/$pkgname

	#very bad hardcoding the archive name dont like this
	rm "$pkgdir"/opt/$pkgname/Flumi_Linux.tar.gz

	chmod +x "$pkgdir"/opt/$pkgname/$_pkgname

	ln -s /opt/$pkgname/$_pkgname "$pkgdir"/usr/bin/$_pkgname

	
	cp $pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
}
