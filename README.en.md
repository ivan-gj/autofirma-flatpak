# Autofirma Flatpak

[Leer en Español](README.md)

---

Unofficial Flatpak of Autofirma, the Spanish Government's electronic signature application.

> [!WARNING]
> **Unofficial community package** - Not supported by the Spanish Government.

## Current Status

✅ **Compatible with:**
- Local document signing
- Native Firefox and [Flathub's Firefox][firefox-flathub] (Flatpak)
- DNIe
- Other PKCS#11 cryptographic modules supported by OpenSC (e. g.: YubiKey) - Follow the same procedure as for integrating with DNIe.

## Installation

**Prerequisites:**
```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08 org.freedesktop.Sdk.Extension.openjdk17//25.08
```

**Build and install:**
```bash
git clone https://gitlab.com/ivangj/autofirma-flatpak.git
cd autofirma-flatpak
flatpak-builder --force-clean --user --install build-dir es.gob.autofirma.yaml
flatpak run es.gob.autofirma
```

## Integration with DNIe
- Open the application and go to `Herramientas` > `Preferencias`. Select the tab: `Almacenes de claves`.
- In section `Tarjetas inteligentes`, click on `Agregar tarjeta`.
- Insert a name (e. g.: `OpenSC`) in `Nombre de la tarjeta` and click `Examinar`.
- Select the library: `/app/lib/opensc-pkcs11.so`.
- (Optional) In `Almacén por defecto`, select the recently created card to select it by default when signing.

## Collaboration

Help us improve! The goal is to publish on Flathub.

- [**Report issues**][issues] (preferably on GitLab)
- [**Matrix chat**][matrix-chat]
- [Primary repository on GitLab][self-repo] (GitHub is a mirror)

## References

- [Official AutoFirma website][official-website]
- [Official repository][official-repo]
- [Flatpak documentation][flatpak-docs]
- [**Unofficial build attempt by aruiz**][aruiz-repo]


[aruiz-repo]: https://github.com/aruiz/autofirma-flatpak
[firefox-flathub]: https://flathub.org/apps/org.mozilla.firefox
[flatpak-docs]: https://docs.flatpak.org/
[issues]: https://gitlab.com/ivangj/autofirma-flatpak/-/issues
[matrix-chat]: https://matrix.to/#/#autofirma-flatpak:matrix.org
[official-repo]: https://github.com/ctt-gob-es/cliente-firma-desktop
[official-website]: https://firmaelectronica.gob.es/
[self-repo]: https://gitlab.com/ivangj/autofirma-flatpak
