pkgname=peg-markdown
pkgver=0.4.14
pkgrel=1
pkgdesc="An implementation of markdown in C, using a PEG grammar"
arch=('i686' 'x86_64')
url="https://github.com/jgm/peg-markdown/"
license=('GPL' 'MIT')
depends=('glib2')
options=('!buildflags')
provides=('markdown')
conflicts=('markdown')
source=("$pkgname-$pkgver.tar.gz::https://github.com/jgm/$pkgname/archive/$pkgver.tar.gz")
md5sums=('3ed6318831ebcc8539dd3d9e96982545')

build() {
  cd $pkgname-$pkgver
  make
  #  
  # for possible future reference, this is currently necessary in the git version:
  # make CC="cc -fPIC"
  #
  # also note that !buildflags is used above due to build failure with the
  # -O2 CFLAG, but the git version does not need this
}

package() {
  cd $pkgname-$pkgver
  install -Dm755 markdown "$pkgdir"/usr/bin/markdown
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/peg-markdown/LICENSE
}
