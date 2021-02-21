# Maintainer: Rebecca Klauser (schmocker.roman at gmail)

pkgname=brother-hll5100dn
pkgver=3.5.1
pkgrel=1
pkgdesc="Brother HL-L5100DN CUPS driver"
arch=('i686' 'x86_64')
url="http://www.brother.com"
license=('custom')
arch=('i686' 'x86_64')
depends=('cups' 'ghostscript')
#depends_x86_64=('lib32-glibc')

source=(
	"https://download.brother.com/welcome/dlf102552/hll5100dncupswrapper-$pkgver-$pkgrel.i386.rpm"
	"https://download.brother.com/welcome/dlf102551/hll5100dnlpr-$pkgver-$pkgrel.i386.rpm"
)
sha512sums=(
	'0ac79e5b6384c775ff491e891061a36c06fd5677bb7e4f4eff44038abe70a3abf11f157d605e83ba74b4a38c4f935f9f1308012c3c97a283d969143f4ae96176'
       	'077ea2aacbc46e1363b81c3545586f3e32a8eb348d4c199cfc2e9e7a15b9218f03711d87900a3f28ce2432bc45f5830d9679addc9afcde75a88f526044cd629a')

package(){
  cp -R "$srcdir/opt" "$pkgdir/opt"
  ln -s "/opt/brother/Printers/HLL5100DN/lpd/$CARCH/rawtobr3" "$pkgdir/opt/brother/Printers/HLL5100DN/lpd/rawtobr3"
  ln -s "/opt/brother/Printers/HLL5100DN/lpd/$CARCH/brprintconflsr3" "$pkgdir/opt/brother/Printers/HLL5100DN/lpd/brprintconflsr3"
    
  install -d "$pkgdir/usr/lib/cups/filter/"
  ln -s "/opt/brother/Printers/HLL5100DN/cupswrapper/lpdwrapper" "$pkgdir/usr/lib/cups/filter/brother_lpdwrapper_HLL5100DN"

  install -d "$pkgdir/usr/share/cups/model/"
  ln -s "/opt/brother/Printers/HLL5100DN/cupswrapper/brother-HLL5100DN-cups-en.ppd" "$pkgdir/usr/share/cups/model"
  
  install -Dm644 "$srcdir/opt/brother/Printers/HLL5100DN/cupswrapper/Copying" "$pkgdir/usr/share/licenses/$pkgname/LICENSE.txt"
}
