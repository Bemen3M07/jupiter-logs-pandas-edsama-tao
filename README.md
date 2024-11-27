[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ULiw8LbN)
# Empty
Repositori buit

# Contenido del README.md
readme_content = """
# Logging en Python

## Comparativa de formas de hacer logs

| **Forma**                                       | **Ejemplo**                                                                                              | **Ventajas**                                                                                                                              | **Desventajas**                                                                                                                            |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **Usando la configuración por defecto del módulo logging** | ```python\nimport logging\nlogging.warning('Esto es una advertencia')\n```                                  | - Fácil de usar.<br> - Ideal para scripts simples y rápidos.                                                                               | - Falta de flexibilidad.<br> - No permite personalizar fácilmente el formato o los manejadores.<br> - Difícil de escalar en proyectos grandes. |
| **Instanciando un objeto logger y configurándolo desde el programa** | ```python\nimport logging\nlogger = logging.getLogger('mi_logger')\nlogger.setLevel(logging.DEBUG)\n```      | - Totalmente configurable desde el código.<br> - Permite añadir múltiples manejadores y formateadores.<br> - Útil para proyectos personalizados. | - Requiere más líneas de código para configurar.<br> - Puede resultar complejo si se necesita configurar para diferentes entornos (desarrollo/producción). |
| **Instanciando un objeto logger a partir de una configuración almacenada en un archivo** | ```python\nimport logging.config\nlogging.config.fileConfig('logging.conf')\nlogger = logging.getLogger()\n``` | - Separa la configuración del código.<br> - Ideal para proyectos grandes o despliegues con diferentes entornos.<br> - Fácil de modificar sin tocar el código. | - Requiere aprender la sintaxis del archivo de configuración.<br> - Menos flexible para cambios rápidos durante la ejecución del programa.         |

## Notas
- Para proyectos pequeños, la configuración por defecto suele ser suficiente.
- Para aplicaciones más complejas o profesionales, es recomendable utilizar un objeto logger configurado programáticamente o mediante un archivo de configuración.
"""

# Escribir el contenido en un archivo README.md
with open("README.md", "w") as readme_file:
    readme_file.write(readme_content)

# Librerías de Logging en Diferentes Lenguajes

Este documento describe y compara dos librerías de logging, una para Python y otra para JavaScript. Se detallan las características típicas de cada librería para facilitar su uso.

| **Característica**                  | **Python** (`logging`)                                                                                       | **JavaScript** (`Winston`)                                                                                                            |
|-------------------------------------|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| **Lenguaje**                        | Python                                                                                                       | JavaScript                                                                                                                            |
| **Nombre de la librería**           | `logging`                                                                                                    | `winston`                                                                                                                             |
| **¿Es nativa del lenguaje?**        | Sí                                                                                                           | No                                                                                                                                    |
| **URL para descargar la librería**  | [https://docs.python.org/3/library/logging.html](https://docs.python.org/3/library/logging.html)             | [https://github.com/winstonjs/winston](https://github.com/winstonjs/winston)                                                         |
| **Inicialización del objeto logger** | `logger = logging.getLogger(__name__)`                                                                       | ```javascript const winston = require('winston'); const logger = winston.createLogger({}); ```                                         |
| **Niveles de log disponibles**      | DEBUG, INFO, WARNING, ERROR, CRITICAL                                                                        | error, warn, info, http, verbose, debug, silly                                                                                       |
| **Método para hacer log**           | `logger.info('Mensaje de prueba')`                                                                           | `logger.log({ level: 'info', message: 'Mensaje de prueba' });`                                                                        |
| **Tipos de manejadores (pantalla, archivo, etc.)** | `StreamHandler`, `FileHandler`, `SMTPHandler`, `SysLogHandler`                                               | Console (`winston.transports.Console`), File (`winston.transports.File`), HTTP (`winston.transports.Http`)                            |
| **Opciones de formato**             | `logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')`                                   | ```javascript new winston.format.combine(winston.format.timestamp(), winston.format.simple()) ```                                     |

## Resumen

1. **Python**: `logging` es una librería nativa que ofrece gran flexibilidad con múltiples tipos de manejadores, opciones de formato y soporte para diferentes niveles de logs.
2. **JavaScript**: `winston` es una librería poderosa que permite configurar transportes versátiles y personalizables para enviar logs a diferentes destinos.
