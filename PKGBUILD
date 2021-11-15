# Maintainer: Chrysostomus <forum.manjaro.org>
# Developer: pheiduck <forum.manjaro.org>
# Contributor: Roman Perepelitsa <roman.perepelitsa@gmail.com>

pkgname=manjaro-zsh-config
pkgver=0.22
pkgrel=2
pkgdesc="Zsh configuration for manjaro"
arch=(any)
url="https://github.com/Chrysostomus/manjaro-zsh-config"
_gitcommit=737fba1290f15e8092b2c92dc78698d82a35c398
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
sha256sums=('5e9ecd772cb73d34c2eb798db7007f1f63bdfb7c7c9a99022b735b46ac1adbcc')

package() {
	cd "$pkgname-$_gitcommit"
	install -D -m644 .zshrc -t "${pkgdir}/etc/skel/"
	install -D -m644 "$pkgname" -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 manjaro-zsh-prompt -t "${pkgdir}/usr/share/zsh"
	install -D -m644 zsh-maia-prompt -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 p10k.zsh -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 p10k-portable.zsh -t "${pkgdir}/usr/share/zsh/"
	install -D -m644 command-not-found.zsh -t "${pkgdir}/usr/share/zsh/functions/"
	install -D -m640 .zshrc -t "${pkgdir}/root/"
	chmod 750 "${pkgdir}/root"
	install -d "$pkgdir/usr/share/zsh/scripts"
	cp -r base16-shell "$pkgdir/usr/share/zsh/scripts/"
	chmod a+x "$pkgdir/usr/share/zsh/scripts/base16-shell/"*
}
