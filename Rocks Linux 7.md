


# Rocks Linux 7



## Instalación y configuración del frontend

El fronted debe tener instalado los siguientes rolls como mínimo:
-   Kernel Roll
-   Base Rol
-   Core Roll
-   CentOS Roll
-   Updates-CentOS Roll

Rocks 7 solo permite solo permite instalación por la red, se debe poder acceder a todos los rolls desde un servidor.

## Bootear con el roll del kernel de Rocks 7 en el frontend

1.  Grabar la imagen del kernel en modo dd.
       
2.  Bootear la imagen en el frontend
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/rocks-boot-screen-640.png)
    
3.  Seleccionar el idioma   
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/choose-language-640.png)
  Configurar la red pública:
       
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/no-network-scrolled-640.png)
    
    En  "NETWORK & HOST NAME" configurar la IP pública y el nombre de host. Si existen varias interfaces, configurar sólo la interfaz para acceso público, en este caso es eth1.
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/network-public-640.png)
    
    Hacer click en configurar y seleccionar la dirección IPv4 en configuración manual.
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/manual-network-frontend-640.png)
    
    Configurar IPv6 como "link-local only"
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/ipv6-link-local-640.png)
    
    Guardar y hacer click en on/off para activar la interfaz red. Debería aparecer el IP y el DNS. Cambiar el hostname:
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/network-up-640.png)
   
    
4.  Configurar la red local
    
    En ROCKS CLUSTER CONFIG seleecionar CLUSTER PRIVATE NETWORK
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/private-network-setup-640.png)
    
    En el menu desplegable "private cluster interface" seleccionar la interfaz física para la conexión de área local, no está disponible el adaptador de conexión a internet:
    
    Seleccionar la subnet IPv4. Las IP pública y privada deben ser diferentes.
    
        
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/private-network-complete-640.png)
    
5.  Seleccionar los rolls a instalar en ROCKS ROLLS
    
    Escribir el servidor de rolls y seleccionar los rolls:
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/list-rolls-640.png)
    
Hacer click en "Add Selected Rolls" para agregarlos al frontend.
    
6.  Configurar el cluster en CLUSTER CONFIG
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/configure-cluster-640.png)
    
    Completar los items en rojo:
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/configure-cluster-1-640.png)

    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/configure-contact-640.png)
    
7.  Configurar la partición con el esquema deseado dependiendo si es UEFI o BIOS.
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/configure-partition-manual-640.png)
  
    
8.  Iniciar la instalación:
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/begin-ready-640.png)
    
   
    
9.  Configurar la contraseña del rootcon SET ROOT PASSWORD, aún no crear usuario.
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/need-rootpw-640.png)

    Después de la instalación, se verá la siguiente pantalla:
    
    ![](http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/images/install7/installation-complete-640.png)
  10.  Hacer click en reboot y remover medio de instalación.




------------------------------------------------------------------------------

Guía basada en:
http://central-7-0-x86-64.rocksclusters.org/roll-documentation/base/7.0/install-frontend.html

