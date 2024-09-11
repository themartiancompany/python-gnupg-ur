# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Sven Klomp <mail@klomp.eu>
# Contributor: Sven Klomp <mail@klomp.eu>

_py="python"
_pkg=gnupg
pkgname="${_py}-${_pkg}"
_pkgsrcname="${pkgname}"
pkgver=0.4.0
pkgrel=1
_pkgdesc=(
  "This module allows easy access to GnuPG's key management,"
  "encryption and signature functionality from Python programs."
)
pkgdesc="${_pkgdesc[*]}"
url="https://pypi.python.org/pypi/${pkgname}" 
license=(
  "BSD"
)
arch=(
  "any"
)
depends=(
  "${_py}"
  "${_pkg}"
) 
makedepends=(
  "${_py}-setuptools"
)
_pypi="https://pypi.io/packages/source"
source=(
  "${_pypi}/${pkgname::1}/${pkgname}/${pkgname}-${pkgver}.tar.gz"
)
#source=("https://pypi.python.org/packages/ec/bc/6e27b54c2fd74f40c0b040693a5d7be20ab4e6e996dc2344cd918e360c16/python-gnupg-0.3.9.tar.gz")
sha256sums=(
  'e6aaf344852fa11824e4151ab63326a07dd0ef977dddffcce43669a79842a8f9'
)

prepare() {
  cd \
    "${srcdir}/${pkgname}-${pkgver}/"
}

build() {
  cd \
    "${srcdir}/${pkgname}-${pkgver}/"
  "${_py}" \
    setup.py \
    build
}

package() {
  cd \
    "${srcdir}/${pkgname}-${pkgver}/"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
	--optimize=1
  install \
    -Dm644 \
    LICENSE.txt \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

