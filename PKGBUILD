# Maintainer: senselessDev <mikrocontroller@arcor.de>
pkgname=airPi
pkgver=0.1
pkgrel=1
epoch=
pkgdesc=""
arch=(armv6h)
url=""
license=('unknown')
groups=()
depends=('base-devel' 'nginx' 'php-fpm' 'gstreamer' 'gst-plugins-good' 'gst-plugins-bad' 'avahi' 'nss-mdns')
makedepends=('nginx' 'php-fpm' 'gstreamer' 'gst-plugins-good' 'gst-plugins-bad' 'avahi' 'nss-mdns')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=airPi.install
changelog=
source=()
noextract=()
md5sums=() #generate with 'makepkg -g'

package() {
	#avahi configuration
	install -D -m644 "$srcdir/airPi.service" "$pkgdir/etc/avahi/services/airPi.service";

	#systemctl configuration
	install -D -m644 "$srcdir/50-airPi.preset" "$pkgdir/usr/lib/systemd/system-preset/50-airPi.preset";	

	#webinterface php files
	mkdir -p "$pkgdir/usr/share/nginx/html/";
	cp -rp "$srcdir/www-data/" "$pkgdir/usr/share/nginx/html/";  
	
	#nginx configuration
	install -D -m644 "$srcdir/nginx.conf" "$pkgdir/etc/nginx/nginx.conf.hidden";
}	
