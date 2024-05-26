**Laboratorio 2 del módulo 4** 

**Creación de un bucket de S3** 

Crear un **bucket** de **S3** 

Selecciona el menú Servicios, localiza los servicios de Almacenamiento y selecciona S3. Selecciona **Crear bucket** en la parte derecha de la página.

En **Nombre del bucket**, introduce un nombre exclusivo compatible con el sistema de nombres de dominio (DNS) para el nuevo bucket.

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.001.jpeg)

Quita la marca de la casilla Bloquear *todo* el acceso público porque quieres verificar si el sitio web funciona. 

Debajo de la configuración de seguridad de la que quitaste la marca de selección, se muestra un mensaje de advertencia que dirá algo como Al desactivar el bloqueo de todo el acceso público, este bucket y los objetos se conviertan en públicos.

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.002.jpeg)Elige el enlace para el nombre del bucket y, a continuación, selecciona la pestaña **Permisos**. 

En la sección **Política de bucket**, selecciona **Editar**. 

Para conceder acceso de lectura pública a tu sitio web, copia la siguiente política de bucket y pégala en el editor de políticas.

En la política, reemplaza **example-bucket** por el nombre del bucket. Selecciona **Guardar cambios**. 

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.003.png)

**Subir un documento HTML** 

En esta tarea, subirás un documento HTML al nuevo bucket.

Abre el menú contextual (clic derecho) para el siguiente enlace y después selecciona **Guardar enlace como**: in[dex.html ](https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-ACCAIC-1-91563/02-lab-4.2-S3/s3/index.html)

Guarda el archivo index.html en el equipo local. En la consola, selecciona la pestaña **Objetos**. Carga el archivo index.html en tu bucket.

`    `Selecciona **Cargar**. 

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.004.jpeg)

**Probar el sitio web** 

Selecciona la pestaña **Propiedades** y desplázate a la sección **Alojamiento de sitios web estáticos**. 

Selecciona **Editar**. 

Selecciona **Habilitar**. 

En el cuadro de texto **Documento de índice**, introduce index.html. Selecciona **Guardar cambios**. 

Desplázate de nuevo hacia abajo hasta la sección **Alojamiento de sitios web estáticos** y copia la URL del **Punto de enlace de sitio web del bucket** en el portapapeles. 

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.005.jpeg)

Abre una nueva pestaña en el navegador web, pega la URL que acabas de copiar y pulsa **Intro**. 

Debería abrirse la página web **Hello World**. Has alojado correctamente un sitio web estático mediante un bucket de S3.

![](https://github.com/JohnJairoR/READMI/blob/main/Laboratorios_AWS/imagenes/Aspose.Words.fd0944bd-69fd-4711-8150-41cc3bfcc5e9.006.png)

**Laboratorio completado** 
