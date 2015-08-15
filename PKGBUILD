# Maintainer: Andreas Theodosiou <andreasabu at gmail dot com>
# Contributor: Jonas Heinrich <onny@project-insanity.org>
# Contributor: DaZ <daz.root+arch@gmail.com>
# Contributor: Paul Nicholson <brenix at gmail.com>
# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Alex Anthony <alex.anthony28991@googlemail.com>

pkgname=epsilon
pkgver=0.7.0
pkgrel=2
pkgdesc="A package of Python utilities, famous for its Time class"
arch=('any')
url="https://code.launchpad.net/divmod.org"
license=('MIT')
depends=('twisted' 'python2-pyopenssl')
makedepends=('python2-setuptools')
source=("https://pypi.python.org/packages/source/E/Epsilon/Epsilon-${pkgver}.tar.gz")
md5sums=('39a5caa66e54e970cec8ddef18bf55a6')

build() {
  cd "${srcdir}/Epsilon-${pkgver}"
  python2 setup.py build
}

package() {
  cd "${srcdir}/Epsilon-${pkgver}"
  python2 setup.py install --root="${pkgdir}" --optimize=1
  install -D "LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  # Fix clash with festival
  mv "${pkgdir}/usr/bin/benchmark" "${pkgdir}/usr/bin/epsilon_benchmark"
}
