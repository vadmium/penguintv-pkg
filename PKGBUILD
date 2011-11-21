# Contributor: DonVla <donvla@users.sourceforge.net>

pkgname=penguintv
pkgver=4.1.0
pkgrel=1
pkgdesc="A podcast and video blog aggregator"
arch=('i686' 'x86_64')
url="http://penguintv.sourceforge.net/"
license=('GPL')
depends=('python-pysqlite' 'gnome-python-extras' 'pil' 'python-pycurl' 'pyxml' 'xulrunner')
depends+=('python2')
optdepends=('gstreamer0.10-python: enable built-in player' 'xapian-python-bindings: enable internal rss and podcast search')
makedepends=('python2' 'patch')
source=(http://downloads.sourceforge.net/project/${pkgname}/${pkgname}/4.1/${pkgname}_${pkgver}-0.tar.gz)
md5sums=('98bdd2ed232d3ffe4394d1cc531a95c9')
sha256sums=('5a8911ec0f6775f3fa30d381c8958a522664eddcce2a68c2bc6925020e74d070')

source+=(python2.patch)
md5sums+=('c396da58f51fdcf0e9c211829ec374b3')
sha256sums+=('f7021c2f2a7475e60515c2555d87d4416b67d0d28f14f57d2dc6f911f4c0ac07')

build() {
  patch -d "${srcdir}/PenguinTV-${pkgver}" -p 0 < python2.patch
}

package() {
  cd ${srcdir}/PenguinTV-$pkgver
  export MOZILLA_FIVE_HOME="/usr/lib/xulrunner-1.9.1"
  python2 setup.py install --prefix ${pkgdir}/usr 
}
