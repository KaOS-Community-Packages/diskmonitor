pkgname=diskmonitor
pkgver=0.3.1
pkgrel=1
pkgdesc='KDE tools to monitor SMART devices and MDRaid health status'
arch=('x86_64')
url="https://github.com/papylhomme/diskmonitor"
license=('GPLv2')
depends=('ki18n' 'kiconthemes' 'qt5-base' 'udisks2')
makedepends=('extra-cmake-modules')
source=( "https://github.com/papylhomme/${pkgname}/archive/${pkgver}.tar.gz")
md5sums=('40c1e8b93d4ad6b5532584e3172ece2e')

build() {
    mkdir -p build
    cd build
            
    cmake -DCMAKE_INSTALL_PREFIX=/usr ..
    make
}

package() {
    cd build
    
    make DESTDIR="${pkgdir}" install
}
