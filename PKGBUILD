# Maintainer: Chrysostomus <forum.manjaro.org>
# Developer: pheiduck <forum.manjaro.org>
# Contributor: Roman Perepelitsa <roman.perepelitsa@gmail.com>

pkgname=manjaro-zsh-config
pkgver=0.21
pkgrel=3
pkgdesc="Zsh configuration for manjaro"
arch=(any)
url="https://github.com/Chrysostomus/manjaro-zsh-config"
_gitcommit=08a33dc2f692462862d32c48931a28426e1ffc2a
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
source=("$pkgname-$_gitcommit.tar.gz::$url/archive/$_gitcommit.tar.gz")
sha256sums=('f5dc55f217503e55d0ffa45861171c562f7f67e3307398b78d1c7a2e05cd581a')

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
