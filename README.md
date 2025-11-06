# AutoFirma Flatpak

[Read in English](README.md)

---

Este repositorio permite construir AutoFirma para Flatpak, la aplicación de firma electrónica del Gobierno de España.

> [!WARNING]
> Este es un paquete comunitario y **no está soportado oficialmente por el Gobierno de España**.



## Objetivo

El objetivo principal de este proyecto es empaquetar AutoFirma para Linux como Flatpak, con el objetivo final de **enviarlo a [Flathub][flathub]** para facilitar su distribución e instalación.



## ¡Colabora!

Este es un proyecto en curso. Dirígete a los [issues][issues] y ayuda o envía tus propios issues y propuestas.

También tenemos un [chat en Matrix][matrix-chat] para conversaciones rápidas. ¡Ayúdanos a conectarlo con otras plataformas!


## Prerrequisitos

Para construir este Flatpak, necesitas tener `flatpak` y `flatpak-builder` instalados en tu sistema.

El comando `bsdunzip` también debe estar disponible. Podría estar incluido en `libarchive` en tu distribución.


### Instalar el Runtime y SDK de Freedesktop

Esta aplicación utiliza el runtime Freedesktop 25.08. Añade el repositorio de Flathub e instala el runtime y SDK requeridos con los siguientes comandos:

```bash
flatpak remote-add --if-not-exists --user flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install --user flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08
```


## Instalación Local

Una vez cumplidos los prerrequisitos, puedes construir e instalar el Flatpak localmente.

**Clona este repositorio:**
```bash
git clone https://github.com/ivan-gj/autofirma-flatpak.git
cd autofirma-flatpak
```

**Construye e instala la aplicación**. Usa `flatpak-builder` para construir la aplicación e instalarla para el usuario actual.
```bash
flatpak-builder --force-clean --user --install build-dir es.gob.AutofirmaClient.yaml
```

**Ejecuta la aplicación**. Ahora puedes ejecutar AutoFirma usando
```bash
flatpak run es.gob.AutofirmaClient
```


## Enlaces y Referencias

- [**Sitio web oficial de Autofirma**][official-website]
- [**Repositorio oficial del Cliente AutoFirma**][official-repo]
- [**Intento de construcción no oficial por aruiz**][aruiz-repo]
- [**Documentación de Flatpak**][flatpak-docs]
- [**Flathub**][flathub]

[official-website]: https://firmaelectronica.gob.es
[official-repo]: https://github.com/ctt-gob-es/clienteafirma
[aruiz-repo]: https://github.com/aruiz/autofirma-flatpak
[flatpak-docs]: https://docs.flatpak.org
[flathub]: https://flathub.org
[flatpak-bundles]: https://docs.flatpak.org/en/latest/single-file-bundles.html
[matrix-chat]: https://matrix.to/#/#autofirma-flatpak:matrix.org
[issues]: https://github.com/ivan-gj/autofirma-flatpak/issues
