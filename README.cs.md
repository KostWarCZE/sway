# sway
CZECH VERSION

"**S**irCmpwn's **Way**land compositor" je **work in progress**
i3-compatibilní window manager s [Wayland](http://wayland.freedesktop.org/) compositorem.
Pro více informací čtěte [FAQ](https://github.com/swaywm/sway/wiki) či se připojte na
[IRC channel](http://webchat.freenode.net/?channels=sway&uio=d4) (nebo-li #sway na
irc.freenode.net).

**Upozornění**: Prohlížíte si **nestabilní** a **nepodporovanou** sway master branch, 
odkud se bude práce zpracovávat do [wlroots](https://github.com/swaywm/wlroots). 
Podporovaná verze branch je 0.15, konciví-uživatelé by meli používat jen stabilní verze.

Pokud chcete podpořit vývoj swaye, tak se můžete přidat na [SirCmpwn's
Patreon page](https://patreon.com/sircmpwn).

## Podpis zveřejněně verze

Zveřejněné verze jsou podepsány přes [B22DA89A](http://pgp.mit.edu/pks/lookup?op=vindex&search=0x52CB6609B22DA89A)
aa zveřejněny [na GitHubu](https://github.com/swaywm/sway/releases).

## Status

- [i3 feature support](https://github.com/swaywm/sway/issues/2)
- [IPC feature support](https://github.com/swaywm/sway/issues/98)
- [i3bar feature support](https://github.com/swaywm/sway/issues/343)
- [i3-gaps feature support](https://github.com/swaywm/sway/issues/307)
- [security features](https://github.com/swaywm/sway/issues/984)

## Instalace

### Z balíčků / From Packages

Sway je dostupný na několika distibucích linuxu. Zkuste instalovat sway balíček z té Vaší. 
Pokud to není dostupné, tak zkuste [tuto wiki stránku](https://github.com/swaywm/sway/wiki/Unsupported-packages)
pro více informací na instalaci pro Vaší distribuci.

Pokud máte zájem o zabalení swaye pro Vaší distribuci, tak se zastavte na IRC či nás kontaktunte na email sir@cmpwn.com pro rady.

### Zpracování ze zdroje / Compiling from Source 

Nainstalujte návazné balíčky:

* meson
* [wlroots](https://github.com/swaywm/wlroots)
* wayland
* xwayland
* libinput >= 1.6.0
* libcap
* pcre
* json-c >= 0.13
* pango
* cairo
* gdk-pixbuf2 *
* pam **
* dbus >= 1.10 ***
* [scdoc](https://git.sr.ht/~sircmpwn/scdoc) (nutný pro man stránky.)

_\*Důležité jen pro swaybar, swaybg, and swaylock_

_\*\*Důležité jen pro swaylock_

_\*\*\*Důležité jen pro tray support_

Vyvolejte následující příkazy:

    meson build
    ninja -C build
    sudo ninja -C build install

Na systémech bez logind, budete potřebovat SUID pro sway knihovnu:

    sudo chmod a+s /usr/local/bin/sway

Sway deaktivuje root pravomoce krátce po spuštění.

## Konfigurace

Pokud už používáte i3 window manager, tak zkopírujte Váš i3 config do `~/.config/sway/config` a to by mělo fungovat out of the box. Jinak zkopírujte vzorovou konfiguraci do `~/.config/sway/config`, která je běžně uložena v `/etc/sway/config`.
Vyvolejte `man 5 sway` pro více informací ohledně konfigurace.

## Spuštění

Vyvolejte `sway` z TTY. Některé display managers mohou fungovat, ale nejsou podporovány swayem
(gdm by měl také fungovat docela dobře).
