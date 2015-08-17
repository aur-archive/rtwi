# Maintainer: Aaron Ali <t0nedef@causal.ca>
pkgname=rtwi
pkgver=0.3.7
pkgrel=3
_svnver=120621
pkgdesc="A simple rTorrent web interface written in PHP by Gabor Hudiczius"
arch=('any')
url="http://rtwi.jmk.hu/"
install=$pkgname.install
license=('GPL')
depends=('rtorrent' 'php')
optdepends=(
	'apache: Web server to run rTWi'
	'cherokee: Lightweight Web server to run rTWi'
)
#	'http://static.jmk.hu/rtwi/downloads/rtwi/rtwi-'$pkgver'-'$_svnver'.tar.gz'
source=(
	'http://aur.causal.ca/archlinux/rtwi/rtwi-'$pkgver'.tar.gz'
	'magnet_base64.patch'
	'xmlrpc_methods.patch'
)
build() {
	cd rtwi-${pkgver}-${_svnver}
	patches="magnet_base64.patch xmlrpc_methods.patch"
	for patch in $patches; do
		patch -i ../${patch}
	done
}

package() {
	install -d ${pkgdir}/srv/http
	cp -r rtwi-${pkgver}-${_svnver} ${pkgdir}/srv/http/rtwi
}
#
md5sums=('89d23dad6c66f2b00054f91af23c531d'
         'db0a0ac19e5e9b3e0c81aef0d9abcd59'
         '53c4dd3f53187c6953c22cc45f1889b2')
