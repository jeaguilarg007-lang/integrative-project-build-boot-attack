# Parte 2 - Kernel de 64 bits

## Objetivo

El objetivo de esta parte fue construir y ejecutar un kernel mínimo booteable utilizando herramientas de bajo nivel como NASM, GRUB y QEMU.

En esta implementación se completó el *Episode 1* del proyecto del kernel, el cual consiste en crear un kernel básico con encabezado *Multiboot2*, generar una imagen ISO booteable y ejecutarla en QEMU mostrando un mensaje en pantalla.

El kernel fue probado en una máquina virtual x86_64 mediante QEMU.

---

## Herramientas Utilizadas

Para el desarrollo y prueba del kernel se utilizaron las siguientes herramientas:

* *Docker:* utilizado para crear un entorno de compilación reproducible.
* *NASM:* utilizado para ensamblar los archivos escritos en Assembly.
* *GRUB:* utilizado como bootloader para cargar el kernel.
* *GCC / Binutils:* utilizados para enlazar los archivos objeto y generar el binario del kernel.
* *QEMU:* utilizado para emular una máquina x86_64 y probar el arranque del kernel.
* *Make:* utilizado para automatizar la compilación, generación de la ISO y ejecución.

---

## Estructura del Proyecto

La estructura utilizada para la Parte 2 fue la siguiente:

text
part2-kernel/
├── Dockerfile
├── Makefile
├── kernel.iso
├── src/
│   ├── header.asm
│   └── main.asm
├── targets/
│   └── x86_64/
│       ├── linker.ld
│       └── grub.cfg
└── README.md


### Descripción de archivos principales

* *Dockerfile:* define el entorno de compilación con NASM, GRUB, xorriso, Make, GCC y Binutils.
* *Makefile:* automatiza la construcción del kernel, la generación de la ISO y la ejecución en QEMU.
* *src/header.asm:* contiene el encabezado Multiboot2 requerido para que GRUB reconozca el kernel.
* *src/main.asm:* contiene el punto de entrada del kernel y el código que escribe el mensaje OK en memoria de video VGA.
* *targets/x86_64/linker.ld:* define cómo se enlazan las secciones del kernel en memoria.
* *targets/x86_64/grub.cfg:* configura GRUB para arrancar el archivo kernel.bin.
* *kernel.iso:* imagen ISO generada para arrancar el kernel en QEMU.

---

## Compilación

Para compilar el kernel se utilizó el siguiente comando dentro de la carpeta part2-kernel:

bash
make build


Este comando realiza los siguientes pasos:

1. Construye la imagen Docker llamada kernel-builder.
2. Ejecuta el entorno de compilación dentro de Docker.
3. Ensambla los archivos header.asm y main.asm usando NASM.
4. Enlaza los archivos objeto mediante el linker script.
5. Genera el binario kernel.bin.
6. Crea la estructura de arranque con GRUB.
7. Genera la imagen ISO final llamada kernel.iso.

Durante la compilación se obtuvo como resultado la creación exitosa del archivo:

text
kernel.iso


---

## Ejecución

Para ejecutar el kernel en QEMU se utilizó el siguiente comando:

bash
make run


Este comando ejecuta internamente:

bash
qemu-system-x86_64 -cdrom kernel.iso


QEMU carga la imagen ISO generada, inicia GRUB y posteriormente arranca el kernel definido en el archivo grub.cfg.

---

## Resultado

El kernel arrancó correctamente en QEMU y mostró el mensaje:

text
OK


El mensaje fue escrito directamente en la memoria de video VGA, lo cual demuestra que el kernel fue cargado y ejecutado correctamente.

---

## Evidencias

Se tomaron capturas de pantalla de las siguientes etapas:

1. Carpeta del proyecto part2-kernel con los archivos creados.
2. Ejecución del comando make build.
3. Generación exitosa del archivo kernel.iso.
4. Ejecución del comando make run.
5. Ventana de QEMU mostrando el mensaje OK.

---
