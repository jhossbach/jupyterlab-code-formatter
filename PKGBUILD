# Maintainer: jhossbach <julian dot hossbach at gmx dot de>

pkgname=jupyterlab-code-formatter
_name=jupyterlab_code_formatter
pkgver=2.2.1
pkgrel=1
pkgdesc='A universal code formatter for JupyterLab.'
arch=(any)
url=https://pypi.org/project/${pkgname}
license=(MIT)
depends=(python jupyterlab)
makedepends=(python-build python-installer python-wheel python-hatchling python-hatch-nodejs-version python-hatch-jupyter-builder)
optdepends=(autopep8 yapf python-isort python-black)
source=(https://files.pythonhosted.org/packages/source/${_name::1}/$_name/$_name-$pkgver.tar.gz)
sha256sums=('85322819da61f025ebc7c4a842979994fa812ad44c334fdb6ebb9ebad58dae08')

build() {
    cd "$_name-$pkgver"
    python -m build --wheel --no-isolation
}

package() {
  cd "$_name-$pkgver"
  python -m installer --destdir="$pkgdir" dist/*.whl

  install -Dm644 LICENSE -t "$pkgdir"/usr/share/licenses/$pkgname
}
