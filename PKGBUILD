pkgname=pecl-memcache
pkgver=3.0.8
pkgrel=1
_commit=e3e9aa9e4bcc54b8c73077bc9bef9c1bf8648f6b
pkgdesc="Caching daemon designed for dynamic web applications to decrease database load by storing objects in memory."
arch=('x86_64')
url="https://github.com/websupport-sk/pecl-memcache"
license=('PHP')
depends=('php')
backup=('etc/php/conf.d/memcache.ini')
source=("https://github.com/websupport-sk/pecl-memcache/archive/${_commit}.zip")
md5sums=('ed2a2babd85b8461ca3566fa6869c679')

build() {
  cd ${pkgname}-${_commit}

  phpize
  ./configure --prefix=/usr
  make
}

package() {
  cd ${pkgname}-${_commit}
  make INSTALL_ROOT=${pkgdir} install

  echo 'extension=memcache.so' >memcache.ini
  install -Dm644 memcache.ini ${pkgdir}/etc/php/conf.d/memcache.ini
}
