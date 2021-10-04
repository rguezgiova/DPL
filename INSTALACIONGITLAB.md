## **Instalación de GitLab en linux**

### **Índice**
[Actualización de repositorios](#id1)<br>
[Instalación de paquetes adicionales](#id2)<br>
[Instalación de GitLab](#id3)
[Acceso](#id4)


### **Actualización de repositorios**<a name = "id1"></a>
Lo primero que haremos será actualizar los repositorios del sistema operativo.

```bash
daw@DLP17-Lubuntu18:~$   sudo apt update && sudo apt upgrade
[sudo] contraseña para daw:
Obj:1 http://security.ubuntu.com/ubuntu bionic-security InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Obj:3 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease
Obj:4 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease
Leyendo lista de paquetes... Hecho                     
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se pueden actualizar 543 paquetes. Ejecute «apt list --upgradable» para verlos.
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Calculando la actualización... Hecho
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes NUEVOS:
  amd64-microcode bubblewrap distro-info fwupd-signed intel-microcode iucode-tool libbrotli1
  libllvm10 libnetplan0 libwayland-egl1 libwoff1 libxmlb1 linux-headers-4.15.0-159
  linux-headers-4.15.0-159-generic linux-image-4.15.0-159-generic
  linux-modules-4.15.0-159-generic linux-modules-extra-4.15.0-159-generic python3-asn1crypto
  python3-cffi-backend python3-click python3-colorama python3-crypto python3-cryptography
  python3-dateutil python3-keyring python3-keyrings.alt python3-launchpadlib
  python3-lazr.restfulclient python3-lazr.uri python3-netifaces python3-oauth
  python3-secretstorage python3-simplejson python3-wadllib python3-zope.interface
Se actualizarán los siguientes paquetes:
  accountsservice apparmor apport apport-gtk appstream apt apt-config-icons apt-utils
  aptdaemon aptdaemon-data aspell avahi-daemon base-files bash bind9-host blueman bluez
  bluez-obexd bsdutils busybox-initramfs busybox-static bzip2 ca-certificates
  command-not-found command-not-found-data console-setup console-setup-linux cpio cups
  cups-bsd cups-client cups-common cups-core-drivers cups-daemon cups-filters
  cups-filters-core-drivers cups-ipp-utils cups-ppdc cups-server-common dbus dbus-x11 debconf
  debconf-i18n desktop-file-utils dirmngr distro-info-data dmidecode dmsetup dnsutils dpkg
  e2fsprogs evince evince-common evolution-data-server-common fdisk file file-roller
  fonts-beng-extra fonts-deva-extra fonts-gujr-extra fonts-guru-extra fonts-liberation
  fonts-noto-cjk fonts-noto-color-emoji fonts-orya-extra friendly-recovery fwupd fwupdate
  fwupdate-signed gettext-base ghostscript ghostscript-x gir1.2-appindicator3-0.1
  gir1.2-dbusmenu-glib-0.4 gir1.2-goa-1.0 gir1.2-gtk-3.0 gir1.2-javascriptcoregtk-4.0
  gir1.2-packagekitglib-1.0 gir1.2-pango-1.0 gir1.2-polkit-1.0 gir1.2-snapd-1 gir1.2-soup-2.4
  gir1.2-udisks-2.0 gir1.2-vte-2.91 gir1.2-webkit2-4.0 glib-networking glib-networking-common
  glib-networking-services gnome-desktop3-data gnome-disk-utility gnome-keyring gnome-software
  gnome-software-common gnupg gnupg-l10n gnupg-utils gpg gpg-agent gpg-wks-client
  gpg-wks-server gpgconf gpgsm gpgv grep gstreamer1.0-plugins-bad gstreamer1.0-plugins-base
  gstreamer1.0-plugins-good gvfs gvfs-backends gvfs-common gvfs-daemons gvfs-fuse gvfs-libs
  gzip im-config indicator-application initramfs-tools initramfs-tools-bin
  initramfs-tools-core iproute2 iputils-ping iputils-tracepath irqbalance isc-dhcp-client
  isc-dhcp-common keyboard-configuration kmod krb5-locales language-pack-en
  language-pack-en-base language-selector-common language-selector-gnome libaccountsservice0
  libapparmor1 libappindicator1 libappindicator3-1 libappstream4 libapt-inst2.0 libapt-pkg5.0
  libarchive13 libasound2 libasound2-data libaspell15 libaudit-common libaudit1
  libavahi-client3 libavahi-common-data libavahi-common3 libavahi-core7 libavahi-glib1
  libavcodec57 libavdevice57 libavfilter6 libavformat57 libavresample3 libavutil55
  libbind9-160 libblkid1 libbluetooth3 libbsd0 libbz2-1.0 libc-bin libc-dev-bin libc6
  libc6-dev libcaca0 libcairo-gobject2 libcairo2 libcamel-1.2-61 libcogl-pango20
  libcogl-path20 libcogl20 libcom-err2 libcryptsetup12 libcups2 libcupscgi1 libcupsfilters1
  libcupsimage2 libcupsmime1 libcupsppdc1 libdb5.3 libdbus-1-3 libdbusmenu-glib4
  libdbusmenu-gtk3-4 libdbusmenu-gtk4 libdevmapper1.02.1 libdjvulibre-text libdjvulibre21
  libdns-export1100 libdns1100 libdrm-amdgpu1 libdrm-common libdrm-intel1 libdrm-nouveau2
  libdrm-radeon1 libdrm2 libebook-contacts-1.2-2 libedataserver-1.2-23 libegl-mesa0 libegl1
  libegl1-mesa libelf1 libevdev2 libevdocument3-4 libevview3-3 libexif12 libexo-1-0 libexo-2-0
  libexo-common libexo-helpers libext2fs2 libfdisk1 libfontembed1 libfreetype6 libfwup1
  libfwupd2 libgbm1 libgcrypt20 libgd3 libgettextpo0 libgif7 libgl1 libgl1-mesa-dri
  libgl1-mesa-glx libglapi-mesa libglib2.0-0 libglib2.0-bin libglib2.0-data libglvnd0
  libglx-mesa0 libglx0 libgnome-desktop-3-17 libgnutls30 libgoa-1.0-0b libgoa-1.0-common
  libgpgme11 libgs9 libgs9-common libgssapi-krb5-2 libgstreamer-gl1.0-0
  libgstreamer-plugins-bad1.0-0 libgstreamer-plugins-base1.0-0 libgstreamer-plugins-good1.0-0
  libgstreamer1.0-0 libgtk-3-0 libgtk-3-common libhogweed4 libicu60 libidn11 libidn2-0
  libinput-bin libinput10 libio-socket-ssl-perl libirs160 libisc-export169 libisc169
  libisccc160 libisccfg160 libjavascriptcoregtk-4.0-18 libjpeg-turbo8 libjson-c3
  libjson-glib-1.0-0 libjson-glib-1.0-common libk5crypto3 libkmod2 libkpathsea6 libkrb5-3
  libkrb5support0 liblcms2-2 liblcms2-utils libldap-2.4-2 libldap-common libldb1 liblwres160
  liblz4-1 libmagic-mgc libmagic1 libmbim-glib4 libmbim-proxy libmm-glib0 libmount1 libmysofa0
  libnautilus-extension1a libncurses5 libncursesw5 libneon27-gnutls libnet-ssleay-perl
  libnettle6 libnm0 libnma0 libnss-systemd libnss3 libntfs-3g88 libnuma1 libobrender32v5
  libobt2v5 libopenexr22 libopenjp2-7 libp11-kit0 libpackagekit-glib2-18 libpam-modules
  libpam-modules-bin libpam-runtime libpam-systemd libpam0g libpango-1.0-0 libpangocairo-1.0-0
  libpangoft2-1.0-0 libpangoxft-1.0-0 libparted-fs-resize0 libparted2 libpcap0.8 libpci3
  libperl5.26 libplymouth4 libpng16-16 libpolkit-agent-1-0 libpolkit-backend-1-0
  libpolkit-gobject-1-0 libpoppler-glib8 libpoppler73 libpostproc54 libprocps6 libproxy1v5
  libpulse-mainloop-glib0 libpulse0 libpulsedsp libpython2.7 libpython2.7-minimal
  libpython2.7-stdlib libpython3-stdlib libpython3.6 libpython3.6-minimal libpython3.6-stdlib
  libqmi-glib5 libqmi-proxy libqpdf21 libraptor2-0 librsvg2-2 librsvg2-common libsane-common
  libsane1 libsasl2-2 libsasl2-modules libsasl2-modules-db libsdl2-2.0-0 libseccomp2
  libsmartcols1 libsmbclient libsnapd-glib1 libsndfile1 libsnmp-base libsnmp30
  libsoup-gnome2.4-1 libsoup2.4-1 libsqlite3-0 libss2 libssh-gcrypt-4 libssl1.0.0
  libswresample2 libswscale4 libsystemd0 libtiff5 libtinfo5 libudev1 libudisks2-0
  libunistring2 libupower-glib3 libuuid1 libvpx5 libvte-2.91-0 libvte-2.91-common libvulkan1
  libwavpack1 libwayland-client0 libwayland-cursor0 libwayland-egl1-mesa libwayland-server0
  libwbclient0 libwebkit2gtk-4.0-37 libwebp6 libwebpdemux2 libwebpmux3 libwhoopsie0
  libwww-perl libx11-6 libx11-data libx11-xcb1 libxapian30 libxatracker2 libxau6 libxcb-dri2-0
  libxcb-dri3-0 libxcb-glx0 libxcb-present0 libxcb-render0 libxcb-shape0 libxcb-shm0
  libxcb-sync1 libxcb-xfixes0 libxcb1 libxkbcommon0 libxml2 libxslt1.1 libzmq5 libzstd1
  lightdm-gtk-greeter linux-base linux-firmware linux-generic linux-headers-generic
  linux-image-generic linux-libc-dev locales login lshw lubuntu-artwork lubuntu-artwork-18-04
  lubuntu-default-session lubuntu-default-settings lubuntu-desktop lubuntu-gtk-core
  lubuntu-gtk-desktop lubuntu-icon-theme lubuntu-lxpanel-icons man-db modemmanager mount
  multiarch-support ncurses-base ncurses-bin netcat-openbsd netplan.io network-manager
  network-manager-gnome networkd-dispatcher nplan ntfs-3g openbox openssh-client openssl
  p11-kit p11-kit-modules packagekit parted passwd patch pciutils perl perl-base
  perl-modules-5.26 plymouth plymouth-label plymouth-theme-lubuntu-logo
  plymouth-theme-lubuntu-text plymouth-theme-ubuntu-text policykit-1
  policykit-desktop-privileges poppler-utils ppp procps psmisc pulseaudio pulseaudio-utils
  python-apt-common python3 python3-apport python3-apt python3-aptdaemon
  python3-aptdaemon.gtk3widgets python3-commandnotfound python3-debconf python3-distro-info
  python3-distupgrade python3-gdbm python3-gi python3-gi-cairo python3-httplib2
  python3-minimal python3-pil python3-problem-report python3-reportlab python3-reportlab-accel
  python3-requests python3-software-properties python3-update-manager python3-urllib3
  python3.6 python3.6-minimal rfkill rsync samba-libs sbsigntool secureboot-db
  software-properties-common software-properties-gtk sudo sylpheed sylpheed-i18n
  sylpheed-plugins systemd systemd-sysv tar tcpdump tzdata ubuntu-advantage-tools
  ubuntu-drivers-common ubuntu-keyring ubuntu-minimal ubuntu-mono ubuntu-release-upgrader-core
  ubuntu-release-upgrader-gtk ubuntu-report ubuntu-standard udev udisks2 ufw unzip
  update-manager update-manager-core update-notifier update-notifier-common upower ureadahead
  usb-creator-common usb-creator-gtk util-linux uuid-runtime vim-common vim-tiny wget whoopsie
  wireless-regdb wpasupplicant x11-common x11-xkb-utils xdg-utils xkb-data xserver-common
  xserver-xorg-core xserver-xorg-input-all xserver-xorg-video-all xxd
543 actualizados, 35 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
Se necesita descargar 423 MB de archivos.
Se utilizarán 658 MB de espacio de disco adicional después de esta operación.
```

### **Instalación de paquetes adicionales**<a name = "id2"></a>
Ahora instalaremos algunos paquetes necesarios para instalar GitLab.

```bash
daw@DLP17-Lubuntu18:~$   sudo apt install -y vim curl ca-certificates apt-transport-https
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
ca-certificates ya está en su versión más reciente (20210119~18.04.2).
curl ya está en su versión más reciente (7.58.0-2ubuntu3.16).
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes adicionales:
  vim-runtime
Paquetes sugeridos:
  ctags vim-doc vim-scripts
Se instalarán los siguientes paquetes NUEVOS:
  apt-transport-https vim vim-runtime
0 actualizados, 3 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
Se necesita descargar 6.593 kB de archivos.
```

### **Instalación de GitLab**<a name = "id3"></a>
Ahora en este paso descargaremos **GitLab**, para ello abrimos una terminal y lanzamos el siguiente comando:

```bash
daw@DLP17-Lubuntu18:~$   curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
Detected operating system as Ubuntu/bionic.
Checking for curl...
Detected curl...
Checking for gpg...
Detected gpg...
Running apt-get update... done.
Installing apt-transport-https... done.
Installing /etc/apt/sources.list.d/gitlab_gitlab-ce.list...done.
Importing packagecloud gpg key... done.
Running apt-get update... done.

The repository is setup! You can now install packages.
```

Después de descargarlo, procederemos a su instalación con lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$   sudo apt install gitlab-ce
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes adicionales:
  ncurses-term openssh-server openssh-sftp-server ssh-import-id
Paquetes sugeridos:
  molly-guard monkeysphere rssh ssh-askpass
Se instalarán los siguientes paquetes NUEVOS:
  gitlab-ce ncurses-term openssh-server openssh-sftp-server ssh-import-id
0 actualizados, 5 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
Se necesita descargar 944 MB de archivos.
Se utilizarán 2.514 MB de espacio de disco adicional después de esta operación.
```

Por último lanzaremos lo siguiente para terminar la configuración de **GitLab**.

```bash
daw@DLP17-Lubuntu18:~$   sudo gitlab-ctl reconfigure
```

### **Acceso**<a name = "id4"></a>
Ahora para acceder, lanzaremos el comando **ip a** en nuestra terminal para saber la IP de nuestra máquina.

```bash
daw@DLP17-Lubuntu18:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:0b:fb:48 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 84923sec preferred_lft 84923sec
    inet6 fe80::a00:27ff:fe0b:fb48/64 scope link
       valid_lft forever preferred_lft forever
```
