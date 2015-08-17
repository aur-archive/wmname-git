# Contributor: Army

_pkgname=wmname
pkgname=$_pkgname-git
pkgver=20130813.6
pkgrel=1
pkgdesc="prints/sets the window manager name property of the root window"
arch=('i686' 'x86_64')
url='http://tools.suckless.org/wmname'
license=('MIT')
depends=('libx11')
makedepends=('git')
provides=("$_pkgname")
conflicts=("$_pkgname")
source=("$_pkgname::git+http://git.suckless.org/wmname")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  echo "$(git log -1 --format="%cd" --date=short | sed 's|-||g').$(git rev-list --count master)"
}

build() {
  cd "$srcdir/$_pkgname"
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
