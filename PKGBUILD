# Maintainer: Chrysostomus @forum.manjaro.org
# Developer: pheiduck @forum.manjaro.org

pkgname=manjaro-zsh-config
pkgver=0.21
pkgrel=1
pkgdesc="Zsh configuration for manjaro"
arch=(any)
url="https://github.com/Chrysostomus/$pkgname"
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
source=("$pkgname.tar.gz::$url/archive/$_gitcommit.tar.gz")
install=manjaro-zsh-config.install
sha256sums=('f459dc20c0b823268793be7501c4e06273d402cebe1cbf8e1f444f8e1827ee48')
backup=(root/.zshrc)

package() {
	cd ${srcdir}
	install -D -m644 $srcdir/$pkgname-$_gitcommit/.zshrc ${pkgdir}/etc/skel/.zshrc
	install -D -m644 $srcdir/$pkgname-$_gitcommit/manjaro-zsh-config ${pkgdir}/usr/share/zsh/manjaro-zsh-config
	install -D -m644 $srcdir/$pkgname-$_gitcommit/manjaro-zsh-prompt ${pkgdir}/usr/share/zsh/manjaro-zsh-prompt
	install -D -m644 $srcdir/$pkgname-$_gitcommit/zsh-maia-prompt ${pkgdir}/usr/share/zsh/zsh-maia-prompt
	install -D -m644 $srcdir/$pkgname-$_gitcommit/p10k.zsh ${pkgdir}/usr/share/zsh/p10k.zsh
	install -D -m644 $srcdir/$pkgname-$_gitcommit/command-not-found.zsh ${pkgdir}/usr/share/zsh/functions/command-not-found.zsh
	install -D -m640 $srcdir/$pkgname-$_gitcommit/rootzshrc ${pkgdir}/root/.zshrc
	chmod 750 ${pkgdir}/root
	mkdir -p $pkgdir/usr/share/zsh/scripts
	cp -r $srcdir/$pkgname-$_gitcommit/base16-shell $pkgdir/usr/share/zsh/scripts
	chmod a+x $pkgdir/usr/share/zsh/scripts/base16-shell/*
}
