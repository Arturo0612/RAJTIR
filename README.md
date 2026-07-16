# RAJTIR - MICRAS

Sistema de escritorio para la gestión de un negocio (MICRAS), desarrollado en Python con interfaz gráfica en Tkinter y base de datos MySQL. Permite administrar movimientos/ventas, empleados, productos, proveedores y comisiones, además de generar recibos en PDF.

## Características principales

- **Movimientos**: registro de ventas/apartados y generación automática de recibos en PDF.
- **Empleados**: gestión del personal del negocio.
- **Productos**: alta, edición y consulta de productos, asociados a un proveedor.
- **Proveedores**: administración de proveedores.
- **Comisiones**: cálculo automático de comisión (5%) por venta/apartado registrado.
- **Interfaz gráfica** en modo oscuro, organizada en pestañas (una por módulo).

## Tecnologías utilizadas

- **Python 3**
- **Tkinter / ttk** — interfaz gráfica de escritorio.
- **MySQL** (`mysql-connector-python`) — base de datos del negocio.
- **ReportLab** — generación de recibos en PDF.

## Estructura del proyecto

```
├── main.py              # Punto de entrada; arma la ventana principal y las pestañas
├── movimientos.py        # Módulo de movimientos/ventas y generación de recibos PDF
├── empleados.py          # Módulo de gestión de empleados
├── productos.py          # Módulo de gestión de productos
├── proveedores.py        # Módulo de gestión de proveedores
├── comisiones.py         # Módulo de cálculo y consulta de comisiones
├── mysqlconn.py          # Conexión a la base de datos MySQL
├── db/
│   └── rajtirdb.sql      # Esquema de la base de datos
├── recursos/
│   └── logo_RAJTIR.png   # Logo usado en la interfaz
└── recibos/               # Recibos en PDF generados por la app
```

## Instalación y ejecución

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/new_rajtir.git
   cd new_rajtir
   ```

2. Instala las dependencias:
   ```bash
   pip install mysql-connector-python reportlab
   ```

3. Crea la base de datos en MySQL e impórtala desde el esquema incluido:
   ```bash
   mysql -u root -p -e "CREATE DATABASE rajtir"
   mysql -u root -p rajtir < db/rajtirdb.sql
   ```

4. Configura la conexión en `mysqlconn.py` con tu usuario y contraseña de MySQL:
   ```python
   conexion = mysql.connector.connect(
       host="localhost",
       user="root",
       password="tu_contraseña",
       database="rajtir"
   )
   ```

5. Ejecuta la aplicación:
   ```bash
   python main.py
   ```

## Notas

- ⚠️ El archivo `mysqlconn.py` no debería subirse con credenciales reales a un repositorio público. Se recomienda usar variables de entorno o un archivo de configuración excluido con `.gitignore`.
- Los recibos generados se guardan localmente en la carpeta `recibos/`.

## Autor

**Arturo** — Estudiante de Ingeniería en Tecnología de Software, FIME-UANL
[GitHub](https://github.com/Arturo0612)

## Licencia

Proyecto de uso académico.
