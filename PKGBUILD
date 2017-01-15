pkgname=diskmonitor
pkgver=0.3.1
pkgrel=2
pkgdesc='KDE tools to monitor SMART devices and MDRaid health status'
arch=('x86_64')
url="https://github.com/papylhomme/diskmonitor"
license=('GPLv2')
depends=('ki18n' 'kiconthemes' 'qt5-base' 'udisks2')
makedepends=('extra-cmake-modules')
source=("https://github.com/papylhomme/${pkgname}/archive/${pkgver}.tar.gz"
        "${pkgname}.patch")
md5sums=('40c1e8b93d4ad6b5532584e3172ece2e'
         'bfe33fb9274286bb532c9b2a63ae6018')
prepare(){
    cd ${pkgname}-${pkgver}
    patch -p1 < $srcdir/${pkgname}.patch
}
         
build() {
    mkdir -p build
    cd build
    
    cmake ../${pkgname}-${pkgver} \
        -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release
    make
}

package() {
    cd build
    
    make DESTDIR="${pkgdir}" install
}
