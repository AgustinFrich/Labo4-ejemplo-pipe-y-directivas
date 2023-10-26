# Pipe y Directivas

## Pipe

- Los pipes nos permiten filtrar información, por eso se llaman tuberías.
- Sirven para modificar cadenas, importes de moneda, fechas y otros datos para su visualización.
- Solo los modifican para mostrarlos, es algo puramente visual.
- Esto se realiza a través de la función transform, que recibe como value un string y también puede recibir argumentos
  a través de una variable ...args.

Con esto, podemos usar los pipes que ya trae angular como:

- UpperCasePipe: Transforma el texto a mayúsculas.
- DecimalPipe: Transforma un número en una cadena con un punto decimal, formateada según las reglas locales.
  etc.

Pueden encontrar el resto en la guía de Angular.

Aquí vemos un ejemplo de cómo utilizar el UpperCasePipe

```
<h3>Transformar a mayusculas: {{ minusculas | uppercase }}</h3>
```

El ejemplo de pipes/fecha.pipe.ts recibe una fecha y devuelve un string que comunica hace cuánto fue esa fecha,
ideal para comunicar la última vez que alguien se conectó.

Separamos la lógica de visualización, no hay necesidad de guardar estos datos ya que cambian a cada minuto.

podemos aplicar varios pipe al mismo tiempo con solo agregar otro pipe |

```
{{ variable | uppercase | otropipe }}
```

Para pasar valores, usamos los ":" y luego el valor que le queremos agregar. Si queremos seguir agregando valores, agregamos ":" y otro valor o variable.

```
{{ valorInicial | miPipe : "valor1" : "valor2" : variable3 }}
```

Todos estos parámetros se almacenan en el array "...args" de la función transform.

## Directivas

https://angular.io/guide/attribute-directives

Ya habíamos visto las directivas estructurales que trae Angular: ngIf, ngFor, ngSwitch
Vimos también algunas directivas de estilo como ngStyle, ngClass.

Lo que vamos a ver hoy son las directivas de atributos, las cuales nos permiten modificar la **apariencia y/o comportamiento del DOM**.
ng generate directive directives/resaltar

En esta directiva vamos a ver cómo manipular el dom para que un elemento de nuestro HTML, CUALQUIERA, se modifique para reslatar el texto que contiene.

Particularidades: Las directivas pueden recibir datos por Input (misma sintaxis que los componentes) y utilizarlos para modificar distintos aspectos.

- Para que revisen: ¿Puedo emitir información con Output?

El selector es el nombre del atributo que colocamos en las tag html:

```
<h3 miDirectiva [parametroInputDeMiDirectiva]="datoQueLeEnvio">...</h3>
```
