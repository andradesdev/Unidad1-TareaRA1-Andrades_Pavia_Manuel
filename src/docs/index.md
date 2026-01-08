# Lavadero de Coches – Unidad 1

## Elementos de Python
En esta práctica se ha desarrollado una aplicación en Python que simula el funcionamiento de un lavadero de coches mediante un autómata de estados.

El código fuente se encuentra en la carpeta `src/`, donde se definen:
- La clase `Lavadero`
- Las fases del lavado
- El control de ingresos
- Las reglas de negocio

➡️ Ver más detalles en la sección *Elementos de Python*.

---

## Ejecución y Depuración
Durante la ejecución y depuración se detectaron varios errores:
- Errores en el cálculo de ingresos
- Errores en la transición entre fases
- Excepciones incorrectas

Estos errores se solucionaron utilizando breakpoints y ejecución paso a paso en Visual Studio Code.

Se adjuntan capturas de pantalla a pantalla completa mostrando el terminal y el entorno de desarrollo.

---

## Pruebas
Se han desarrollado pruebas unitarias con `unittest` para validar:
- Estado inicial del lavadero
- Reglas de negocio
- Cálculo de ingresos
- Flujo correcto de fases

Las pruebas permitieron detectar errores que fueron corregidos posteriormente.

---

## Ejecución en Sandbox
La aplicación se ha ejecutado en un entorno aislado utilizando **Firejail** en una máquina virtual Ubuntu.

Esto permite limitar el acceso al sistema y mejorar la seguridad durante la ejecución.

---

## Reflexión sobre Seguridad
Finalmente, se realiza una reflexión sobre las medidas de seguridad de Python en comparación con otros lenguajes como Java o C++, destacando la importancia del entorno de ejecución.
