# Instalación de CentOS 8


Este documento proporciona una guía detallada para la instalación de CentOS 8. Asegúrate de tener una copia de la imagen ISO de CentOS 8 y un dispositivo USB de arranque.


## 1. Descargar la imagen ISO

Descarga la imagen ISO de CentOS 8 desde el sitio web oficial de CentOS o un mirror confiable.  Necesitarás la imagen ISO "DVD" que incluye BaseOS y AppStream.


## 2. Crear un USB booteable

Utiliza la herramienta `dd` para crear un USB booteable.  Reemplaza `/ruta/a/centos8.iso` con la ruta a tu archivo ISO y `/dev/sdX` con la ruta a tu dispositivo USB (**ten mucho cuidado con esto, ya que un error podría sobrescribir datos importantes**). Verifica la ruta correcta con `lsblk`.

```bash
sudo dd bs=4M if=/ruta/a/centos8.iso of=/dev/sdX status=progress && sync
```

## 3. Arrancar desde el USB

Configura tu BIOS para arrancar desde el USB.  Esto generalmente implica presionar una tecla específica (como F2, F12, Esc o Del) durante el inicio. Consulta la documentación de tu placa base para obtener instrucciones específicas.


## 4. Iniciar el instalador

Una vez que hayas arrancado desde el USB, selecciona "Install CentOS 8" en el menú de arranque.


## 5. Verificar el medio de instalación (opcional)

Si es la primera vez que usas este medio de instalación, puedes verificar su integridad seleccionando "Test this media & install CentOS 8".


## 6. Seleccionar el idioma

En la pantalla de selección de idioma, elige "Español (Latinoamericano)".


## 7. Configurar la fuente de instalación

En "INSTALL SOURCE", generalmente puedes dejar la opción por defecto.


## 8. Configurar el destino de la instalación

En "INSTALL DESTINATION", selecciona el disco o partición donde se instalará CentOS 8.  Elige "Custom" para configurar las particiones manualmente.

* **Esquema de particionado:**  Se recomienda utilizar GPT para sistemas modernos.
* **Particiones:** Crea las siguientes particiones:
    * `/boot`:  Alrededor de 1GB (formato ext4)
    * `swap`:  El doble de tu RAM (sin formato)
    * `/`: El espacio restante (formato ext4)
    * `/home` (opcional): Si deseas una partición separada para los directorios de usuario.

## 9. Configurar la red y el nombre de host

En "NETWORK & HOSTNAME":

* Configura el adaptador de red.  Para IPv4, selecciona "Automático (DHCP)". Para IPv6, selecciona "Link-local area only" si estás en un clúster, o "Automático (DHCP)" si necesitas conectividad IPv6.
* Cambia el nombre de host a un nombre descriptivo.
* Habilita todas las redes necesarias.

## 10. Seleccionar el software

En "SOFTWARE SELECTION", selecciona "Servidor" como la instalación base.  Puedes agregar o quitar paquetes individuales según tus necesidades.  Considera instalar "Servidor con GUI" si necesitas un entorno gráfico.


## 11. Configurar la zona horaria

Selecciona tu zona horaria.


## 12. Crear usuario y contraseña

En "USER CREATION", crea un usuario y una contraseña.  Asegúrate de darle a este usuario privilegios de administrador marcando la casilla "Make this user administrator".


## 13. Iniciar la instalación

Una vez que hayas configurado todas las opciones, haz clic en "Begin Installation".  La instalación puede tardar un tiempo.


## 14. Reiniciar el sistema

Después de que la instalación se complete, reinicia el sistema y retira el USB de arranque.


## 15. Primer inicio de sesión

Inicia sesión con el usuario y la contraseña que creaste durante la instalación.

