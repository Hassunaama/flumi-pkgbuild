# Maintainer: Nino K. <aur@assyt.fi>

workflow_artifacts="https://api.github.com/repos/Hassunaama/gurted-linux-ci-autobuild/releases";

digest=$(
  curl -Ls $workflow_artifacts |
  grep -m1 '"digest":' |
  sed -E 's/.*"sha256:([0-9a-f]+)".*/\1/'
)


pkgname=flumi-bin
_pkgname=Flumi.x86_64

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

source=("https://github.com/Hassunaama/gurted-linux-ci-autobuild/releases/download/infinite/flumi.zip" "$pkgname.desktop")
sha256sums=("69a4beceb93bdfea4833d43d5366844ddbab6c883868ab361a45851a6c745259" "a36f76492d0779302d25cd6770f22385013a1d8cfb3dcaa9fe75060835f3ec60")

package() {
	mkdir -p "$pkgdir"/usr/bin
	mkdir -p "$pkgdir"/usr/share/applications
	mkdir -p "$pkgdir"/opt

	cp -r . "$pkgdir"/opt/$pkgname
	rm "$pkgdir"/opt/$pkgname/flumi.zip
	chmod +x "$pkgdir"/opt/$pkgname/$_pkgname

	ln -s /opt/$pkgname/$_pkgname "$pkgdir"/usr/bin/$_pkgname

	
	cp $pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
}
