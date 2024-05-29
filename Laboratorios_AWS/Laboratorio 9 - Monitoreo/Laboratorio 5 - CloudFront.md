﻿**Laboratorio del módulo 9: Creación de una alarma de CloudWatch que inicie un mensaje de Amazon SNS** 

**Tarea 1. Crear un bucket de S3 mediante AWS CLI** 

En esta tarea, crearás un bucket de S3 mediante la Interfaz de la línea de comandos de AWS (AWS CLI). AWS CLI es una herramienta de código abierto que puedes utilizar para interactuar con los servicios de AWS mediante comandos en tu shell de línea de comandos. 

Elige **Servicios** y **Herramientas para desarrolladores** y, después, **CloudShell**. Si aparece una ventana emergente de bienvenida, selecciona **Cerrar**. 

AWS CloudShell es un shell basado en navegador que da acceso a la línea de comandos para los recursos de AWS en la región de AWS seleccionada.

Copia y pega el siguiente código en un editor de texto:

**cd ~** 

**aws s3api create-bucket --bucket (bucket-name) --region us-east-1** 

Selecciona la pestaña **Permisos**. En **Bloquear acceso público (configuración del bucket)**, selecciona **Editar**. Desactiva la casilla de **Bloquear todo el acceso público**. Elige **Guardar cambios**. Confirma los cambios. 

Desplázate hasta **Propiedad del objeto** y selecciona **Editar**. Selecciona **ACL habilitadas**. Comprueba el reconocimiento y, selecciona **Guarda** 

![](![image](https://github.com/JohnJairoR/READMI/assets/152223886/a5b5dd3c-dba9-4ef1-a506-283196755c39)
)

**Tarea 2. Añadir una política de bucket** 

En esta tarea, añadirás una política de bucket a través de AWS CLI para que el contenido esté disponible públicamente.

En la consola, selecciona el menú **Servicios**, localiza la sección **Almacenamiento** y elige **S3**. 

Elige el nombre del bucket que acabas de crear.

Selecciona la pestaña **Permisos**. En **Bloquear acceso público (configuración del bucket)**, selecciona **Editar**. Desactiva la casilla de **Bloquear todo el acceso público**. Elige **Guardar cambios**. Confirma los cambios. 

Desplázate hasta **Propiedad del objeto** y selecciona **Editar**. Selecciona **ACL habilitadas**. Comprueba el reconocimiento y, selecciona **Guardar cambios**. 

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.002.jpeg)

Desplázate hasta **Propiedad del objeto** y selecciona **Editar**. Selecciona **ACL habilitadas**. Comprueba el reconocimiento y, selecciona **Guardar cambios**. 

En la sección **Política del bucket**, selecciona **Editar**. 

Para conceder acceso de lectura pública a tu sitio web, copia y pega la siguiente política del bucket en el editor de políticas.

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.003.jpeg)

**Tarea 3. Subir un documento HTML** 

En esta tarea, subirás el archivo index.html de tu página web en el bucket de S3.

Abre el menú contextual (haz clic con el botón derecho) del siguiente enlace y, a continuación, elige **Save link as** (Guardar enlace como): ind[ex.html ](https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-ACCAIC-1-91563/03-lab-5-cloudfront/s3/index.html)

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.004.jpeg)

**Tarea 4. Probar el sitio web** 

Selecciona la pestaña **Propiedades** y desplázate a la sección **Alojamiento de sitios web estáticos**. 

Selecciona **Editar**. 

Selecciona **Habilitar**. 

En el cuadro de texto **Documento de índice**, introduce "index.html" 

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.005.png)

**Tarea 5. Crear una distribución de CloudFront para servir al sitio web** 

En esta tarea, crearás una distribución de Amazon CloudFront para servir al sitio web.

Selecciona el menú **Servicios**, localiza la sección **Redes y entrega de contenido** y selecciona **CloudFront**. 

Selecciona **Crear una distribución de CloudFront** 

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.006.jpeg)

Para **Viewer Protocol Policy** (Política de protocolo de visor), asegúrate de que **HTTP y HTTPS** estén seleccionados. En **Web Application Firewall (WAF)**, selecciona **Do not enable security protections** (No habilitar protecciones de seguridad).

Desplázate hasta la parte inferior de la página y selecciona **Crear distribución**. 

Se muestra una nueva distribución de CloudFront en la lista de distribuciones. 

El **Estado** será *Implementando* hasta que el sitio web se haya distribuido. Puede tardar hasta 20 minutos. 

Cuando el **Estado** sea *Habilitado*, puedes probar la distribución.

Copia el valor de **Nombre de dominio** de la distribución y guárdalo en un editor de texto para utilizarlo en un paso posterior

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.007.jpeg)

- Reemplaza **domain-name** por el nombre de dominio que copiaste antes para la distribución de CloudFront. 
- Reemplaza **object-name** por el nombre del archivo de imagen que cargaste en el bucket de S3. 

  La línea de código editada debe tener un aspecto similar al siguiente: <p><img  

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.008.png)

Guarda el archivo de texto con extensión HTML. 

Utiliza un navegador de Internet para abrir el archivo HTML que acabas de crear.

Si se muestra la imagen que cargaste, la distribución de CloudFront se realizó correctamente. Si no es así, repite el laboratorio.

![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.009.jpeg)

**Laboratorio completado![](Aspose.Words.a6ce0c63-8f8d-442b-8b3f-8ad4382bfa0d.010.png)**