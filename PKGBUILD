# Contributor: Chris Baker <baker.chris.3@gmail.com>
# Contributor: Reventlov <contact+aur@volcanis.me>
# Maintainer: Martin Herndl <martin.herndl@gmail.com>
pkgname=checkgmail-svn
pkgver=r72
pkgrel=1
pkgdesc="An alternative Gmail Notifier for Linux and other *nix systems - fixed version"
arch=('any')
url="https://github.com/monojp/checkgmail"
license=('GPL2')
depends=('perl-gtk2-trayicon' 'perl-lwp-protocol-https' 'perl-xml-simple' 'perl-freezethaw' 'perl-crypt-simple' 'perl-crypt-blowfish')
makedepends=('subversion')
conflicts=('checkgmail')
provides=('checkgmail')
source=('svn+https://github.com/monojp/checkgmail/trunk'
        'checkgmail.desktop')
sha256sums=('SKIP'
            '12d3c3cc066e97b7dd07b0674646b9a291919e451df4c956023630721cb52f95')

pkgver() {
    cd "trunk"
    local ver="$(svnversion)"
    printf "r%s" "${ver//[[:alpha:]]}"
}

package() {
    cd "$srcdir/trunk"

    install -D -m 755 checkgmail ${pkgdir}/usr/bin/checkgmail
    install -D -m 644 man/checkgmail.1.gz \
        ${pkgdir}/usr/share/man/man1/checkgmail.1.gz

    # freedesktop
    install -D -m 644 ${srcdir}/checkgmail.desktop \
        ${pkgdir}/usr/share/applications/checkgmail.desktop
    install -D -m 644 checkgmail.png \
        ${pkgdir}/usr/share/pixmaps/checkgmail.png
}
