**Laboratorio del módulo 9: Creación de una alarma de CloudWatch que inicie un mensaje de Amazon SNS** 

**Tarea 1. Crear y suscribirse a un tema de SNS** 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.001.jpeg)

Selecciona el menú Servicios, localiza la sección Integración de aplicaciones y elige Simple Notification Service. 

En el panel de navegación izquierdo, selecciona **Temas** 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.002.jpeg)

Selecciona **Crear un tema**. 

Un tema actúa como un canal de comunicación donde se pueden publicar mensajes de alertas y eventos. 

En **Tipo**, selecciona **Estándar** 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.003.png)

En **Tipo**, selecciona **Estándar**. 

En **Nombre**, introduce MoneyAlert Selecciona **Crear un tema** 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.004.png)

Tarea 1. Crear y suscribirse a un tema de SNS

Selecciona el menú Servicios, localiza la sección Integración de aplicaciones y elige Simple Notification Service. 

En el panel de navegación izquierdo, selecciona Temas. 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.005.jpeg)

Tipo, selecciona Estándar. 

En **Nombre**, introduce **MoneyAlert** Selecciona Crear un tema. 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.006.jpeg)

**Tarea 2. Crear una alarma de CloudWatch.** 

selecciona el menú Servicios, localiza la sección Administración y gobernanza y elige CloudWatch. 

En el panel de navegación izquierdo, selecciona Alarmas. Selecciona Crear alarmas y después Crear alarma. 

Selecciona Seleccionar métrica. 

Selecciona Facturación. 

Selecciona Cargo total estimado. 

Marca la casilla EstimatedCharges. 

Selecciona Seleccionar métrica. 

En la sección Condiciones, configura lo siguiente: 

En Tipo de límite, selecciona Estático. 

En Siempre que EstimatedCharges sea..., selecciona Mayor. 

En que..., introduce 100 en el cuadro de texto. 

Selecciona Siguiente. 

En la sección Notificación, configura lo siguiente: 

`  `En Activador de estado de alarma, selecciona En modo alarma. 

`  `Para Enviar una notificación al siguiente tema de SNS, selecciona Seleccione un tema de SNS existente. 

`  `En Enviar una notificación a..., selecciona el tema MoneyAlert. Selecciona Siguiente. 

En Nombre de la alarma, escribe MoneyAlertAlarm 

Selecciona Siguiente. 

Revisa la configuración. Desplázate hacia abajo y selecciona Crear alarma 

![](Aspose.Words.0eb3e47b-f6a3-43ae-9c67-7bf8a9b69b43.007.jpeg)

**Laboratorio finalizado** 
