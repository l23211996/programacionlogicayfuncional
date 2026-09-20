# Anexo — Bitácora de uso de LLM

## 1. Uso de inteligencia artificial

Para la elaboración de esta práctica se utilizó un modelo de lenguaje (LLM) como herramienta de apoyo para comprender los conceptos básicos del lenguaje de programación **Erlang** y desarrollar una primera práctica de **Hola Mundo**.

La inteligencia artificial se utilizó principalmente para comprender la estructura de un programa en Erlang, el funcionamiento de los módulos, la exportación de funciones, la función `io:format` y el proceso de compilación y ejecución mediante la consola interactiva de Erlang (Eshell).

La información obtenida fue revisada y comprendida antes de utilizarla en la práctica.

---

## 2. Prompts utilizados

### Prompt 1

> “Como puedo empezar hacer practicas con Erlang y que me salgan bien porque la verdad esta medio raro. Estoy acostumbrado a otro tipo de programacion como C#, Python, Java/JavaScript.”

**Resultado obtenido:**

El LLM explicó que Erlang utiliza un enfoque diferente al de lenguajes como C#, Python, Java y JavaScript. Se recomendó comenzar con ejercicios sencillos para comprender progresivamente conceptos como variables, funciones, listas, tuplas, pattern matching y recursividad.

También se propuso comenzar con programas pequeños antes de avanzar hacia conceptos más complejos de Erlang.

**Uso del resultado:**

La explicación se utilizó para establecer una metodología de aprendizaje progresiva y comenzar la práctica con un programa sencillo de Hola Mundo.

---

### Prompt 2

> “Entonces por ejemplo, como seria el codigo para imprimir Hola Mundo, y puedes explicarme la funcion de cada cosa por ejemplo lo del module y lo de io:format”

**Resultado obtenido:**

El LLM proporcionó un programa básico de Hola Mundo:

```erlang
-module(hola).
-export([main/0]).

main() ->
    io:format("Hola, Mundo!~n").
```

También explicó la función de cada elemento del programa.

Se explicó que `-module(hola).` define el nombre del módulo y que normalmente debe coincidir con el nombre del archivo `.erl`.

También se explicó que `-export([main/0]).` permite que la función `main` pueda ser llamada desde fuera del módulo y que `/0` indica que la función no recibe parámetros.

Finalmente, se explicó que `io:format` pertenece al módulo `io` y permite mostrar información en la salida, mientras que `~n` representa un salto de línea.

**Uso del resultado:**

Esta explicación se utilizó para comprender la estructura básica del programa antes de escribirlo y ejecutarlo en la instancia de AWS.

---

### Prompt 3

> “Entonces, cuando se haga programas en Erl cual sería el flujo de pasos a seguir para empezar a programar sin problemas.”

**Resultado obtenido:**

El LLM explicó un flujo básico para trabajar con programas en Erlang:

```text
Crear archivo .erl
       ↓
Escribir código
       ↓
Guardar archivo
       ↓
Abrir Erlang
       ↓
Compilar con c(nombre).
       ↓
Ejecutar función
```

También se explicó la diferencia entre el código que se escribe dentro del archivo `.erl` y los comandos que se ejecutan directamente en Eshell.

**Uso del resultado:**

Este procedimiento se utilizó como guía para realizar la práctica de manera ordenada y evitar errores al momento de compilar y ejecutar el programa.

---

### Prompt 4

> “Ayúdame haciendo el formato para mi anexo.md para esta práctica: Hola Mundo en Erlang”

**Resultado obtenido:**

El LLM ayudó a estructurar esta bitácora tomando como referencia un anexo utilizado anteriormente. Se organizaron las secciones relacionadas con el uso de inteligencia artificial, prompts, resultados, decisiones realizadas, limitaciones, validación y reflexión crítica.

**Uso del resultado:**

La estructura fue utilizada para documentar de manera clara cómo se utilizó la inteligencia artificial durante el desarrollo de la práctica.

---

## 3. Cambios y decisiones realizadas

La información proporcionada por el LLM fue utilizada como apoyo y no se incorporó directamente sin comprenderla.

Una de las principales decisiones fue utilizar un programa sencillo para comenzar con Erlang:

```erlang
-module(hola).
-export([main/0]).

main() ->
    io:format("Hola, Mundo!~n").
```

Se decidió utilizar una función `main/0` para poder identificar claramente el punto desde el cual se ejecuta la práctica.

También se decidió trabajar el código dentro de un archivo `.erl` y utilizar Eshell únicamente para compilar y ejecutar el programa.

Por ejemplo:

```erlang
c(hola).
hola:main().
```

Esta separación permitió comprender que la definición de una función, como:

```erlang
main() ->
```

pertenece al archivo del módulo y no debe escribirse directamente en Eshell de la misma manera.

---

## 4. Errores, limitaciones y posibles confusiones

Durante el aprendizaje inicial se identificó que la sintaxis de Erlang puede resultar diferente para una persona acostumbrada a lenguajes como C#, Python, Java o JavaScript.

Una de las principales confusiones fue intentar escribir directamente en Eshell la definición de una función:

```erlang
saludar() ->
    io:format("Hola, mundo!~n").
```

Esto produjo un error de sintaxis porque la definición de la función debe encontrarse dentro de un archivo `.erl` que posteriormente se compila.

A partir de esto se estableció una diferencia importante entre:

* **Archivo `.erl`** → contiene módulos y funciones.
* **Eshell** → permite compilar módulos, ejecutar funciones y realizar pruebas.

También se tuvo en cuenta que la estructura mostrada corresponde a una práctica introductoria y que Erlang cuenta con conceptos más avanzados que serán estudiados posteriormente.

---

## 5. Validación de la información

La práctica se validó mediante la creación, compilación y ejecución del programa en una instancia de AWS utilizando Erlang.

El archivo utilizado fue:

```text
hola.erl
```

El módulo fue compilado mediante:

```erlang
c(hola).
```

La respuesta esperada fue:

```text
{ok,hola}
```

Posteriormente se ejecutó la función:

```erlang
hola:main().
```

Obteniendo como resultado:

```text
Hola, Mundo!
```

Con esto se comprobó que el módulo, la función exportada y la llamada a `io:format` funcionaban correctamente.

La práctica también fue registrada mediante Asciinema como evidencia del procedimiento realizado.

---

## 6. Reflexión crítica

El uso del LLM fue útil para comprender la estructura básica de un programa en Erlang, especialmente porque la sintaxis y la forma de ejecutar programas son diferentes a las de lenguajes previamente utilizados.

Uno de los puntos más importantes fue comprender que un programa de Erlang se organiza mediante módulos y funciones, y que las funciones pueden exportarse para ser llamadas desde fuera del módulo.

También fue útil comprender la diferencia entre escribir código dentro del archivo `.erl` y utilizar Eshell para compilar y ejecutar dicho código.

Sin embargo, la explicación proporcionada por el LLM tuvo que ser revisada y aplicada directamente en el entorno de Erlang, ya que una explicación teórica por sí sola no garantiza que el programa funcione correctamente.

La práctica permitió comprobar mediante la ejecución real que el código proporcionado era válido y ayudó a identificar errores relacionados con la sintaxis y la forma correcta de trabajar con Eshell.

En conclusión, el LLM fue utilizado como una herramienta de apoyo para aprender los conceptos iniciales de Erlang y resolver dudas durante la práctica. La ejecución del programa y la comprobación del resultado permitieron complementar la explicación teórica con una prueba práctica.
