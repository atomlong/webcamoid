# Maintainer: Gonzalo Exequiel Pedone <hipersayan DOT x AT gmail DOT com>

pkgname=webcamoid
pkgver=7.1.0
pkgrel=1
pkgdesc="Webcamoid is a full featured webcam capture application."
url='https://webcamoid.github.io/'
license=('GPL')
arch=('i686' 'x86_64' 'armv6h')
depends=('qt5-quickcontrols' 'qt5-svg' 'libpulse' 'v4l-utils' 'ffmpeg')
# Enable this lines if you want to use GStreamer instead of FFmpeg.
# WARNING: GStreamer support is experimental.
#depends=('qt5-quickcontrols' 'qt5-svg' 'libpulse' 'v4l-utils' 'gst-plugins-base-libs')
optdepends=('v4l2loopback-dkms: Virtual camera support')
#optdepends=('v4l2loopback-dkms: Virtual camera support'
#            'gst-plugins-base'
#            'gst-plugins-good'
#            'gst-plugins-bad'
#            'gst-plugins-ugly')
makedepends=('qt5-tools')
provides=('webcamoid')
source=("https://github.com/${pkgname}/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=('2a1ec890fa5d49fe8efcabb1027a68ec33103bad2cf2d95e03c0a40991a8fabd')

build() {
    cd "$srcdir/${pkgname}-${pkgver}"
    qmake-qt5 Webcamoid.pro #USE_GSTREAMER=1
    make
}

package() {
    cd "$srcdir/${pkgname}-${pkgver}"
    make INSTALL_ROOT="${pkgdir}" install
}
