# Taller de S3

## 1. Clonar y Editar el Repositorio
- **Paso 1: Clonar el repositorio.**
    - Abrir una terminal y ejecutar el siguiente comando para clonar el repositorio:
        ```sh
        git clone https://github.com/usuario/taller-s3.git
        ```
    - Navegar al directorio del repositorio clonado:
        ```sh
        cd taller-s3
        ```
- **Paso 2: Editar los archivos del repositorio.**
    - Abrir el proyecto en tu editor de código (por ejemplo, VSCode):
        ```sh
        code .
        ```
    - Realizar las modificaciones necesarias en los archivos `index.html`, `style.css`, y `app.js`.
    - Guardar los cambios y confirmar que todo funciona correctamente.

## 2. Creación del Bucket S3
- **Paso 3: Acceder a la consola de AWS.**
    - Mostrar cómo crear un bucket en S3:
        - Navegar a la sección "S3" y hacer clic en "Crear bucket".
        - Asignar un nombre único al bucket.
        - Elegir una región cercana.
        - Desactivar el bloqueo de acceso público y confirmar (ya que queremos que sea accesible).
        - Mantener otras configuraciones predeterminadas y crear el bucket.
    - Explicar la importancia de elegir nombres únicos y la región del bucket.

## 3. Configurar el Bucket para Páginas Web
- **Paso 4: Configurar el bucket para alojar una página web estática.**
    - En las propiedades del bucket, ir a la sección "Propiedades" y habilitar la opción "Alojamiento de sitio web estático".
    - Especificar `index.html` como la página de inicio y (opcionalmente) `error.html` para manejar errores.
    - Explicar qué son el documento de índice y el documento de error.

## 4. Diseñar la Página Web
- **Paso 5: Crear una página web simple.**
    - Abre tu editor de código (VSCode).
    - Explicar brevemente cómo crear los archivos `index.html`, `style.css`, y `app.js` básicos.
    - Explicación:
        - Resalta la estructura básica del HTML y cómo el CSS y JavaScript están vinculados.
        - Modificaciones sencillas de estilo o interactividad para personalizar.

## 5. Subir los Archivos a S3
- **Paso 6: Cargar los archivos creados a S3.**
    - En la consola de AWS, ir al bucket recién creado y subir los archivos `index.html`, `style.css` y `main.js` (consola o AWS CLI).
    - Mencionar la importancia de gestionar permisos de archivo.

## 6. Hacer Pública la Página Web
- **Paso 7: Asegurar que los archivos sean accesibles públicamente.**
    - Cambiar las políticas de acceso del bucket para que todos los archivos sean públicos:
        - Configurar políticas en la pestaña "Permisos", añadiendo una política de bucket que permita acceso público:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::pagina-web-estatica/*"
        }
    ]
}
```
    - Consejo: Explicar las implicaciones de la política y por qué es necesaria.

## 7. Ver la Página en Vivo
- **Paso 8: Obtener la URL del bucket.**
    - Mostrar cómo encontrar la URL pública en la configuración del bucket de S3.
    - Probar accediendo a la página desde el navegador.

