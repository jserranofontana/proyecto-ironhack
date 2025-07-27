# Proyecto Final Bootcamp Ironhack - Automatización de Procesos con IA

![Estado del Proyecto](https://img.shields.io/badge/estado-finalizado-green)
![Ironhack](https://img.shields.io/badge/bootcamp-Ironhack-blue)
![Make.com](https://img.shields.io/badge/automatización-Make.com-purple)

Este repositorio contiene todos los ficheros, análisis y escenarios de automatización desarrollados como parte del proyecto final del bootcamp de Ironhack. El objetivo principal del proyecto es demostrar la aplicación práctica de tecnologías de automatización e inteligencia artificial para resolver un problema de negocio real.

## 📝 Descripción del Proyecto

El proyecto se centra en la creación de un sistema automatizado para el procesamiento de facturas de proveedores. El flujo de trabajo completo se encarga de:
1.  **Recepción y clasificación** de correos electrónicos con facturas adjuntas.
2.  **Extracción de datos estructurados** de las facturas (PDF o imagen) utilizando IA (OCR e Invoice Parsing).
3.  **Búsqueda y validación** de proveedores en el ERP Odoo.
4.  **Registro automático** de la información en los sistemas correspondientes, como Google Sheets y el propio ERP.

Este sistema reduce drásticamente el tiempo de procesamiento manual, minimiza errores y crea un registro centralizado y accesible de todas las transacciones.

## 🛠️ Stack Tecnológico y Herramientas

* **Lenguaje de Programación**: Python
* **Plataforma de Automatización (iPaaS)**: [Make.com](https://www.make.com/)
* **Inteligencia Artificial (OCR / Parser)**: [Eden AI](https://www.edenai.co/)
* **ERP**: [Odoo](https://www.odoo.com/)
* **Almacenamiento y Colaboración**: Google Drive, Google Sheets
* **Control de Versiones**: Git y GitHub

## 📂 Estructura del Repositorio

El repositorio está organizado de la siguiente manera para facilitar la navegación y el entendimiento del proyecto.

├── documentación_proyecto/ # Contiene todos los documentos con la descripción del proyecto (CSV, etc.)
├── scenarios_make/         # Exportaciones (blueprints) de los escenarios de Make.com en formato .json.
├── proyecto IA.md          # Resumen ejecutivo del proyecto en formato MarkDown.
├── proyecto IA.html        # Resumen ejecutivo del proyecto en formato HTML.
├── proyecto IA.pdf         # Resumen ejecutivo del proyecto en formato PDF.

└── README.md               # Este mismo archivo.

## 🤖 Escenarios de Automatización en Make.com

La carpeta `scenarios_make/` contiene los blueprints de los flujos de trabajo de automatización. Para utilizarlos, debes importarlos en tu cuenta de Make.com.

### Escenarios Incluidos:

1.  **`1-recepcion-y-filtrado-adjuntos.json`**:
    * **Disparador**: Se activa al recibir un email en una cuenta de Gmail específica.
    * **Acción**: Filtra los correos para procesar solo aquellos que contienen adjuntos PDF o de imagen y los envía a la ruta correspondiente.

2.  **`2-extraccion-datos-factura-edenai.json`**:
    * **Disparador**: Recibe el fichero desde el escenario anterior.
    * **Acción**: Envía el fichero al módulo **Invoice Parser** de Eden AI. Espera el resultado y obtiene los datos estructurados de la factura (Nº de factura, total, fecha, proveedor, etc.).

3.  **`3-busqueda-y-registro-odoo.json`**:
    * **Disparador**: Recibe los datos extraídos por Eden AI.
    * **Acción**: Busca el proveedor en Odoo por su nombre. Si lo encuentra, registra los datos de la factura en Google Sheets y, opcionalmente, podría crear un borrador de factura en el ERP.

### Cómo importar los escenarios:

1.  En tu panel de Make.com, ve a la sección "Scenarios".
2.  Haz clic en "Create a new scenario".
3.  En el editor, haz clic en el menú de tres puntos (...) en la parte inferior central y selecciona **"Import Blueprint"**.
4.  Selecciona el fichero `.json` correspondiente desde la carpeta `scenarios_make/` de este repositorio.

## 🚀 Instalación y Uso Local

Si necesitas ejecutar los notebooks o scripts de Python de forma local, sigue estos pasos:

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/jserranofontana/proyecto-ironhack.git
    cd proyecto-ironhack
    ```

2.  **Crea en Make.com los escenarios acorde a los blueprints exportados**

3.  **Configura en Make.com las credenciales para los servicios utilizados.**

4.  **Configura la carpeta de Google Drive y la hoja de calculo de Google Sheet en base a lo indicado en la documentación del proyecto.**

5.  **Activa los escenarios de Make.com**

6.  **Comienza a procesar las facturas recibidas en la cuenta de correo configurada**

## 👤 Autor

* **J. Serrano Fontana**
* **GitHub**: [jserranofontana](https://github.com/jserranofontana)
* **LinkedIn**: `[Enlace a tu perfil de LinkedIn]`

## 🙏 Agradecimientos

A todo el equipo de **Ironhack** por su formación, apoyo y por proporcionar las herramientas necesarias para llevar a cabo este proyecto.