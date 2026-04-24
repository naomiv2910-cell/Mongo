# Gestión de Estudiantes con MongoDB Atlas y Python

Este proyecto es una aplicación de consola en Python que permite gestionar una base de datos de estudiantes almacenada en MongoDB Atlas. Utiliza la librería `pymongo` para interactuar con la base de datos, ofreciendo funcionalidades CRUD (Crear, Leer, Actualizar, Eliminar) a través de un menú interactivo.

## Características

*   **Conexión Segura**: Se conecta a una base de datos en la nube de MongoDB Atlas.
*   **Insertar Estudiantes**: Permite añadir nuevos registros de estudiantes con nombre, edad y carrera.
*   **Listar Estudiantes**: Muestra todos los estudiantes almacenados en la base de datos.
*   **Actualizar Edad**: Modifica la edad de un estudiante existente.
*   **Eliminar Estudiantes**: Borra registros de estudiantes de la base de datos.
*   **Menú Interactivo**: Interfaz de usuario simple basada en consola para facilitar la interacción.

## Tecnologías Utilizadas

*   **Python 3.x**
*   **PyMongo**: Driver oficial de MongoDB para Python.
*   **MongoDB Atlas**: Servicio de base de datos en la nube.

## Configuración del Proyecto

Sigue estos pasos para poner en marcha el proyecto en tu entorno local:

### 1. Clona el Repositorio (o descarga el notebook)

Si estás usando este código en un repositorio de GitHub, clónalo:

```bash
git clone <URL_DE_TU_REPOSITORIO>
cd <NOMBRE_DE_TU_REPOSITORIO>
```

Si estás usando Google Colab, simplemente ejecuta las celdas en el orden en que aparecen.

### 2. Instala las Dependencias

Asegúrate de tener `pymongo` instalado. Puedes instalarlo usando `pip`:

```bash
pip install --upgrade pymongo
```

### 3. Configura tu Cadena de Conexión de MongoDB Atlas

Necesitarás una cuenta de MongoDB Atlas y una base de datos configurada. Una vez que tengas tu cluster, obtén tu cadena de conexión (URI de conexión):

1.  Inicia sesión en tu cuenta de [MongoDB Atlas](https://cloud.mongodb.com/).
2.  Navega a tu Cluster.
3.  Haz clic en 'Connect'.
4.  Selecciona 'Connect your application'.
5.  Copia la cadena de conexión. Asegúrate de reemplazar `<username>` y `<password>` con tus credenciales reales, y opcionalmente `<dbname>` con el nombre de tu base de datos.

**Actualiza el código**: En la celda donde se define `cliente = MongoClient(...)`, reemplaza la cadena de conexión existente con la tuya:

```python
cliente = MongoClient("mongodb+srv://<username>:<password>@cluster0.kgm2etf.mongodb.net/?retryWrites=true&w=majority")
```

**¡Importante!** Asegúrate de que el usuario de la base de datos que usas tenga los permisos adecuados (lectura y escritura) sobre la base de datos y colecciones que vas a manipular (`BD_CursoMongo` y `Estudiantes` en este caso).

## Uso

Una vez configurado y con las dependencias instaladas, ejecuta el notebook (o el script de Python si lo has extraído). El programa presentará un menú interactivo en la consola:

```
--- MENÚ DE ESTUDIANTES ---
1. Insertar estudiante
2. Listar estudiantes
3. Actualizar edad de un estudiante
4. Eliminar estudiante
5. Salir
Seleccione una opción: 
```

Simplemente ingresa el número de la opción que deseas realizar y sigue las instrucciones.

### Ejemplo de Interacción

1.  Selecciona `1` para insertar un estudiante.
    *   `Ingrese el nombre del estudiante: Kevin Luengas`
    *   `Ingrese la edad del estudiante: 20`
    *   `Ingrese la carrera del estudiante: Ciencia de datos`
    *   `Estudiante Kevin Luengas insertado.`

2.  Selecciona `2` para listar estudiantes.
    *   `Listado de estudiantes:`
    *   `{'_id': ObjectId('...'), 'nombre': 'Kevin Luengas', 'edad': 20, 'carrera': 'Ciencia de datos'}`

3.  Selecciona `5` para salir del programa.
    *   `Saliendo del programa.`

## Estructura del Código

El código está organizado en funciones para cada operación CRUD:

*   `insertar_estudiante(nombre, edad, carrera)`: Añade un nuevo estudiante.
*   `listar_estudiantes()`: Recupera y muestra todos los estudiantes.
*   `actualizar_edad(nombre, nueva_edad)`: Actualiza la edad de un estudiante por su nombre.
*   `eliminar_estudiante(nombre)`: Elimina un estudiante por su nombre.
*   `menu_estudiantes()`: La función principal que muestra el menú y maneja las interacciones del usuario.

## Contribuciones

Las contribuciones son bienvenidas. Si encuentras un error o tienes una sugerencia de mejora, por favor, abre un 'issue' o envía un 'pull request'.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
