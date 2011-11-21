# Contributor: DonVla <donvla@users.sourceforge.net>

pkgname=penguintv
pkgver=4.2.0
pkgrel=1
pkgdesc="A podcast and video blog aggregator"
arch=('i686' 'x86_64')
url="http://penguintv.sourceforge.net/"
license=('GPL')
depends=('python-pysqlite' 'gnome-python-extras' 'pil' 'python-pycurl' 'pyxml' 'xulrunner')
optdepends=('gstreamer0.10-python: enable built-in player' 'xapian-python-bindings: enable internal rss and podcast search')
source=(http://downloads.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver%.*}/${pkgname}_${pkgver}.tar.gz)
md5sums=('9458c7ce15cca0469a131de5a01bbd8d')
sha256sums=('cfcd52fdb37d93eb31148a3c8097e54dc8ca0181c5a8e38483c372ae98e4e4b2')

build() {
  cd ${srcdir}/PenguinTV-$pkgver
  export MOZILLA_FIVE_HOME="/usr/lib/xulrunner-1.9.1"
  python setup.py install --prefix ${pkgdir}/usr 
}
