**Introducción a IAM**

Tarea 1. Explorar usuarios y grupos
En esta tarea, explorarás los usuarios y los grupos que ya se han creado para ti en IAM.

En primer lugar, toma nota de la región en la que te encuentras; por ejemplo, N. Virginia. La región se muestra en la esquina superior derecha de la página de la consola.

Es posible que necesites esta información más adelante en el laboratorio.
Selecciona el menú Servicios, localiza los servicios de Seguridad, identidad y conformidad y selecciona IAM.
En el panel de navegación de la izquierda, elige Usuarios.
Ya Se han creado los siguientes usuarios de IAM:

user-1
user-2
user-3
Selecciona el nombre user-1.
En el panel de navegación de la izquierda, selecciona Grupos de usuarios.
Elige el nombre del grupo S3-Support.
Selecciona la pestaña Permisos.
El grupo S3-Support tiene la política AmazonS3ReadOnlyAccess asociada.
En Nombre de la política, elige el enlace de la política AmazonS3ReadOnlyAccess.
Selecciona la pestaña {} JSON.
Esta política tiene permisos para obtener y enumerar todos los recursos en Amazon S3.
En el panel de navegación de la izquierda, selecciona Grupos de usuarios.

Elige el nombre del grupo EC2-Admin.
Selecciona la pestaña Permisos.
Este grupo es diferente de los otros dos. En lugar de una política administrada, el grupo tiene una política insertada, que es una política asignada a un solo usuario o grupo. Las políticas insertadas, generalmente, se usan para asignar permisos en situaciones específicas.

En Nombre de la política, elige el nombre de la política EC2-Admin-Policy.
Selecciona la pestaña JSON.
Esta política concede permiso para Describir información acerca de instancias de Amazon EC2 y también la capacidad de Iniciar y Detener instancias.
En la parte inferior de la pantalla, selecciona Cancelar para cerrar la política

Tarea 2. Añadir usuarios a grupos
Recientemente, has contratado al user-1 para un rol en el que presta soporte a Amazon S3. Añadirás a este usuario al grupo S3-Support para que herede los permisos necesarios mediante la política AmazonS3ReadOnlyAccess asociada.
Haz caso omiso de los errores de tipo "no autorizado" que aparezcan durante esta tarea. Se deben a que la cuenta del laboratorio tiene permisos limitados, pero no afectarán a tu capacidad para completar el laboratorio.
Añadir a user-1 al grupo S3-Support
En el panel de navegación izquierdo, selecciona Grupos de usuarios.

Elige el nombre del grupo S3-Support.
En la pestaña Usuarios, elige Añadir usuarios.
Selecciona  user-1 y después Añadir usuarios.
En la pestaña Usuarios, observa que user-1 se ha añadido al grupo.

Añadir a user-2 al grupo EC2-Support
Has contratado a user-2 para un rol en el que presta soporte a Amazon EC2. Lo añadirás al grupo EC2-Support para que pueda heredar los permisos necesarios mediante la política AmazonEC2ReadOnlyAccess adjunta
Obtener la URL de inicio de sesión de la consola
En el panel de navegación de la izquierda, selecciona Panel.
Observa la sección URL de inicio de sesión para los usuarios de IAM de esta cuenta en la parte superior de la página. La URL de inicio de sesión tiene un aspecto similar al siguiente: https://123456789012.signin.aws.amazon.com/console
Este enlace se puede utilizar para iniciar sesión en la cuenta de AWS que utilizas actualmente.
Copia el enlace de inicio de sesión en un editor de texto.
Probar permisos de user-1
Abre una ventana privada o de incógnito en el navegador.
Pega el enlace de inicio de sesión en el navegador privado y pulsa INTRO.
Ahora iniciarás sesión como user-1, que ha sido contratado como personal de apoyo de almacenamiento de Amazon S3.
Inicia sesión con las siguientes credenciales:
Nombre de usuario de IAM: user-1
Contraseña: Lab-Password1
Selecciona el menú Servicios y luego S3.
Elige el nombre de uno de los buckets y explora el contenido

Probar permisos de user-2
Vuelve a pegar el enlace de inicio de sesión en el navegador privado y pulsa INTRO.
Inicia sesión con las siguientes credenciales:
Nombre de usuario de IAM: user-2
Contraseña: Lab-Password2
Selecciona el menú Servicios y después EC2.
En el panel de navegación de la izquierda, selecciona Instancias.
Ahora puedes ver una instancia de EC2. Sin embargo, no puedes realizar ningún cambio en los recursos de Amazon EC2 porque tienes permisos de solo lectura.
Si no ves una instancia de EC2, es posible que la región sea incorrecta. En la esquina superior derecha de la página, elige el nombre de la región y, a continuación, elige la región en la que te encontrabas al principio del laboratorio (por ejemplo, N. Virginia).
Selecciona la instancia de EC2.
Selecciona el menú Estado de la instancia y, a continuación, selecciona Detener instancia.

Probar permisos de user-3

Vuelve a pegar el enlace de inicio de sesión en el navegador privado y pulsa INTRO.
Inicia sesión con las siguientes credenciales:
Nombre de usuario de IAM: user-3
Contraseña: Lab-Password3
Selecciona el menú Servicios y después EC2.
En el panel de navegación de la izquierda, selecciona Instancias

**Laboratorio completado**
