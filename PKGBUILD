# Maintainer: Dmitry Lavnikevich <haff at midgard dot by>
pkgname=unpack-git
pkgver=20140420
pkgrel=0
pkgdesc="Unified utility for unpacking"
arch=('any')
url="https://github.com/githaff/unpack"
license=('BSD')
depends=('bash')
makedepends=('git')
optdepends=('tar: tar archives support'
            'unrar: rar archives support'
            'unzip: zip archives support'
            'p7zip: 7z archives support'
            'lzop: lzo archives support'
            'rpm2cpio: rpm packages support')

_gitroot="git://github.com/githaff/unpack.git"
_gitname="unpack"


build() {
  msg "Connecting to GIT server..."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi
  msg "GIT checkout done or server timeout"
}

package() {
# script
  install -D -m755 "${_gitname}/unpack" "${pkgdir}/usr/bin/unpack"

# documentation
  install -D -m644 "${_gitname}/README" "${pkgdir}/usr/share/doc/${_gitname}/README" 

# license
  install -D -m644 "${_gitname}/LICENSE" "${pkgdir}/usr/share/licenses/${_gitname}/LICENSE"
}
