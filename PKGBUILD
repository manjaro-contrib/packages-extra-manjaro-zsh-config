# Maintainer: Chrysostomus <forum.manjaro.org>
# Developer: pheiduck <forum.manjaro.org>
# Contributor: Roman Perepelitsa <roman.perepelitsa@gmail.com>

pkgname=manjaro-zsh-config
pkgver=0.21
pkgrel=2
pkgdesc="Zsh configuration for manjaro"
arch=(any)
url="https://github.com/Chrysostomus/manjaro-zsh-config"
_gitcommit=7253e5e6d3bb41fc75983603198a509dff39b004
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
source=("$pkgname.tar.gz::$url/archive/$_gitcommit.tar.gz"
        'https://github.com/Chrysostomus/manjaro-zsh-config/pull/30.patch')
sha256sums=('f459dc20c0b823268793be7501c4e06273d402cebe1cbf8e1f444f8e1827ee48'
            'b7a775d368b4d850fc0b1c666681c9f1466d577f688a3bc92063f4dbe9ba1597')

prepare() {
	cd "$pkgname-$_gitcommit"

	# Improve prompt
	patch -Np1 -i ../30.patch
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
