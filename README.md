#!/bin/bash
# Integrative Project: Build, Boot, and Attack

## Integrantes

- Jorge Aguilar
- Matias Quinteros
- Jose Velasco

## Docente

Ing. Jonathan E. Tito O.

## Descripción del Proyecto

El objetivo de este proyecto es comprender el funcionamiento de un sistema Linux desde diferentes niveles, incluyendo la personalización de una distribución Linux, la construcción de un kernel de 64 bits y el despliegue de un laboratorio de seguridad basado en Docker.

El proyecto se divide en tres partes principales:

1. Creación de una distribución Linux personalizada utilizando Cubic.
2. Construcción y arranque de un kernel de 64 bits en QEMU.
3. Despliegue y validación del laboratorio Black Hat Bash, además de la ejecución de una técnica de reconocimiento dentro del entorno aislado.

---

# Estructura del Repositorio

```
integrative-project/
│
├── part1-cubic-distro/
├── part2-kernel/
├── part3-blackhatbash-lab/
├── video/
└── README.md




# Parte 1 - Distro Personalizada con Cubic

Se creó una distribución Linux personalizada basada en Linux Mint/Ubuntu utilizando Cubic.

Las modificaciones realizadas se encuentran documentadas en:


part1-cubic-distro/README.md


# Parte 2 - Kernel de 64 Bits

Se implementó un kernel mínimo de 64 bits utilizando Docker, NASM, GRUB y QEMU.

La documentación completa se encuentra en:

```
part2-kernel/README.md
```

---

# Parte 3 - Black Hat Bash Lab

Se desplegó un laboratorio de seguridad aislado utilizando Docker y Docker Compose.

La documentación y evidencias se encuentran en:

```
part3-blackhatbash-lab/README.md
```

---

# Evidencias

Las capturas de pantalla, logs y resultados obtenidos se encuentran organizados dentro de cada carpeta correspondiente.

---

# Video Demostrativo

Enlace:

https://drive.google.com/drive/folders/1WXend9lIdzGWVUEEaS4ZZddmogmFuRvT?usp=drive_link

---


# Conclusiones

- Se logró personalizar una distribución Linux mediante Cubic.
- Se comprendió el proceso de arranque de un kernel de 64 bits.
- Se desplegó correctamente un laboratorio basado en Docker.
- Se aplicó una técnica de reconocimiento dentro de un entorno controlado y aislado.
- El proyecto permitió integrar conocimientos de sistemas operativos, virtualización, redes y seguridad informática.