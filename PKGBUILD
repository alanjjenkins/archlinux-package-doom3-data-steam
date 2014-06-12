# Maintainer: Alan Jenkins <alan.james.jenkins [at] gmail.com>
pkgname=doom3-data-steam
pkgver=1
pkgrel=1
pkgdesc="Doom 3 data via Steam"
arch=('any')
provides=('doom3-data')
depends=('steamcmd')
license=('GPL')
install='doom3-data-steam.install'
url='http://store.steampowered.com/app/9050'

package() {
    cd $srcdir
    doom3dir=$srcdir/doom3

    # Use steamcmd to get quake3.
    mkdir -p $doom3dir
    printf "Enter your Steam username:"
    read steam_username
    steamcmd +@sSteamCmdForcePlatformType windows +@ShutdownOnFailedCommand 1 +force_install_dir $doom3dir +login $steam_username "+app_update 9050 validate" +quit

    # Move required files to pkgdir
    # install -D -m 644 $srcdir/quake3/baseq3/pak0.pk3 $pkgdir/opt/quake3/baseq3/pak0.pk3
}

