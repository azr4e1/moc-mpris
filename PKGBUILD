pkgname=moc-mpris-git
pkgver=r17.5104279
pkgrel=1
pkgdesc="MPRIS2 bridge for MOC (Music on Console)"
arch=('any')
url="https://github.com/azr4e1/moc-mpris"
license=('GPL3')
depends=(
    'python'
    'python-dbus'
    'python-gobject'
    'python-musicbrainzngs'
    'moc'
    'alsa-utils'
)
makedepends=('git')
source=("${pkgname}::git+${url}.git")
sha256sums=('SKIP')

pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "$pkgname"

    install -Dm755 moc_mpris.py "$pkgdir/usr/lib/moc-mpris/moc_mpris.py"
    install -Dm755 moc_mpris.sh "$pkgdir/usr/lib/moc-mpris/moc_mpris.sh"
    install -Dm644 moc_mpris.service "$pkgdir/usr/lib/systemd/user/moc_mpris.service"
    install -Dm644 moc_mpris@.service "$pkgdir/usr/lib/systemd/user/moc_mpris@.service"
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
