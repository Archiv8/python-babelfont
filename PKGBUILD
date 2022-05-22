#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-babelfont/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-babelfont/discussions>

_langname="python"
_relname="babelfont"

pkgname="${_langname}-${_relname}"
pkgver=2.0.2
pkgrel=3
pkgdesc="Interrogate and manipulate UFO, TTF and OTF fonts with a common interface"
arch=(
  "any"
)
url="https://github.com/simoncozens/babelfont"
license=(
  "MIT"
)
depends=(
  "python"
  "python-defcon"
  "python-fontparts"
  "python-fonttools"
)
makedepends=(
  "python-setuptools"
)
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
)
sha512sums=(
  "c012045908d6f38587c3af09aee101cf3fbea544af8e702c2259f9020c36603bb86dca1045671203cd835b0d2613d06dafd6a3392864cd51ff0183a6832e7c1f"
)

build() {

  cd "${_tarname}"

  python setup.py build
}

package() {

  cd "${_tarname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE
}
