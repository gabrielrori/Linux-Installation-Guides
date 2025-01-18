# Instalación de Rocky Linux 8.5

Esta guía proporciona instrucciones detalladas para la instalación de Rocky Linux 8.5. Asegúrate de tener una copia de la imagen ISO "Rocky-8.5-x86_64-dvd1.iso" y un dispositivo USB de arranque.

## 1. Descargar la Imagen ISO

Descarga "Rocky-8.5-x86_64-dvd1.iso" del sitio web oficial de Rocky Linux o un mirror confiable. Esta imagen incluye BaseOS y los repositorios de AppStream.

## 2. Crear un USB Booteable

Utiliza la herramienta `dd` para crear un USB booteable. Reemplaza `/ruta/a/rocky-8.5.iso` con la ruta a tu archivo ISO y `/dev/sdX` con la ruta a tu dispositivo USB (**¡extrema precaución! Verifica la ruta con `lsblk` antes de ejecutar, ya que podrías sobrescribir datos importantes**).

```bash
sudo dd bs=4M if=/ruta/a/rocky-8.5.iso of=/dev/sdX status=progress && sync
```

## 3. Arrancar e Iniciar la Instalación

Configura tu BIOS para arrancar desde el USB.  Presiona una tecla específica (F2, F12, Esc, Del, etc.) durante el inicio. Consulta la documentación de tu placa base. Una vez que hayas arrancado desde el USB, selecciona "Install Rocky Linux 8.5".

## 4. Verificar el Medio de Instalación (Opcional)

Si es la primera vez que usas este medio, selecciona "Test this media & install Rocky Linux 8.5" para verificar su integridad.

## 5. Seleccionar Idioma y Teclado

* **LANGUAGE:** Selecciona "English".
* **KEYBOARD:** Selecciona "Spanish (Latin American)".

## 6. Configurar Fecha y Hora (TIME & DATE)

Selecciona tu zona horaria: "Americas - Lima".

## 7. Configurar la Fuente de Instalación (INSTALLATION SOURCE)

Deja la opción por defecto (medio de instalación), ya que la imagen DVD contiene todos los paquetes necesarios.

## 8. Selección de Software (SOFTWARE SELECTION)

Selecciona "Server with GUI" y cualquier otro paquete adicional que necesites.

## 9. Destino de la Instalación (INSTALLATION DESTINATION)

* Selecciona el disco o partición donde instalarás Rocky Linux 8.5.
* Selecciona "Custom".
* **Particiones (MBR):**
    * Elimina cualquier partición existente en el disco.
    * Crea las siguientes particiones:
        * `/boot`: ~1GB (ext4)
        * `swap`:  El doble de tu RAM (swap)
        * `/home` (opcional): Tamaño deseado (ext4)
        * `/`: Espacio restante (ext4)

```bash
# Comandos para particionar con fdisk (reemplaza /dev/sda con tu disco):
# fdisk /dev/sda
# n (nueva partición)
# p (primaria)
# 1 (número de partición)
# (tamaño por defecto para /boot o especifica el tamaño)
# t (cambiar tipo de partición)
# 83 (Linux)
# ... (repetir para swap, /home y /)
# w (escribir cambios)
```

## 10. KDUMP

Habilita KDUMP para el diagnóstico de fallas del sistema.

## 11. Red y Nombre de Host (NETWORK & HOSTNAME)

* **IPv4:** "Automatic (DHCP)"
* **IPv6:** "Link-local only" (o "Automatic (DHCP)" si necesitas IPv6).
* **Hostname:** Introduce un nombre de host descriptivo.
* Habilita las redes necesarias.


## 12. Contraseña de Root (ROOT PASSWORD)

Define una contraseña segura para el usuario root.

## 13. Creación de Usuario (USER CREATION)

Crea un usuario con privilegios de administrador.

## 14. Iniciar la Instalación

Haz clic en "Begin Installation".

## 15. Reiniciar y Aceptar Acuerdos de Licencia

Después de la instalación, reinicia el sistema y acepta los acuerdos de licencia.
