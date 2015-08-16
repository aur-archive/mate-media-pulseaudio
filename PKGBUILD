# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

_pkgname=mate-media
pkgname=${_pkgname}-pulseaudio
pkgver=1.6.0
pkgrel=5
pkgdesc="MATE Media Tools (pulseaudio)"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('libcanberra-pulse' 'libunique' 'mate-desktop'
         'mate-window-manager' 'pulseaudio')
makedepends=('mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
conflicts=("${_pkgname}-gstreamer" 'mate-settings-daemon-gstreamer')
provides=("${_pkgname}")
replaces=("${_pkgname}")
source=("http://pub.mate-desktop.org/releases/1.6/${_pkgname}-${pkgver}.tar.xz")
sha1sums=('06c3418dfe0be26e74b0e40aa92eea6260579a72')

build() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    ./autogen.sh \
        --prefix=/usr \
        --sysconfdir=/etc \
        --libexecdir=/usr/lib/${_pkgname} \
        --localstatedir=/var \
        --enable-pulseaudio \
        --disable-gstmix \
        --disable-gst-mixer-applet \
        --disable-static \
        --disable-scrollkeeper
    make
}

package() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
