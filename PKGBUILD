# Maintainer: Ke Liu <spcter119@gmail.com>

pkgname=python-asciimatics
_name=${pkgname//python-}
pkgver=1.11.0
pkgrel=2
pkgdesc='A cross platform package to do curses-like operations, plus higher level APIs and widgets to create text UIs and ASCII art animations.'
arch=('any')
url='https://pypi.org/project/asciimatics'
license=('Apache2')
depends=('python-wcwidth' 'python-mock' 'python-pyfiglet' 'python-future' 'python-setuptools-scm' 'python-pillow')
source=("https://files.pythonhosted.org/packages/source/a/${_name}/${_name}-${pkgver}.tar.gz")
md5sums=('9abc134166e6a83671b379dc03830a3f')

build() {
	cd "$srcdir/${_name}-$pkgver"
	python setup.py clean --all
	python setup.py build
}

package() {
	cd "$srcdir/${_name}-$pkgver"
	python setup.py install --root "$pkgdir" --skip-build --optimize=1
	install -Dm644 "$srcdir/${_name}-${pkgver}/LICENSE" "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
}
