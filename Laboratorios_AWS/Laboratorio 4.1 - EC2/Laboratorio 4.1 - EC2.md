**LABORATORIO 4.1 AWS** 

**Acceso a la consola de administración de AWS**

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.001.png)

Para comenzar la sesión de laboratorio, selecciona **Start Lab** (Iniciar laboratorio) en la esquina superior derecha de la página

Selecciona el menú **Servicios**, localiza los servicios de **Computación** y selecciona **EC2**. Selecciona el botón **Lanzar instancia** en medio de la página y luego selecciona **Lanzar** 

**instancia** en el menú desplegable. 

` `Pon un nombre a la instancia:

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.002.png)

` `**Imágenes de aplicación y SO** 

Selecciona una AMI a partir de la cual crear la instancia:

En la lista de AMI disponibles de *Quick Start*, mantén la AMI predeterminada de **Amazon Linux** seleccionada. 

Además, mantén seleccionada la **Amazon Linux 2023 AMI x86\_64 (HVM)** predeterminada 

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.003.jpeg)

**Elegir el tipo de instancia** 

Especifica un tipo de instancia: 

En el panel *Tipo de instancia*, mantén el tipo predeterminado **t2.micro** seleccionado. 

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.004.png)

**Detalles avanzados** 

Configura un script para que se ejecute en la instancia cuando se inicie: Expande el panel **Detalles avanzados**. 

Desplázate hacia la parte inferior de la página y copia y pega el código que se muestra a continuación en la casilla **Datos de usuario**: 

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.005.png)

Selecciona la instancia **Web Server 1** y revisa la información de la pestaña **Detalles** que se muestra en el panel inferior. 

Observa que la instancia tiene una **dirección DNS de IPv4 pública**. Puedes utilizar esta dirección IP para comunicarte con la instancia desde Internet.

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.006.jpeg)

**Actualizar el grupo de seguridad** 

No puedes acceder al servidor web porque el grupo de seguridad no permite el tráfico entrante en el puerto 80, que se utiliza para las solicitudes web HTTP. En esta tarea, actualizarás el grupo de seguridad.

` `Vuelve a la pestaña del navegador de la **Consola de administración de EC2**. 

` `En el panel de navegación izquierdo, en **Red y seguridad**, selecciona **Grupos de seguridad**. 

` `Selecciona el grupo de seguridad **Web Server** que creaste al lanzar la instancia de EC2.  En el panel inferior, selecciona la pestaña **Reglas de entrada**. 

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.007.png)

**Probar la regla** 

Vuelve a la pestaña que utilizaste para intentar conectarte al servidor web.  Actualiza la página. 

¡Debería mostrar la página del servidor web con el mensaje **Hello World!** 

![](Aspose.Words.842530a6-6b73-4834-bfeb-1cee7bc60cb9.008.png)

**Laboratorio Finalizado** 
