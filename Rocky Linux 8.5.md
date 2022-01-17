

# Rocky linux 8.5

1. Descargar el DVD de Rocky Linux 8.5 : "Rocky-8.5-x86_64-dvd1.iso", incluye BaseOS y repositorios del AppStream. 

2. Grabar imagen en modo DD y bootear para iniciar la instalación.

3. Si es la primera vez que se usa el medio, seleccionar instalar con checkeo del medio de instalación para comprobar que Rocky ha sido bien grabado.

4. Seleccionar lenguaje (inglés) y en KEYBOARD el teclado correspondiente (español - latinoamericano).

5. TIME & DATE: seleccionar la zona horaria correspondiente (Americas - Lima)

6. INSTALLATION SOURCE: Origen por defecto (medio de instalación), ya que todos los paquetes necesarios se encuentran en la imagen DVD y no se requieren repositorios adicionales.

7. SOFTWARE SELECTION: Seleccionar "Server with GUI" y los paquetes que se desean instalar.

8. INSTALLATION DESTINATION: Seleccionar el disco o partisión en la cual se vaya a instalar. Seleccionar CUSTOM y en el modo de participación manualmente, elmiminar contenido previo y crear particiones. En MBR: crear SWAP, HOME (opcional) y ROOT (/) con el espacio restante. Aceptar cambios.

9. KDUMP: Habilitar KDUMP para diagnósticos de posibles fallas en el sistema

10. En NETWORK & HOSTNAME configurar adaptador de red: En IPv4 "Automatic (DHCP)" y en IPv6 "Link-local oronly". Cambiar nombre al hostname, habilitar redes.

11. En ROOT PASSWORD,  crear usuario y clave. En USER CREATION, crear usuario con derechos de administrador.

12. Reiniciar y aceptar acuerdos de licencia.
