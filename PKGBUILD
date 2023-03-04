# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=hybris-quirks
pkgver=1
pkgrel=2
pkgdesc="hybris quirks"
arch=('aarch64')
url="https://github.com/manjaro-libhybris/hybris-quirks"
license=('BSD-3')
depends=('systemd' 'bash')
source=('boot-wlan.sh'
        'ipa-enable.sh'
        'lmk-disable.sh'
        'wcnss-enable.sh'
        'boot-wlan.service'
        'ipa-enable.service'
        'lmk-disable.service'
        'wcnss-enable.service'
        'zz-manjaro.sh'
        'zz-wayland.sh'
        '20-qt-force-gles'
        'machine-info')
sha256sums=('a3a50eb7edad196a75888ee14c0a6968cb8bcbffe70a3a21c321b0b22a1418b9'
            '02f5bb2686f306df7ad2bb9cda99b0925c3e8c4e9d55691e228dc48bf0ab3eb8'
            'facd370b53d8f963e2bc9c63a137c20fc4132eb239f7d2776dc989823d1726a3'
            'f29a7b3242eee7050eafc4f382806a28dcac7c75d17f8f368f5bd1dc43e32183'
            'aa1134b2ff07dd5af70a33cfdbdb16fd8e544a611a4e4c76807875b07f2e57a9'
            'fe14145d55572b232ba735e412824b181e6db96e72c71023c5cdea4308f5aaa9'
            '493d9ca491099b50577d1bc0a1c3cf3d8e7841b603f6ecb282a69c6d0e7797ec'
            '2c82e335e91fb2bd158e99c4abc4df6541057bff35a67bec23450827cd62e29c'
            'efee70f8e58f115420eca8b97d6a755610c0b03165da13170062c60aa51b7b98'
            '3a75a56b983e6af8b83b1b29a2f48e714e41f290ebb7e07b9fb7619a34663525'
            '35ab3dd336887538c8a20b7ba30995db24bf63f562744443d9fa8cb9d3ecce60'
            'd147c7f34bf22c96b4ae12127885559ac4c52f70e9e632e0eb8b963eb2b32d95')

package() {
  mkdir -p ${pkgdir}/usr/bin/
  cd ..
  install -m755 boot-wlan.sh "$pkgdir"/usr/bin
  install -m755 ipa-enable.sh "$pkgdir"/usr/bin
  install -m755 lmk-disable.sh "$pkgdir"/usr/bin
  install -m755 wcnss-enable.sh "$pkgdir"/usr/bin

  mkdir -p ${pkgdir}/usr/lib/systemd/system/
  install -m644 boot-wlan.service "$pkgdir"/usr/lib/systemd/system
  install -m644 ipa-enable.service "$pkgdir"/usr/lib/systemd/system
  install -m644 lmk-disable.service "$pkgdir"/usr/lib/systemd/system
  install -m644 wcnss-enable.service "$pkgdir"/usr/lib/systemd/system

  mkdir -p ${pkgdir}/etc/profile.d/
  install -m755 zz-manjaro.sh "$pkgdir"/etc/profile.d
  install -m755 zz-wayland.sh "$pkgdir"/etc/profile.d
  install -m755 20-qt-force-gles "$pkgdir"/etc/profile.d

  install -m644 machine-info "$pkgdir"/etc/
}
