# Maintainer: senselessDev <mikrocontroller@arcor.de>
pkgname=airpi
pkgver=0.1
pkgrel=2
pkgdesc=""
arch=(armv6h)
license=('unknown')
groups=()
depends=('base-devel' 'nginx' 'php-fpm' 'gstreamer' 'gst-plugins-good' 'gst-plugins-bad' 'avahi' 'nss-mdns')
install=airPi.install

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
