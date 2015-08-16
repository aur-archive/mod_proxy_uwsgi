_pkgbase=uwsgi
pkgname=mod_proxy_uwsgi
pkgver=2.0.8
pkgrel=1
pkgdesc='Apache uWSGI proxy module'
arch=(i686, x86_64)
url='http://projects.unbit.it/uwsgi'
license=('GPL2')
depends=(uwsgi apache)
source=("http://projects.unbit.it/downloads/${_pkgbase}-${pkgver}.tar.gz")
md5sums=('356b71060aa4c1f0e888dbca03567bd5')

build() {
  cd "${srcdir}/${_pkgbase}-${pkgver}/apache2"

  /usr/bin/apxs -c mod_proxy_uwsgi.c
}

package() {
  cd "${srcdir}/${_pkgbase}-${pkgver}/apache2"

  install -D -m755 \
      .libs/mod_proxy_uwsgi.so \
      "${pkgdir}/usr/lib/httpd/modules/mod_proxy_uwsgi.so"
}
