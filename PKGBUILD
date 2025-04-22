# Maintainer: Aspen Schneider <rendezvous71@outlook.com>

pkgname='laniakea-dotnet-runtime'
pkgdesc='Laniakea runtime for .NET'
_pkgver=0.1.0
_dotnetmajor=9
_sdkminor=105
pkgver="${_pkgver}.sdk${_sdkminor}"
pkgrel=1
url='https://www.laniakeaos.com/'
arch=('any')
license=('MIT')
makedepends=(
  dotnet-sdk
)
depends=(
  dotnet-runtime
)

validpgpkeys=(
  '425529067DE156F86814B55D2AE736768A7E87E6'
)

source=(
  "git+https://github.com/laniakeaos/Laniakea.NET.git#tag=v${_pkgver}"
)
b2sums=(
  'SKIP'
)


build() {
  echo "build..."
  cd $srcdir/Laniakea.NET
  make
  make runtime
}

package() {
  cd $srcdir/Laniakea.NET
  make DESTDIR=$pkgdir install-runtime
}
