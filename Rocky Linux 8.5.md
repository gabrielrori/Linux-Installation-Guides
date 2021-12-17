



# Rocky linux 8.5

Basado en:
https://docs.rockylinux.org/guides/installation/

---------------

1. Descargar el DVD (BaseOS y repositorios AppStream).

2. Grabar en un USB booteable con DD command.

3. Booter PC desde USB.

4. En el instalador de Rocky Linux 8.5... Instalar con checkeo del medio de instalación (si es la primera vez que se instala), para comprobar que Rocky ha sido bien grabado.
5. En KEYBOARD, seleccionar Spanish (Latin-American).

6. INSTALL SOURCE: Origen por defecto.

7. INSTALL DESTINATION: Seleccionar el disco o partisión en la cual se vaya a instalar. Seleccionar "custom", eliminar todo el contenido, en MBR crear swap, home (opcional) y root (/).

8. En NETWORK & HOSTNAME configurar adaptador de red: En IPv4 "Automatic" y en IPv6 "Link-local area only" (Clusters). Cambiar nombre al hostname. Habilitar todas las redes.

11. SOFTWARE Seleccionar servidor y los paquetes que se desean instalar.

12. En USUARIO Y CLAVE,  crear usuario y clave, dar derechos de administrador.


------------------------------------------------------
