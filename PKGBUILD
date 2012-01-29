# Contributor: DonVla <donvla@users.sourceforge.net>

pkgname=penguintv
pkgver=4.5.0
_tarname="PenguinTV-${pkgver}"
pkgrel=1
pkgdesc="A podcast and video blog aggregator"
arch=('any')
url="http://penguintv.sourceforge.net/"
license=('GPL')
depends=('python-pysqlite' 'gnome-python-extras' 'pil' 'python-pycurl' 'pyxml' 'xulrunner')
depends+=('python2')
depends+=('sh')
optdepends=('gstreamer0.10-python: enable built-in player' 'xapian-python-bindings: enable internal rss and podcast search')
makedepends=('python2' 'patch')
source=("http://downloads.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver%.*}/${_tarname}.tar.gz")
md5sums=('49ebc329d3573ddc5ddd342dcec064aa')
#sha1sums=('e3090c33085f2b4f21760850916dddc42a554288')

source+=(python2.patch)
md5sums+=('c396da58f51fdcf0e9c211829ec374b3')
#sha256sums+=('f7021c2f2a7475e60515c2555d87d4416b67d0d28f14f57d2dc6f911f4c0ac07')

# Files missing from tarball
_pixmaps='share/pixmaps'
_icon='penguintvicon.png'
_rev="revision=635"
_viewvc="http://${pkgname}.svn.sourceforge.net/viewvc/${pkgname}/trunk"

source+=("64x64.png::${_viewvc}/${_pixmaps}/64x64/${_icon}?${_rev}")
md5sums+=('fe503765e69b0eeba47d2955342073f9')
source+=("40x40.png::${_viewvc}/${_pixmaps}/40x40/${_icon}?${_rev}")
md5sums+=('fb27238877712da45d5badcb54ffd238')
source+=("26x26.png::${_viewvc}/${_pixmaps}/26x26/${_icon}?${_rev}")
md5sums+=('c99cc0c6856d6c29c7297aedb63a624a')

build() {
  local size
  for size in 64x64 40x40 26x26; do
    mkdir -p "${srcdir}/${_tarname}/${_pixmaps}/${size}"
    ln -sf "../../../../${size}.png" "${srcdir}/${_tarname}/${_pixmaps}/${size}/${_icon}"
  done
  
  patch -d "${srcdir}/${_tarname}" -p 0 < python2.patch
}

package() {
  cd "${srcdir}/${_tarname}"
  export MOZILLA_FIVE_HOME="/usr/lib/xulrunner-1.9.1"
  python2 setup.py install --prefix ${pkgdir}/usr 
}
