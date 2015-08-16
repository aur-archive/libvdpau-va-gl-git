# Maintainer: Behem0th <grantipak@gmail.com>
# Contributor: 謝致邦 <Yeking@Red54.com>
# Contributor: lolilolicon <lolilolicon@gmail.com>

pkgname=libvdpau-va-gl-git
_realname=libvdpau-va-gl
pkgver=20140903
pkgrel=1
pkgdesc='VDPAU driver with OpenGL/VAAPI backend. Git version'
arch=('i686' 'x86_64')
url='https://github.com/i-rinat/libvdpau-va-gl'
license=('LGPLv3')
depends=('libvdpau' 'libva' 'libgl' 'ffmpeg' 'glu')
makedepends=('git' 'cmake')
provides=('libvdpau-va-gl')
conflicts=('libvdpau-va-gl')
source=('git://github.com/i-rinat/libvdpau-va-gl.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_realname"
  git log -1 --format="%cd" --date=short | tr -d -
}

build() {
  cd "$srcdir/$_realname"
  cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/$_realname"
  make DESTDIR="$pkgdir" install
}

