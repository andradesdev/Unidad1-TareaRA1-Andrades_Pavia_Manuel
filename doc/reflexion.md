En este apartado se presenta una reflexión personal sobre las medidas de seguridad que incorporan los distintos lenguajes de programación, basándome tanto en los contenidos teóricos vistos en la asignatura como en la experiencia práctica adquirida durante el desarrollo de esta tarea.

## Seguridad como parte del lenguaje

Uno de los aspectos más relevantes que he aprendido es que la seguridad no depende únicamente del usuario, sino también del lenguaje y su infraestructura de ejecución.

Los lenguajes modernos incorporan mecanismos que ayudan a prevenir errores comunes y vulnerabilidades, como:

- Gestión automática de memoria.

- Tipado seguro.

- Manejo de excepciones.

- Restricciones de acceso a recursos del sistema.

Sin embargo, ningún lenguaje es completamente seguro por sí solo; la seguridad real surge de la combinación entre lenguaje, entorno de ejecución y buenas prácticas.

## Python y su infraestructura de seguridad

Python es un lenguaje de alto nivel que prioriza la legibilidad y la productividad. Desde el punto de vista de la seguridad, ofrece varias ventajas:

- Gestión automática de memoria, evitando errores como buffer overflows.

- Sistema de excepciones, que permite controlar errores de forma explícita.

- Encapsulación y propiedades, como se ha utilizado en la clase Lavadero.

- Gran ecosistema de herramientas para pruebas, análisis y seguridad.

Durante esta práctica, Python ha demostrado ser un lenguaje seguro y adecuado para desarrollar aplicaciones, siempre que se utilice correctamente.

No obstante, Python también presenta limitaciones: Permite operaciones potencialmente peligrosas si no se controlan (acceso a archivos, ejecución de comandos, etc.). Por este motivo, ha sido especialmente importante complementar el lenguaje con pruebas unitarias y ejecución en sandbox.

## Comparación con otros lenguajes

Lenguajes como C o C++ ofrecen un control total sobre la memoria y el sistema, pero esto supone un mayor riesgo de seguridad:

- Gestión manual de memoria.

- Vulnerabilidades comunes como desbordamientos de búfer.

- Mayor probabilidad de errores críticos.

Aunque son muy potentes, requieren un nivel de experiencia mucho mayor para desarrollar aplicaciones seguras.

Lenguajes como Java o C# incorporan máquinas virtuales (JVM, CLR) que añaden una capa extra de seguridad:

- Gestión automática de memoria.

- Verificación de bytecode.

- Control de acceso y permisos.

Estos lenguajes suelen ser más seguros por defecto, aunque a costa de mayor complejidad y consumo de recursos.

## Relación con la práctica realizada

Durante el desarrollo de esta tarea he aplicado varias medidas de seguridad que refuerzan el uso del lenguaje:

- Encapsulación de atributos en la clase Lavadero.

- Validación de reglas de negocio mediante excepciones.

- Pruebas unitarias para detectar errores de lógica.

- Ejecución en Sandbox con Firejail, aislando la aplicación del sistema.

Esto demuestra, como he dicho antes, que la seguridad no depende solo del lenguaje, sino de cómo se utiliza y del entorno en el que se ejecuta.
