# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=hybris-quirks
pkgver=2
pkgrel=3
pkgdesc="hybris quirks"
arch=('any')
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
        'gnome-session-unfailed.service'
        'zz-manjaro.sh'
        'zz-wayland.sh'
        'gnome-session-not-failed'
        'machine-info'
        '90_manjaro.gschema.override')
sha256sums=('a3a50eb7edad196a75888ee14c0a6968cb8bcbffe70a3a21c321b0b22a1418b9'
            '02f5bb2686f306df7ad2bb9cda99b0925c3e8c4e9d55691e228dc48bf0ab3eb8'
            'facd370b53d8f963e2bc9c63a137c20fc4132eb239f7d2776dc989823d1726a3'
            'f29a7b3242eee7050eafc4f382806a28dcac7c75d17f8f368f5bd1dc43e32183'
            'aa1134b2ff07dd5af70a33cfdbdb16fd8e544a611a4e4c76807875b07f2e57a9'
            'fe14145d55572b232ba735e412824b181e6db96e72c71023c5cdea4308f5aaa9'
            '493d9ca491099b50577d1bc0a1c3cf3d8e7841b603f6ecb282a69c6d0e7797ec'
            '2c82e335e91fb2bd158e99c4abc4df6541057bff35a67bec23450827cd62e29c'
            '241dc6ecce72aaf448494998f98b23620d0b0cefd6dadf6d41658cfed131c667'
            '6e61d44eaa0357f5297b8331ba77e3f05da755274f894d40ab60c58ba7a88b1b'
            '3a75a56b983e6af8b83b1b29a2f48e714e41f290ebb7e07b9fb7619a34663525'
            '22ea73e9fdb56ca473d7f8c33248c30bbf0954378c5190cacd70d34fb179d708'
            'd147c7f34bf22c96b4ae12127885559ac4c52f70e9e632e0eb8b963eb2b32d95'
            '6d79a6fb74c705e25fb98f46c5a47e5be917a74fe199f578ac222c157a9aef33')

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
  install -m644 gnome-session-unfailed.service "$pkgdir"/usr/lib/systemd/system

  mkdir -p ${pkgdir}/etc/profile.d/
  install -m755 zz-manjaro.sh "$pkgdir"/etc/profile.d
  install -m755 zz-wayland.sh "$pkgdir"/etc/profile.d

  install -m644 machine-info "$pkgdir"/etc/

  mkdir -p ${pkgdir}/usr/lib/
  install -m755 gnome-session-not-failed "$pkgdir"/usr/lib/

  mkdir -p ${pkgdir}/usr/share/glib-2.0/schemas/
  install -m644 90_manjaro.gschema.override -t "$pkgdir"/usr/share/glib-2.0/schemas/
}
