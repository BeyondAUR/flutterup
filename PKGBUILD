pkgname=flutterup
pkgver=0.2.5
pkgrel=1.0
pkgdesc='A flutter wrapper, to install and package flutter packages'
arch=('x86_64' 'aarch64')
url='https://github.com/Decodetalkers/flutterup'
license=('MIT')
provides=('flutter' 'dart')
conflicts=('flutter' 'dart')
depends=('git')
makedepends=('rust')
source=("flutterup-v${pkgver}.tar.gz::https://github.com/BeyondAUR-Upstream/flutterup/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('bfe6a8757b7cb12482df09a4040a0bf4fe40d4cece0b182cb7a3fdf3120e02ae')

build() {
  cd ${pkgname}-$pkgver
  cargo build --release
}

package() {
  cd ${pkgname}-$pkgver
  install -Dm0755 -t "${pkgdir}/usr/bin/" "target/release/${pkgname}"
  install -D -m644 LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}/"

  ln -sr "${pkgdir}/usr/bin/dart" ${pkgname}
  ln -sr "${pkgdir}/usr/bin/flutter" ${pkgname}
}
