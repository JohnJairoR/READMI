**Asociar un volumen de EBS**

Tarea 1. Comenzar a crear la instancia y asignarle un nombre
Selecciona el menú Servicios, localiza los servicios de Computación y selecciona EC2.

Selecciona el botón Lanzar instancia en medio de la página y luego selecciona Lanzar instancia en el menú desplegable
area 2. Imágenes de aplicación y SO
Selecciona una AMI a partir de la cual crear la instancia:

En la lista de AMI disponibles de Quick Start, mantén la AMI predeterminada de Amazon Linux seleccionada.

Además, mantén seleccionada la Amazon Linux 2023 AMI x86_64 (HVM) predeterminada.

El tipo de imagen de máquina de Amazon (AMI) que selecciones determina el sistema operativo (SO) que se ejecutará en la instancia de EC2 que inicies. En este caso, has seleccionado Amazon Linux 2023 como SO invitado.

 

Tarea 3. Elegir el tipo de instancia
Especifica un tipo de instancia:

En el panel Tipo de instancia, mantén el tipo predeterminado t2.micro seleccionado.

El Tipo de instancia define los recursos de hardware asignados a la instancia. Este tipo de instancia tiene 1 unidad de procesamiento central virtual (CPU) y 1 GiB de memoria.

 

Tarea 4. Seleccionar un par de claves
Selecciona el par de claves que quieras asociar con la instancia:

En el menú Nombre del par de claves, selecciona vockey.
El par de claves vockey que has seleccionado te permitirá conectarte a esta instancia mediante SSH después de que se haya iniciado. Aunque no tendrás que hacer eso en este laboratorio, sigue siendo necesario para identificar un par de claves existente, crear uno nuevo o al lanzar una instancia.

 

Tarea 5. Configuración de red
Junto a la configuración de red, selecciona Editar.

 

Mantén los ajustes predeterminados para VPC y subred. Mantén también el ajuste de Asignar automáticamente la IP pública como Habilitar.
La red indica la nube virtual privada (VPC) en la que quieres lanzar la instancia. Puede tener varias redes; por ejemplo, una para desarrollo, una segunda para pruebas y una tercera para producción.

En Firewall (grupos de seguridad), selecciona el valor predeterminado La opción  Crear grupo de seguridad está seleccionada.

 

Configura un nuevo grupo de seguridad:

Mantén la selección predeterminada Crear un nuevo grupo de seguridad.

Nombre del grupo de seguridad: borra el texto e introduce Web Server

Tarea 6. Configurar el almacenamiento
En la sección Configurar almacenamiento, mantén la configuración predeterminada

Tarea 7: Detalles avanzados
Configura un script para que se ejecute en la instancia cuando se inicie:

Expande el panel Detalles avanzados.

Desplázate hacia la parte inferior de la página y copia y pega el código que se muestra a continuación en la casilla Datos de usuario:

#!/bin/bash
yum update -y
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello World!</h1></html>' > /var/www/html/index.html

 Revisar la instancia y lanzarla
En la parte inferior del panel Resumen en la parte derecha de la pantalla, selecciona Lanzar instancia

Verás un mensaje de éxito.

 

Selecciona Ver todas las instancias

La instancia aparecerá primero en estado Pendiente, que significa que se está lanzando.



Acceder a la instancia de EC2
Cuando lanzaste la instancia de EC2, proporcionaste un script que instaló un servidor web y creó una página web sencilla. En esta tarea, intentarás acceder al contenido desde el servidor web.

 

En la pestaña Detalles, copia el valor de la Dirección IPv4 pública de la instancia en el portapapeles.

Tarea 10. Actualizar el grupo de seguridad
No puedes acceder al servidor web porque el grupo de seguridad no permite el tráfico entrante en el puerto 80, que se utiliza para las solicitudes web HTTP. En esta tarea, actualizarás el grupo de seguridad.

 

Vuelve a la pestaña del navegador de la Consola de administración de EC2.
En el panel de navegación izquierdo, en Red y seguridad, selecciona Grupos de seguridad.
Selecciona el grupo de seguridad Web Server que creaste al lanzar la instancia de EC2.
En el panel inferior, selecciona la pestaña Reglas de entrada.
Tarea 11: Crear una regla de entrada
Selecciona Editar reglas de entrada y, a continuación, selecciona Añadir regla.
Configura lo siguiente:

Tipo: HTTP
Fuente: Cualquier lugar-IPv4
Selecciona Guardar reglas
La nueva regla HTTP de entrada crea una entrada para las direcciones IP IPv4 IP (0.0.0.0/0) y IPv6 (::/0).

 

Tarea 12. Probar la regla
Vuelve a la pestaña que utilizaste para intentar conectarte al servidor web.
Actualiza la página.

Debería mostrar la página del servidor web con el mensaje Hello World!
Tarea 13: Adjuntar un volumen de EBS a la instancia de EC2
Vuelve a la pestaña del navegador de la Consola de administración de EC2.
En el panel de navegación izquierdo, en Instancias, selecciona Instancias

Selecciona la instancia Web Server y, en la pestaña Redes que aparece debajo, toma nota de la Zona de disponibilidad en la que se ejecuta la instancia.

El volumen de EBS que vas a crear pronto tendrá que estar en la misma zona de disponibilidad.

En el panel de navegación izquierdo, en Elastic Block Store, selecciona Volúmenes.

Selecciona Crear volumen.

En Tamaño, introduce 1 para crear un volumen con 1 GiB.

En Zona de disponibilidad, selecciona la misma zona de disponibilidad en la que se ejecuta la instancia de EC2.

 

Desplázate hacia abajo y selecciona Crear volumen

El nuevo volumen aparece en la lista de volúmenes con el estado disponible.
Selecciona el nuevo volumen con un tamaño de 1 GiB. A continuación, elige Acciones y Asociar volumen.
Selecciona el menú desplegable Instancia y selecciona tu instancia de EC2. La lista de instancias se rellenará automáticamente.
Selecciona Asociar volumen.

El estado del volumen cambia a en uso. El nuevo volumen se ha adjuntado a la instancia de EC2.


**Laboratorio completado**
