# Instalación de Rocks Linux 7

Esta guía describe la instalación y configuración de un frontend en Rocks Linux 7. Rocks 7 solo permite la instalación por red, por lo que necesitarás acceso a un servidor de rolls.

## Rolls Necesarios

El frontend requiere los siguientes rolls como mínimo:

* Kernel Roll
* Base Roll
* Core Roll
* CentOS Roll
* Updates-CentOS Roll

## Bootear con el Roll del Kernel

1. **Grabar la Imagen del Kernel:**

    ```bash
    sudo dd bs=4M if=/ruta/a/imagen_kernel.iso of=/dev/sdX status=progress && sync
    ```

    **Advertencia:** Reemplaza `/ruta/a/imagen_kernel.iso` con la ruta correcta a la imagen del kernel y `/dev/sdX` con la ruta a tu dispositivo USB. **Verifica la ruta con `lsblk` antes de ejecutar para evitar la pérdida de datos.**

2. **Bootear la Imagen:** Configura tu BIOS para arrancar desde el USB.

3. **Seleccionar Idioma:** Elige tu idioma preferido.

4. **Configurar la Red Pública (NETWORK & HOST NAME):**

    * Configura la IP pública, máscara de subred, puerta de enlace y DNS.
    * Configura el nombre de host.
    * Si tienes varias interfaces de red, configura solo la interfaz de acceso público.

    **Ejemplo de configuración manual de IPv4:**

    ```
    Dirección IP: 192.168.1.10
    Máscara de subred: 255.255.255.0
    Puerta de enlace: 192.168.1.1
    DNS: 8.8.8.8, 8.8.4.4
    ```

    * Configura IPv6 como "link-local only".
    * Activa la interfaz de red.

5. **Configurar la Red Privada (ROCKS CLUSTER CONFIG > CLUSTER PRIVATE NETWORK):**

    * Selecciona la interfaz física para la red privada (no la de acceso público).
    * Configura la subred IPv4 (diferente a la pública).

    **Ejemplo:**

    ```
    Interfaz: eth0
    Subred IPv4: 10.0.0.0/24
    ```

6. **Seleccionar Rolls (ROCKS ROLLS):**

    * Especifica la dirección del servidor de rolls.
    * Selecciona los rolls necesarios y agrégalos al frontend.

    **Ejemplo:**

    ```
    Servidor de Rolls: rocks.example.com
    Rolls: Kernel, Base, Core, CentOS, Updates-CentOS
    ```

7. **Configurar el Clúster (CLUSTER CONFIG):**

    * Completa la información requerida, como el nombre del clúster, la organización, el contacto, etc.

8. **Configurar la Partición:**

    * Configura el esquema de partición (UEFI o BIOS).
    * Crea las particiones necesarias.  Se recomienda usar una herramienta como `parted` o `gdisk` para particiones GPT en sistemas UEFI.

    **Ejemplo con `parted` (reemplaza /dev/sda con tu disco):**

    ```bash
    # parted /dev/sda
    # mklabel gpt
    # mkpart /boot ext4 1MiB 500MiB
    # mkpart swap linux-swap 500MiB 2GiB
    # mkpart / ext4 2GiB 100%
    # quit
    ```

9. **Iniciar la Instalación:** Haz clic en "Begin Installation".

10. **Contraseña de Root (SET ROOT PASSWORD):** Define una contraseña segura para root.  **No crees otros usuarios en este paso.**

11. **Reiniciar:** Después de la instalación, reinicia el sistema y retira el medio de instalación.

