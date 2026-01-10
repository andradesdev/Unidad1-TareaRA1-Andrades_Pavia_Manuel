En este apartado se describen los principales elementos del lenguaje Python utilizados en la implementación de la aplicación Lavadero de Coches, así como el diseño del código y las decisiones tomadas durante su desarrollo.

## Clase Lavadero

La aplicación se basa en una clase orientada a objetos, lo que permite encapsular el estado y el comportamiento del lavadero en una única entidad.

``` class Lavadero: ```


Esta clase representa un túnel de lavado con control de:

Estados (fases del lavado)

Reglas de negocio

Ingresos económicos

Ocupación del lavadero

## Constantes de clase (Estados del autómata)

Se definen constantes para representar cada fase del lavado:

```
FASE_INACTIVO = 0
FASE_COBRANDO = 1
FASE_PRELAVADO_MANO = 2
FASE_ECHANDO_AGUA = 3
FASE_ENJABONANDO = 4
FASE_RODILLOS = 5
FASE_SECADO_AUTOMATICO = 6
FASE_SECADO_MANO = 7
FASE_ENCERADO = 8
```

El uso de constantes permite:

Evitar el uso de números mágicos.

Mejorar la legibilidad del código.

Facilitar la realización de pruebas unitarias.

Representar claramente el flujo de estados del sistema.

## Constructor __init__

El constructor inicializa el estado del lavadero:
```
def __init__(self):
    self.__ingresos = 0.0
    self.__fase = self.FASE_INACTIVO
    self.__ocupado = False
    self.__prelavado_a_mano = False
    self.__secado_a_mano = False
    self.__encerado = False
    self.terminar()
```

Se emplean atributos privados (prefijo __) para proteger el estado interno del objeto y evitar modificaciones externas indebidas.

## Encapsulación mediante @property

Para acceder a los atributos privados se utilizan propiedades:

```
@property
def ingresos(self):
    return self.__ingresos
```

Esto permite:

Mantener el principio de encapsulación.

Ofrecer acceso de solo lectura.

Evitar modificaciones directas desde el exterior.

## Método hacerLavado()

Este método inicia un nuevo ciclo de lavado y valida las reglas de negocio:

```
def hacerLavado(self, prelavado_a_mano, secado_a_mano, encerado):
```

Reglas implementadas:

No se puede iniciar un lavado si el lavadero está ocupado.

No se permite el encerado sin secado a mano.

Se utilizan excepciones (ValueError) para gestionar errores de uso incorrecto.

## Cálculo de ingresos _cobrar()

El método privado _cobrar() calcula el coste del lavado según las opciones seleccionadas:
```
coste_lavado = 5.00
```

Costes adicionales:

Prelavado a mano: +1.50 €

Secado a mano: +1.00 €

Encerado: +1.20 €

Este método actualiza los ingresos acumulados y devuelve el importe cobrado.

## Autómata de estados avanzarFase()

El método avanzarFase() controla la transición entre estados del lavadero:
```
def avanzarFase(self):
```

Características principales:

Implementa un autómata finito.

Decide la siguiente fase según las opciones seleccionadas.

Garantiza que el cobro se realice una sola vez.

Finaliza el ciclo llamando a terminar().

Cada estado conduce de forma controlada al siguiente, respetando el flujo definido en los requisitos de la práctica.

## Métodos de salida por consola

Se incluyen métodos auxiliares para mostrar información:

```imprimir_fase():``` muestra la fase actual del lavado.

```imprimir_estado():``` muestra el estado completo del lavadero (ingresos, ocupación y fase).

Estos métodos son útiles para depuración y demostraciones.

## Método auxiliar para pruebas unitarias
```
def ejecutar_y_obtener_fases(self, prelavado, secado, encerado):
```

Este método no forma parte del sistema real, pero se incluye para facilitar las pruebas unitarias.
Permite:

Ejecutar un ciclo completo de lavado.

Obtener una lista con las fases visitadas.

Detectar bucles infinitos mediante un límite de seguridad.