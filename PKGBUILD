# Maintainer: Chrysostomus <forum.manjaro.org>
# Developer: pheiduck <forum.manjaro.org>
# Contributor: Roman Perepelitsa <roman.perepelitsa@gmail.com>

pkgname=manjaro-zsh-config
pkgver=0.21
pkgrel=3
pkgdesc="Zsh configuration for manjaro"
arch=(any)
url="https://github.com/Chrysostomus/manjaro-zsh-config"
_gitcommit=b6990f0b78d7610c84f494395fc7889f9f8a1e34
license=('MIT')
conflicts=('grml-zsh-config')
depends=('zsh-autosuggestions'
	'zsh-syntax-highlighting'
	'zsh-completions'
	'zsh-history-substring-search'
	'zsh'
	'pkgfile'
	'nerd-fonts-noto-sans-mono'
	'zsh-theme-powerlevel10k')
backup=(root/.zshrc)
install="$pkgname.install"
source=("$pkgname-$_gitcommit.tar.gz::$url/archive/$_gitcommit.tar.gz"
        'https://github.com/Chrysostomus/manjaro-zsh-config/pull/31.patch')
sha256sums=('c58cd6d9fb2a2b9a2cd51661129d824ed583d78915785481e765149d40db60bb'
            'eaed56356bbe4d58db2c4cadc353616e256268e60c86d3abbba112bc6c6e315f')

prepare() {
  cd "$pkgname-$_gitcommit"
  patch -Np1 -i ../31.patch
}

package() {
	cd "$pkgname-$_gitcommit"
	install -D -m644 .zshrc -t "${pkgdir}/etc/skel/"
	install -D -m644 "$pkgname" -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 manjaro-zsh-prompt -t "${pkgdir}/usr/share/zsh"
	install -D -m644 zsh-maia-prompt -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 p10k.zsh -t "${pkgdir}/usr/share/zsh/p10k.zsh"
	install -D -m644 command-not-found.zsh -t "${pkgdir}/usr/share/zsh/functions/"
	install -D -m640 rootzshrc -t ${pkgdir}/root/.zshrc
	chmod 750 "${pkgdir}/root"
	install -d "$pkgdir/usr/share/zsh/scripts"
	cp -r base16-shell "$pkgdir/usr/share/zsh/scripts/"
	chmod a+x "$pkgdir/usr/share/zsh/scripts/base16-shell/"*
}
