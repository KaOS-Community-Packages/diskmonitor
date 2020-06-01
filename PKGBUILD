pkgname=diskmonitor
pkgver=0.3.4
pkgrel=1
pkgdesc='KDE tools to monitor SMART devices and MDRaid health status'
arch=('x86_64')
url="https://github.com/papylhomme/diskmonitor"
license=('GPLv2')
depends=('ki18n' 'kiconthemes' 'qt5-base' 'qt5-declarative' 'udisks2' 'knotifications' 'kiconthemes' 'kxmlgui' 'plasma-framework')
makedepends=('extra-cmake-modules')
source=("https://github.com/papylhomme/${pkgname}/archive/${pkgver}.tar.gz")
md5sums=('8ec1219c5a2464cd7cc330ba9587e55d')

build() {
    mkdir -p build
    cd build
    
    cmake ../${pkgname}-${pkgver} \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
    make
}

package() {
    cd build
    
    make DESTDIR="${pkgdir}" install
}
