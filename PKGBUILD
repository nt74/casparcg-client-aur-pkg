# Maintainer: Nikos Toutountzoglou <nikos.toutou@protonmail.com>
# Original AUR package: https://aur.archlinux.org/packages/casparcg-client-bin

pkgname=casparcg-client
pkgver=2.0.9
pkgrel=1
pkgdesc="A client software used to control the CasparCG Server software"
arch=(x86_64)
url="http://www.casparcg.com/"
license=(GPL)
depends=(vlc)
provides=(casparcg-client)
conflicts=(casparcg-client)
_next='cb3ad0d7f3cd20f950f5976ccffca5e68b9f45ba'
source=("https://casparcg.com/builds/CasparCG%20Client/next/CasparCG%20Client%20${_next}.tar.gz")
sha256sums=('12107cbc9553ae6d0f6d080398954ebcc4cc0e28c7cbf5c3f204ddefa6aabe91')

prepare() {
# Create executable /usr/bin file
cat > casparcg-client <<EOF
#!/bin/sh
cd /opt/casparcg-client && ./run.sh
EOF
}

package() {
	mkdir -p "$pkgdir"/usr/bin "$pkgdir"/opt/$pkgname
	cp -av "CasparCG Client $_next"/* "$pkgdir"/opt/$pkgname
	install -m755 $pkgname "$pkgdir"/usr/bin/$pkgname
}
