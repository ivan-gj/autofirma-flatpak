# Autofirma Flatpak

[Read in English](README.en.md)

---

Flatpak no oficial de Autofirma, la aplicación de firma electrónica del Gobierno de España.

> [!WARNING]
> **Paquete comunitario no oficial** - No está soportado por el Gobierno de España.

## Estado actual

✅ **Compatible con:**
- Firma local de documentos
- Firefox nativo y [Flathub][firefox-flathub] (Flatpak)
- DNIe
- Otros módulos criptograficos PKCS#11 soportados por OpenSC (p. ej.: YubiKey) - Seguir el mismo procedimiento que para la integración con DNIe.

## Instalación

**Prerrequisitos:**
```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08 org.freedesktop.Sdk.Extension.openjdk17//25.08
```

**Construir e instalar:**
```bash
git clone https://gitlab.com/ivangj/autofirma-flatpak.git
cd autofirma-flatpak
flatpak-builder --force-clean --user --install build-dir es.gob.autofirma.yaml
```

## Integración con DNIe

- Abrir la aplicación e ir a `Herramientas` > `Preferencias`. Seleccionar la pestaña `Almacenes de claves`.
- En el apartado `Tarjetas inteligentes`, hacer click en `Agregar tarjeta`.
- Introducir un nombre (p.ej.: `OpenSC`) en `Nombre de la tarjeta` y hacer click en `Examinar`.
- Seleccionar la libreria `/app/lib/opensc-pkcs11.so`.
- (Opcional) En `Almacén por defecto`, seleccionar la tarjeta recién creada para seleccionarla por defecto al firmar.


## Colaboración

¡Ayúdanos a mejorar! El objetivo es publicar en Flathub.

- [**Reportar incidencias**][issues] (preferiblemente en GitLab)
- [**Chat en Matrix**][matrix-chat]
- [Repositorio principal en GitLab][self-repo] (GitHub es espejo)

## Referencias

- [Sitio oficial de AutoFirma][official-website]
- [Repositorio oficial][official-repo]
- [Documentación Flatpak][flatpak-docs]
- [**Intento de construcción no oficial por aruiz**][aruiz-repo]

[aruiz-repo]: https://github.com/aruiz/autofirma-flatpak
[firefox-flathub]: https://flathub.org/apps/org.mozilla.firefox
[flatpak-docs]: https://docs.flatpak.org/
[issues]: https://gitlab.com/ivangj/autofirma-flatpak/-/issues
[matrix-chat]: https://matrix.to/#/#autofirma-flatpak:matrix.org
[official-repo]: https://github.com/ctt-gob-es/cliente-firma-desktop
[official-website]: https://firmaelectronica.gob.es/
[self-repo]: https://gitlab.com/ivangj/autofirma-flatpak
