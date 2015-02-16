pkgname=diskmonitor
pkgver=0.2
pkgrel=1
pkgdesc='KDE tools to monitor SMART devices and MDRaid health status'
arch=('x86_64')
url="https://github.com/papylhomme/diskmonitor"
license=('GPLv2')
depends=('ki18n' 'kiconthemes' 'qt5-base' 'udisks2')
makedepends=('extra-cmake-modules')
source=( "https://github.com/papylhomme/${pkgname}/archive/${pkgver}.tar.gz")
md5sums=('99d50abe418bb0d34fe915ead6189c88')

build () {
	cd "${srcdir}/${pkgname}-${pkgver}"
	[ -e build ] || mkdir build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=/usr ..
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}/build"
	make DESTDIR="${pkgdir}" install
}
