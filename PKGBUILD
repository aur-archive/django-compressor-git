# Maintainer: Benjamin A. Shelton <zancarius at gmail _ com>
# Source: https://github.com/zancarius/archlinux-pkgbuilds

pkgname=django-compressor-git
pkgver=20130314
pkgrel=1
pkgdesc="Compresses linked and inline JavaScript or CSS into a single cached file."
arch=(any)
url="https://github.com/jezdez/django_compressor"
license=(MIT)
depends=(python2 python2-django)
makedepends=(git python2-distribute)

_gitver=1.2
_gitroot="https://github.com/jezdez/django_compressor.git"
_gitname="django_compressor"

build() {

    cd "${srcdir}"

    if [ -d "${_gitname}/.git" ] ; then
        msg "Updating git repository..."
        (cd "${_gitname}" && git checkout develop && git pull)
    else
        msg "Cloning git repository..."
        git clone ${_gitroot} ${_gitname}
    fi

    (cd "${_gitname}" && git checkout "${_gitver}")

    cp -a "${_gitname}" "${_gitname}-work"

    cd "${_gitname}-work"

    python2 setup.py install --root="${pkgdir}/"
                                                                

}