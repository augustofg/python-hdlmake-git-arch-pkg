# Maintainer: Augusto Fraga Giachero <afg@augustofg.net>
# Based on the python-hdlmake PKGBUILD by Popolon <popolon@popolon.org>

pkgname='python-hdlmake-git'
_module='hdlmake'
_src_folder='hdl-make'
pkgver=r1660.51fc22f
pkgrel=1
pkgdesc="Generates multi-purpose makefiles for HDL projects management."
url="http://www.ohwr.org/projects/hdl-make"
depends=('python')
makedepends=('python-build' 'python-installer' 'python-wheel')
license=('GPL3')
arch=('any')
source=("git+https://ohwr.org/project/hdl-make.git")
sha256sums=('SKIP')
conflicts=('python-hdlmake')

pkgver() {
	cd "${srcdir}/${_src_folder}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}/${_src_folder}"
    python -m build --wheel --no-isolation
}

package() {
    depends+=()
    cd "${srcdir}/${_src_folder}"
    python -m installer --destdir="${pkgdir}" dist/*.whl
}
