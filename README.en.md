# AutoFirma Flatpak

[Leer en español](README.es.md)

---


This repository can build AutoFirma for Flatpak, the electronic signature application from the Spanish Government.

> [!WARNING]
> This is a community package and is **not officially supported by the Spanish Government**.



## Objective

The primary goal of this project is to package AutoFirma for Linux as a Flatpak, with the ultimate objective of **submitting it to [Flathub][flathub]** for easy distribution and installation.


## Collaborate! 

This is an ongoing project. Head to the [issues][issues] and help out or submit your own issues and proposals!

We also have a [Matrix chat][matrix-chat] for quick conversations. Help us bridge it to other platforms! 


## Prerequisites

To build this Flatpak, you need to have `flatpak` and `flatpak-builder` installed on your system.

The command `bsdunzip` must also be available. It might be provided by `libarchive` in your distribution.


### Install the Freedesktop Runtime and SDK

This application uses the Freedesktop 25.08 runtime. Add the Flathub repository and install the required runtime and SDK with the following commands:

```bash
flatpak remote-add --if-not-exists --user flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install --user flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08
```


## Local Installation

Once the prerequisites are met, you can build and install the Flatpak locally.

**Clone this repository:**
```bash
git clone https://github.com/ivan-gj/autofirma-flatpak.git
cd autofirma-flatpak
```

**Build and install the application**. Use `flatpak-builder` to build the application and install it for the current user.
```bash
flatpak-builder --force-clean --user --install build-dir es.gob.AutofirmaClient.yaml
```

**Run the application**. You can now run AutoFirma using
```bash
flatpak run es.gob.AutofirmaClient
```


## Links and References

- [**Official Autofirma website**][official-website]
- [**Official AutoFirma Client Repository**][official-repo]
- [**Unofficial Build Attempt by aruiz**][aruiz-repo]
- [**Flatpak Documentation**][flatpak-docs]
- [**Flathub**][flathub]


[official-website]: https://firmaelectronica.gob.es
[official-repo]: https://github.com/ctt-gob-es/clienteafirma
[aruiz-repo]: https://github.com/aruiz/autofirma-flatpak
[flatpak-docs]: https://docs.flatpak.org
[flathub]: https://flathub.org
[flatpak-bundles]: https://docs.flatpak.org/en/latest/single-file-bundles.html
[matrix-chat]: https://matrix.to/#/#autofirma-flatpak:matrix.org
[issues]: https://github.com/ivan-gj/autofirma-flatpak/issues
