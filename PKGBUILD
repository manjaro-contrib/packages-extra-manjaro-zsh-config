# Maintainer: Chrysostomus <forum.manjaro.org>
# Contributor: pheiduck <forum.manjaro.org>
# Contributor: Roman Perepelitsa <roman.perepelitsa@gmail.com>

pkgname=manjaro-zsh-config
pkgver=0.25
pkgrel=3
pkgdesc="Zsh configuration for manjaro"
arch=('any')
url="https://github.com/Chrysostomus/manjaro-zsh-config"
license=('MIT')
depends=('zsh-autosuggestions'
  'zsh-syntax-highlighting'
  'zsh-completions'
  'zsh-history-substring-search'
  'zsh'
  'pkgfile'
  'ttf-meslo-nerd-font-powerlevel10k'
  'zsh-theme-powerlevel10k')
makedepends=('git')
conflicts=('grml-zsh-config')
backup=('root/.zshrc')
install="$pkgname.install"
_commit=a09dbc3f6bf22d553def64247b3529d9310c7b1f
source=("git+${url}.git#commit=${_commit}"
        "${url}/pull/42.patch")
sha256sums=('SKIP'
            'f9b220ce31676c35ac403cdd8b7d5f2e21545355dd30138bccb4c1e8ee178e20')

prepare() {
  cd "$srcdir/$pkgname"
  patch -Np1 -i ../42.patch
}

package() {
  cd "$srcdir/$pkgname"
  install -D -m644 .zshrc -t "${pkgdir}/etc/skel/"
  install -D -m644 "$pkgname" -t "${pkgdir}/usr/share/zsh/"
  install -D -m644 manjaro-zsh-prompt -t "${pkgdir}/usr/share/zsh"
  install -D -m644 zsh-maia-prompt -t "${pkgdir}/usr/share/zsh/"
  install -D -m644 p10k.zsh -t "${pkgdir}/usr/share/zsh/"
  install -D -m644 p10k-portable.zsh -t "${pkgdir}/usr/share/zsh/"
  install -D -m644 command-not-found.zsh -t "${pkgdir}/usr/share/zsh/functions/"
  install -D -m640 .zshrc -t "${pkgdir}/root/"
  chmod 750 "${pkgdir}/root"
  install -d "${pkgdir}/usr/share/zsh/scripts"
  cp -r base16-shell "${pkgdir}/usr/share/zsh/scripts/"
  chmod a+x "${pkgdir}/usr/share/zsh/scripts/base16-shell/"*
  install -D -m644 LICENSE -t "${pkgdir}/usr/share/licenses/$pkgname/"
}
