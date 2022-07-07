# Maintainer: jmcb <joelsgp@protonmail.com>
pkgname=pico8
pkgver=0.2.4c
pkgrel=1
pkgdesc='Fantasy console'
arch=('x86_64')
url='https://www.lexaloffle.com/pico-8.php'
license=('custom:pico8')
depends=('wget')
source=("pico-8_${pkgver}_amd64.zip"
		'pico8.desktop')
sha256sums=('00967d08289d08f0fe275b21f9453734fb6c3d7f674191fa6026a0301e837d43'
            '8f2c26a9c2c4997fc10e08eca9265534f1587dc018c0be40706403a91f645bae')

prepare() {
	mv -t ${srcdir} pico-8/pico8 pico-8/pico8.dat
	mv pico-8/lexaloffle-pico8.png pico8.png
	mv pico-8/license.txt LICENSE
	mv pico-8/readme_linux.txt ${pkgname}.1
	gzip -c ${pkgname}.1 > ${pkgname}.1.gz
}

package() {
	dest="${pkgdir}"/opt/${pkgname}
	share="${pkgdir}"/usr/share
	# executable
	install -Dm755 ${pkgname} "${dest}"/${pkgname}
	# data
	install -Dm644 -t "${dest}"/ pico8.dat
	# license
	install -Dm644 LICENSE "${share}"/licenses/${pkgname}/LICENSE
	# manual
	install -Dm644 ${pkgname}.1.gz "${share}"/man/man1/${pkgname}.1.gz
	# desktop entry
	install -Dm644 ${pkgname}.desktop "${share}"/applications/${pkgname}.desktop
	install -Dm644 ${pkgname}.png "${share}"/icons/${pkgname}.png
	# PATH symlink
	install -dm755 "${pkgdir}"/usr/bin/
	ln -s /opt/${pkgname}/${pkgname} "${pkgdir}"/usr/bin/${pkgname}
}
