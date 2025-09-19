pkgname=file
pkgver=5.46
pkgrel=2
pkgdesc="File type identification utility"
arch=('x86_64')
url="https://www.darwinsys.com/file/"
license=(
    'BSD-2-Clause-Darwin'
    'BSD-2-Clause'
)
groups=('base' 'base-devel')
depends=(
    'bzip2'
    'glibc'
    'xz'
    'zlib'
    'zstd'
)
options=('!emptydirs')
source=(https://astron.com/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(c9cc77c7c560c543135edc555af609d5619dbef011997e988ce40a3d75d86088)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        ${configure_options}
    )

    CFLAGS+=" -pthread"

    ./configure ${configure_args[@]}

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
