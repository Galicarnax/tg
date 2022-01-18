pkgname=telegram-tg-galicarnax
pkgver=0.17.0.r37.77dc9cd
pkgrel=5
pkgdesc="terminal telegram client that really works"
arch=(any)
url="https://github.com/paul-nameless/tg"
license=('Unlicense')
depends=('python-telegram=0.15.0' 'python3' 'python-setuptools')
makedepends=('git' 'python-setuptools')
optdepends=(
	'libnotify: for notifications, you could also use other programs: see config'
	'ffmpeg: to record voice msgs and upload videos correctly'
	'urlview: to choose urls when there is multiple in message, use URL_VIEW in config file to use another app, it should accept urls in stdin'
	'ranger: can be used to choose file when sending, customizable with FILE_PICKER_CMD'
	'nnn: can be used to choose file when sending, customizable with FILE_PICKER_CMD'
	'fzf: to create groups and secret chats, used for single and multiple user selection'
)
provides=("telegram-tg" "telegram-tg-git")
conflicts=("telegram-tg" "telegram-tg-git")
source=()
md5sums=('SKIP')

pkgver() {
	# cd "$srcdir/$_pkgname"
    cd "$startdir"
	printf "%s" "$(git describe --long --tags | sed 's/\([^-]*-\)g/r\1/;s/-/./g;s/\(v\)\(.*\)/\2/')"
}

build() {
	# cd "$srcdir/$_pkgname"
    cd "$startdir"
	python3 setup.py build
}

package() {
	# cd "$srcdir/$_pkgname"
    cd "$startdir"
	python3 setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
