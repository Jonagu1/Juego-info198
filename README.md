# Juego-info198
# Juego-info198- Proyecto de C++/Qt

## Introducción

Una parte del programa del sistema operatvo, sirve para crear un ejecutable para el juego.
Este proyecto es un juego de tablero multijugador por turnos, desarrollado en C++ con el framework Qt 6. Utiliza un modelo Host-Cliente (Servidor-Cliente) para permitir partidas en una red local (LAN). La aplicación es multiplataforma y ha sido diseñada para compilarse y ejecutarse en Windows y sistemas operativos GNU/Linux.

## Requisitos Previos

## Requisitos Previos

Todos los desarrolladores deben tener **Qt 6** con **Qt Creator** instalados.

### Windows

1.  Descargar el **Instalador Online de Qt** desde el [sitio web oficial](https://www.qt.io/download-qt-installer).
2.  Ejecutar el instalador. Se requiere una cuenta de Qt (gratuita).
3.  En la pantalla "Seleccionar componentes", los siguientes elementos deben estar marcados:
    * **Qt 6.x.x** (la versión más reciente disponible).
    * Bajo `Qt 6.x.x`, marcar el compilador **MinGW x.x.x** (ej: `MinGW 13.1.0 64-bit`).
    * **Qt Creator 1x.x.x**.

### Linux (Debian/Arch-based)

Se deben instalar los paquetes de desarrollo de Qt 6, el compilador, las herramientas y las dependencias que faltan.

# Instalar todas las dependencias de desarrollo de Qt
```bash
sudo apt update
sudo apt install build-essential qtcreator cmake gdb qt6-base-dev qt6-base-dev-tools qt6-tools-dev-tools libgl1-mesa-dev
**En sistemas Debian-based (Mint, Ubuntu):**
```
**En sistemas Arch-based:**
# Instalar el compilador, el IDE, las herramienta, las librerías y dependencias de Qt 6
```bash
sudo pacman -Syu gcc qtcreator gdb cmake

sudo pacman -S qt6-base qt6-tools mesa
```

El juego utiliza un archivo .env para la configuración de la partida.

    Localizar el archivo .env.example en la raíz del proyecto.

    Crear una copia de este archivo con el nombre .env. (En Linux: cp .env.example .env).

    Importante: Asegurarse de que el archivo se llame .env y no .env.txt.

Compilar el Proyecto

    Abrir Qt Creator.

    Navegar a Archivo > Abrir Proyecto o Archivo....

    Seleccionar el archivo JuegoSO.pro (o CMakeLists.txt) del repositorio clonado.

    Qt Creator detectará el "Kit" de compilación apropiado (MinGW en Windows, GCC en Linux). Confirmar la configuración.

    Hacer clic en el botón "Ejecutar" (Play) en la esquina inferior izquierda. Qt Creator compilará y lanzará la aplicación.

Ejecución

La aplicación utiliza un modelo Host/Cliente. Un usuario debe actuar como Host (Servidor).

Instrucciones para el Host

    Lanzar la aplicación.

    En la pantalla de conexión, introducir un Nombre.

    Dejar el campo IP en blanco y hacer clic en "Crear Partida".

    La aplicación iniciará la instancia del servidor internamente. El usuario se encuentra ahora en el Lobby como Administrador.

    El Host debe obtener su dirección IP local (ejecutando ipconfig en cmd de Windows, o ip a en la terminal de Linux) y compartirla con los demás jugadores.

Instrucciones para el Cliente

    Lanzar la aplicación.

    En la pantalla de conexión, introducir un Nombre.

    En el campo IP, introducir la dirección IP proporcionada por el Host.

    Hacer clic en "Unirse a Partida".

Lobby

    Todos los jugadores verán la lista de usuarios conectados y sus respectivos equipos.

    Cada jugador debe introducir un nombre de equipo y hacer clic en "Unirse a Equipo".

    El Admin (Host) es el único jugador que puede ver y presionar el botón "Empezar Juego".

    El juego solo puede comenzar cuando se cumplen las condiciones de inicio (mínimo 2 equipos, con mínimo 2 jugadores por equipo).

Configuración (.env) (Este ya lo añadí)

Las reglas del juego pueden ser modificadas editando el archivo .env antes de lanzar la partida como Host. La lógica del juego leerá estas variables de entorno al iniciarse.

    WIN_THRESHOLD=30: El puntaje que un equipo necesita para ganar (el valor por defecto es 20).

    BOARD_SIZE=50: (Variable de lógica, por defecto 20).
