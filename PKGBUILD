pkgname=warpcast
pkgver=1.0
pkgrel=1
pkgdesc="Shortcut for warpcast.com with Google Chrome"
arch=('x86_64')
url="https://warpcast.com"
license=('MIT')           # Assuming a common open-source license for simplicity
depends=('google-chrome') # Google Chrome must be installed
makedepends=('wget')      # wget for downloading the icon
optdepends=()             # Optional dependencies can be added here if needed in the future
source=("warpcast-icon.png::https://www.google.com/s2/favicons?domain=warpcast.com&sz=256")
sha256sums=('SKIP') # It's recommended to replace 'SKIP' with the actual SHA-256 sum

package() {
	# Create the necessary directories
	install -dm755 "${pkgdir}/usr/share/applications"
	install -dm755 "${pkgdir}/usr/share/icons/hicolor/256x256/apps/"

	# Install the icon
	install -Dm644 "${srcdir}/warpcast-icon.png" "${pkgdir}/usr/share/icons/hicolor/256x256/apps/warpcast.png"

	# Create the desktop entry
	echo "[Desktop Entry]
Type=Application
Name=Warpcast
Exec=google-chrome-stable --app=https://warpcast.com
Icon=warpcast
Comment=Access Warpcast with Google Chrome
Categories=Network;WebBrowser;" >"${pkgdir}/usr/share/applications/warpcast.desktop"
}
