# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-game-libretro-parallel-n64
pkgver=2.0.0.4
_codename=Leia
pkgrel=1
pkgdesc="Libretro wrapper for Kodi's Game API"
arch=('x86_64')
url='https://github.com/kodi-game/game.libretro.parallel_n64'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-game')
depends=('kodi-addon-game-libretro' 'libretro-parallel-n64')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/kodi-game/game.libretro.parallel_n64/archive/$pkgver-$_codename.tar.gz")
sha512sums=('d6b9fcc28e2c930af8fcca550abe013917b8eeda01372106830224476ada7454d4f7aa75cd0daf8c81b3db320ad676e8b42fa3baa40a712edac12ca1cec8038d')

build() {
    cd "game.libretro.parallel_n64-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "game.libretro.parallel_n64-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

