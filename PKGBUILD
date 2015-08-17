# Maintainer: Melissa Padilla <mpadilla2 at hotmail dot com>
# Contributor: Mike Cooper <mythmon@gmail.com>
pkgname=('python2-dateutils')
pkgver=0.6.6
pkgrel=3
pkgdesc="Various utilities for working with date and datetime objects"
url="https://pypi.python.org/pypi/dateutils"
arch=('any')
license=('BSD')
depends=('python2' 'python2-argparse' 'python2-dateutil' 'python2-pytz')
makedepends=('python2-setuptools')
provides=('dateadd' 'datediff')
conflicts=('python-dateutils')
source=("https://pypi.python.org/packages/source/d/dateutils/dateutils-${pkgver}.tar.gz" "LICENSE.txt")
md5sums=('2ba7fcac03635f1f1cad0d94d785001b'
         '81274242b57f07983b3b1ea4a9cf63df')
sha256sums=('c94a8e77d743abac79ed91f99f5ef594a972a527e05145cbb7aba59beced8a71'
            '034af0f12aedb47d8a201bd38ea7449dad4520a268d44266036b58e072847606')

prepare() {
  cd "$srcdir/dateutils-$pkgver"
  sed -i 's|#!/usr/bin/env python|#!/usr/bin/env python2|' setup.py
}

build() {
  cd "$srcdir/dateutils-$pkgver"
  python2 setup.py build
}

package() {
  cd "$srcdir/dateutils-$pkgver"
  python2 setup.py install --prefix=/usr --root="$pkgdir" --optimize=1

  install -D -m644 ../LICENSE.txt \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE.txt"
}

