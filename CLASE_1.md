# Python para Principiantes
## Clase 1: Fundamentos de Python

**Contenido:** Intérprete de Python, Comentarios, Tipos de Datos, Variables y Asignación

---

## 📑 Tabla de Contenidos

1. [Comenzando con Python (Getting Started)](#1-comenzando-con-python)
   - El Intérprete de Python
   - Modo Interactivo (REPL)
   - Ejecutar Scripts
2. [Comentarios en Python](#2-comentarios-en-python)
   - ¿Por qué usar comentarios?
   - Tipos de comentarios
   - Buenas prácticas
3. [Tipos de Datos (Data Types)](#3-tipos-de-datos)
   - Tipado dinámico
   - Tipos básicos: int, float, str, bool, None
   - Conversiones de tipos
4. [Variables y Asignación](#4-variables-y-asignación)
   - Creación de variables
   - Convenciones de nombres
   - Asignaciones múltiples

---

## 1. Comenzando con Python

### ¿Qué es Python?

Python es un **lenguaje de programación de alto nivel**, lo que significa que está diseñado para ser fácil de leer y escribir para los humanos. A diferencia de lenguajes de bajo nivel que hablan directamente con el hardware de la computadora, Python se encarga de traducir tu código a instrucciones que la máquina puede entender.

> **💡 Analogía:** Imagina que quieres hablar con alguien que solo habla alemán, pero tú solo hablas español. Necesitas un traductor (intérprete) que convierta tus palabras al alemán. Python funciona igual: tú escribes en 'Python' (lenguaje humano), y el intérprete lo traduce a 'lenguaje de máquina' (ceros y unos).

---

### ¿Cómo funciona el Intérprete de Python?

El intérprete de Python (CPython es el más común) es un programa que lee tu código Python y lo ejecuta. Este proceso ocurre en varias etapas:

```
┌─────────────────┐
│  Código Python  │
│     (.py)       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│      Lexer      │  ← Divide el código en "tokens"
│    (Tokens)     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     Parser      │  ← Construye Árbol de Sintaxis Abstracta (AST)
│      (AST)      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    Compiler     │  ← Genera bytecode (.pyc)
│   (Bytecode)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Python Virtual │  ← Ejecuta el bytecode
│    Machine      │
│     (PVM)       │
└────────┬────────┘
         │
         ▼
   Resultado Final
```

#### Explicación de cada fase:

| Fase | Descripción |
|------|-------------|
| **1. Código Python (.py)** | El código fuente que escribes en un archivo con extensión .py |
| **2. Lexer (Análisis Léxico)** | Divide el código en 'tokens' (palabras clave, operadores, identificadores) |
| **3. Parser (Análisis Sintáctico)** | Construye un Árbol de Sintaxis Abstracta (AST) verificando la estructura |
| **4. Compiler (Compilador)** | Convierte el AST en bytecode (.pyc) - código intermedio optimizado |
| **5. Python Virtual Machine** | Ejecuta el bytecode línea por línea y produce el resultado final |

> **📌 Nota importante:** Este proceso es completamente automático y ocurre en milisegundos. Como programador, solo necesitas escribir tu código Python - ¡el intérprete se encarga del resto!

---

### El Modo Interactivo (REPL)

Python tiene dos formas principales de ejecución: **modo interactivo** y **modo script**. El modo interactivo es ideal para experimentar y aprender.

**REPL significa: Read-Eval-Print-Loop** (Leer-Evaluar-Imprimir-Repetir)

```
    ┌──────────────────────────┐
    │                          │
    │    1. READ (Lee)         │
    │           ↓              │
    │    2. EVAL (Evalúa)      │
    │           ↓              │
    │    3. PRINT (Imprime)    │
    │           ↓              │
    │    4. LOOP (Repite) ─────┤
    │                          │
    └──────────────────────────┘
```

#### Iniciar el Shell Interactivo

Para iniciar Python en modo interactivo, abre tu terminal o línea de comandos y escribe:

```bash
$ python
```

Verás el **prompt** de Python representado por tres símbolos de mayor que (`>>>`). Esto indica que Python está esperando que escribas un comando.

#### Ejemplo de uso interactivo:

```python
>>> print("¡Hola, Python!")
¡Hola, Python!

>>> 2 + 2
4

>>> nombre = "Ana"
>>> print(f"Hola, {nombre}")
Hola, Ana
```

#### Salir del Shell Interactivo

Para salir del modo interactivo, escribe:

```python
>>> exit()
```

O presiona **Ctrl+D** (en Linux/Mac) o **Ctrl+Z** (en Windows)

---

### Ejecutar un Script de Python

Un script es un archivo que contiene múltiples líneas de código Python. Los scripts tienen la extensión **.py** y se ejecutan desde la terminal.

#### Paso 1: Crear un archivo

Crea un archivo llamado `mi_script.py` con este contenido:

```python
# mi_script.py
print("Este es mi primer script")
nombre = "Python"
version = 3.12
print(f"Estoy aprendiendo {nombre} {version}")
```

#### Paso 2: Ejecutar el script

Desde la terminal:

```bash
$ python mi_script.py
```

#### Resultado:

```
Este es mi primer script
Estoy aprendiendo Python 3.12
```

---

### Ejecutar Script en Modo Interactivo

Si quieres ejecutar un script y luego seguir experimentando en modo interactivo, usa la opción **-i**:

```bash
$ python -i mi_script.py
```

Esto ejecutará el script y luego te dejará en el prompt interactivo con todas las variables y funciones del script disponibles para usar.

> **💡 ¿Cuándo usar cada modo?**
> 
> - **Modo Interactivo:** Ideal para experimentar, probar pequeños fragmentos de código, aprender y depurar.
> - **Scripts:** Para programas completos que quieres guardar, compartir o ejecutar repetidamente.

---

## 2. Comentarios en Python

### ¿Qué son los Comentarios?

Los **comentarios** son líneas de texto en tu código que Python *ignora completamente*. No se ejecutan ni afectan el funcionamiento del programa. Su propósito es ayudar a los **humanos** (incluyéndote a ti mismo en el futuro) a entender qué hace el código.

```
┌──────────────────┐              ┌──────────────────────────┐
│     Código       │              │      Comentario          │
│  print('Hola')   │  ─────────▶  │  # Esto es un comentario │
│   ✓ Se ejecuta   │              │   ✗ Python lo ignora     │
└──────────────────┘              └──────────────────────────┘

         Python lee solo el código
      Los comentarios son para humanos
```

---

### ¿Por qué son importantes los comentarios?

1. **Documentación:** Explican qué hace el código y por qué
2. **Mantenimiento:** Facilitan modificar el código en el futuro
3. **Colaboración:** Ayudan a otros programadores a entender tu trabajo
4. **Aprendizaje:** Te recuerdan decisiones de diseño importantes
5. **Depuración:** Permiten desactivar temporalmente código sin borrarlo

---

### Sintaxis de los Comentarios

En Python, los comentarios comienzan con el símbolo **#** (numeral o hash). Todo lo que está después del # en esa línea es un comentario.

> **⚠️ Regla importante:** Siempre deja un espacio después del # para mayor legibilidad.

---

### Tipos de Comentarios

#### 1. Comentario de una sola línea

```python
# Este es un comentario de una sola línea
print("Hola, mundo")  # También puede ir al final de una línea de código
```

#### 2. Comentarios de múltiples líneas

Para comentarios largos, usa # en cada línea:

```python
# Este programa calcula el área de un círculo.
# Primero pedimos el radio al usuario.
# Luego aplicamos la fórmula: área = π * r²
# Finalmente mostramos el resultado.

import math
radio = 5
area = math.pi * radio ** 2
print(f"El área es: {area}")
```

---

### Buenas Prácticas para Comentarios

| ✓ HACER | ✗ EVITAR |
|---------|----------|
| **Explica el POR QUÉ, no el qué** | **No repitas lo que el código ya dice** |
| `# Usamos división entera para evitar decimales`<br>`cantidad = total // 2` | `# Divide total por 2`<br>`cantidad = total // 2` |
| **Mantén los comentarios actualizados** | **Dejar comentarios obsoletos o incorrectos** |
| **Usa comentarios para decisiones complejas** | **Comentar código obvio** |
| **Escribe en español claro y conciso** | **Usar jerga o abreviaciones confusas** |

---

### Ejemplos Prácticos de Buenos Comentarios

```python
# Ejemplo 1: Explicando una decisión de diseño
def calcular_descuento(precio, es_miembro):
    # Los miembros obtienen 20% de descuento para fomentar la lealtad
    if es_miembro:
        return precio * 0.80
    return precio

# Ejemplo 2: Advertencia importante
def procesar_pago(tarjeta):
    # IMPORTANTE: Verificar fecha de expiración antes de procesar
    # para evitar cargos fallidos
    if not tarjeta.esta_vigente():
        return False
    return procesar_transaccion(tarjeta)

# Ejemplo 3: TODOs para trabajo futuro
def generar_reporte():
    # TODO: Agregar opción para exportar a PDF
    # TODO: Incluir gráficos de tendencias
    datos = obtener_datos()
    crear_reporte_html(datos)
```

> **💡 Recuerda:** Los buenos comentarios son como un buen mapa: te ayudan a navegar por el código sin perderte. Pero un mapa con demasiada información es confuso, así que comenta solo lo necesario.

---

## 3. Tipos de Datos

### ¿Qué son los Tipos de Datos?

Los **tipos de datos** definen qué clase de información puede contener una variable y qué operaciones se pueden realizar con ella. Es como clasificar objetos en el mundo real: números, texto, verdadero/falso, etc.

> **💡 Analogía:** Imagina que tienes cajas para guardar cosas. Una caja para números, otra para textos, otra para valores verdadero/falso. No puedes sumar texto con texto de la misma forma que sumas números. Los tipos de datos son esas 'cajas' en Python.

---

### Tipos de Datos Básicos en Python

```
┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐
│   int    │  │  float   │  │   str    │  │   bool   │
│    42    │  │   3.14   │  │  "Hola"  │  │   True   │
│ Enteros  │  │Decimales │  │  Texto   │  │Verdadero │
└──────────┘  └──────────┘  └──────────┘  └──────────┘

                    ┌──────────────┐
                    │     None     │
                    │ Sin valor    │
                    └──────────────┘
```

---

### Python es Dinámicamente Tipado

A diferencia de lenguajes como C o Java, en Python **NO necesitas declarar** el tipo de una variable. Python lo determina automáticamente según el valor que le asignes.

```python
# Python determina el tipo automáticamente
edad = 25           # Python sabe que es int
precio = 19.99      # Python sabe que es float
nombre = "Ana"      # Python sabe que es str
activo = True       # Python sabe que es bool

# Puedes cambiar el tipo de una variable en cualquier momento
x = 10              # x es int
x = "Hola"          # ahora x es str (¡esto es válido!)
```

> **✅ Ventaja:** Más flexible y fácil de escribir.
> 
> **⚠️ Cuidado:** Debes tener cuidado de no cambiar tipos accidentalmente.

---

### 1. Enteros (int)

Los enteros son números **sin parte decimal**. Pueden ser positivos, negativos o cero. En Python, los enteros no tienen límite de tamaño (solo limitados por la memoria).

```python
# Ejemplos de enteros
edad = 25
temperatura = -5
poblacion = 1000000
cero = 0

# Python puede manejar números muy grandes
numero_enorme = 123456789012345678901234567890

# Operaciones con enteros
suma = 10 + 5               # 15
resta = 10 - 3              # 7
multiplicacion = 4 * 3      # 12
division_entera = 10 // 3   # 3 (división sin decimales)
residuo = 10 % 3            # 1 (resto de la división)
potencia = 2 ** 3           # 8 (2 elevado a 3)
```

---

### 2. Flotantes (float)

Los flotantes son números **con parte decimal**. Son útiles para mediciones precisas, cálculos científicos y cualquier situación donde necesites decimales.

```python
# Ejemplos de flotantes
precio = 19.99
temperatura = 36.5
pi = 3.14159
resultado = 7.0

# Notación científica
velocidad_luz = 3e8         # 3 × 10^8 = 300,000,000
masa_electron = 9.1e-31     # 9.1 × 10^-31

# Operaciones con flotantes
suma = 3.5 + 2.1            # 5.6
division = 10 / 3           # 3.3333333333333335

# ¡Cuidado con la precisión!
print(0.1 + 0.2)            # 0.30000000000000004 (¡imprecisión!)
```

> **📌 Nota sobre precisión:** Los flotantes pueden tener pequeños errores de redondeo debido a cómo las computadoras representan números decimales. Para cálculos financieros precisos, usa el módulo `decimal`.

---

### 3. Cadenas de Texto (str)

Las cadenas (strings) son secuencias de caracteres usadas para representar texto. Se definen usando comillas simples (' ') o dobles (" ").

```python
# Ejemplos de cadenas
nombre = "Ana García"
ciudad = 'Buenos Aires'
mensaje = "¡Hola, mundo!"

# Cadenas multilínea (con triple comillas)
parrafo = """Este es un texto
que ocupa varias líneas
sin problema."""

# Operaciones con cadenas
saludo = "Hola" + " " + "mundo"  # "Hola mundo" (concatenación)
repetir = "Ja" * 3               # "JaJaJa" (repetición)
longitud = len("Python")         # 6 (número de caracteres)

# Acceso a caracteres (indexación)
palabra = "Python"
print(palabra[0])    # "P" (primer carácter)
print(palabra[-1])   # "n" (último carácter)
```

---

### 4. Booleanos (bool)

Los booleanos representan valores de **verdad**: `True` (verdadero) o `False` (falso). Son fundamentales para la toma de decisiones en programación.

```python
# Valores booleanos
es_mayor_edad = True
tiene_descuento = False

# Los booleanos resultan de comparaciones
edad = 18
es_adulto = edad >= 18    # True

precio = 100
es_caro = precio > 200    # False

# Operadores lógicos
tiene_dinero = True
esta_abierto = True
puede_comprar = tiene_dinero and esta_abierto  # True (ambos deben ser True)

es_fin_semana = False
es_feriado = True
puede_descansar = es_fin_semana or es_feriado  # True (al menos uno True)

esta_lloviendo = True
lleva_paraguas = not esta_lloviendo  # False (invierte el valor)
```

---

### 5. None - Tipo Especial

`None` es un valor especial que representa la **ausencia de valor**. Es útil para indicar que una variable aún no tiene un valor asignado o que una función no devuelve nada.

```python
# Ejemplos de None
resultado = None        # Inicializar sin valor
respuesta = None        # Placeholder para usar después

def buscar_usuario(id):
    if id == 123:
        return "Ana"
    return None        # No se encontró el usuario

# Verificar si algo es None
if resultado is None:
    print("No hay resultado todavía")
```

---

### Investigando Tipos de Datos

Python proporciona funciones útiles para verificar tipos de datos:

```python
# Función type() - devuelve el tipo de un valor
print(type(42))         # <class 'int'>
print(type(3.14))       # <class 'float'>
print(type("Hola"))     # <class 'str'>
print(type(True))       # <class 'bool'>
print(type(None))       # <class 'NoneType'>

# Función isinstance() - verifica si es un tipo específico
edad = 25
print(isinstance(edad, int))      # True
print(isinstance(edad, str))      # False

precio = 19.99
print(isinstance(precio, float))  # True
```

---

### Conversión de Tipos (Type Casting)

Puedes convertir un tipo de dato a otro usando funciones de conversión:

```python
# Convertir a entero
numero = int("42")        # "42" (str) → 42 (int)
entero = int(3.9)         # 3.9 (float) → 3 (int) - ¡trunca decimales!

# Convertir a flotante
decimal = float("3.14")   # "3.14" (str) → 3.14 (float)
flotante = float(10)      # 10 (int) → 10.0 (float)

# Convertir a cadena
texto = str(42)           # 42 (int) → "42" (str)
texto2 = str(True)        # True (bool) → "True" (str)

# Convertir a booleano
bool(1)      # True (cualquier número != 0 es True)
bool(0)      # False
bool("")     # False (cadena vacía es False)
bool("Hola") # True (cadena con contenido es True)
```

> **⚠️ ¡Importante!** No todas las conversiones son posibles. Por ejemplo, `int('Hola')` producirá un error porque 'Hola' no es un número válido.

---

## 4. Variables y Asignación

### ¿Qué es una Variable?

Una **variable** es como una caja etiquetada donde guardas información. El nombre de la variable es la etiqueta, y el valor que le asignas es lo que hay dentro de la caja.

```
┌──────────────────┐
│   Variable:      │
│      edad        │  ← Nombre (etiqueta)
├──────────────────┤
│       25         │  ← Valor (contenido)
└──────────────────┘
```

> **💡 Analogía:** Piensa en las variables como cajas de almacenamiento en tu memoria. Cada caja tiene un nombre único (el identificador) y puede contener un valor. Cuando necesitas ese valor, solo llamas a la caja por su nombre.

---

### Crear y Asignar Variables

Para crear una variable en Python, simplemente asignas un valor usando el operador **=**. La variable se crea en el momento de la asignación.

```python
# Sintaxis básica: nombre = valor
nombre = "Leo"          # Variable 'nombre' contiene "Leo"
edad = 7                # Variable 'edad' contiene 7
altura = 5.6            # Variable 'altura' contiene 5.6
es_gato = True          # Variable 'es_gato' contiene True
defectos = None         # Variable 'defectos' contiene None

# Las variables se pueden usar después de crearlas
print(nombre)           # Leo
print(edad + 3)         # 10
```

---

### Reglas para Nombres de Variables

Python tiene reglas estrictas sobre cómo puedes nombrar variables:

| ✓ VÁLIDO | ✗ INVÁLIDO | EXPLICACIÓN |
|----------|------------|-------------|
| `edad` | `2edad` | No puede empezar con número |
| `nombre_completo` | `nombre-completo` | Usa guion bajo (_), no guion (-) |
| `precio_USD` | `precio USD` | No puede contener espacios |
| `es_valido` | `es-válido` | Evita caracteres especiales y acentos |
| `MAX_VALOR` | `class` | 'class' es palabra reservada de Python |
| `dato1` | `1dato` | No puede empezar con número |

---

### Convención: snake_case

En Python, la convención estándar es usar **snake_case** para nombres de variables: todo en minúsculas, separando palabras con guiones bajos (_).

```python
# ✓ Estilo recomendado (snake_case)
nombre_completo = "Ana García"
precio_total = 150.50
es_mayor_edad = True
numero_intentos = 3

# ✗ Otros estilos (NO recomendados en Python para variables)
NombreCompleto = "Ana"    # PascalCase (se usa para clases)
precioTotal = 150.50      # camelCase (común en JavaScript)
```

---

### Usa Nombres Descriptivos

El nombre de una variable debe describir claramente qué contiene. Código claro es mejor que código corto.

| ✗ MALO | ✓ BUENO | ¿POR QUÉ? |
|--------|---------|-----------|
| `x = 25` | `edad = 25` | 'edad' es más descriptivo que 'x' |
| `t = 36.5` | `temperatura = 36.5` | Queda claro qué representa |
| `d = True` | `descuento_activo = True` | Indica exactamente qué significa |
| `n = "Ana"` | `nombre_usuario = "Ana"` | Específico y claro |

---

### Asignaciones Múltiples

Python permite asignar valores a múltiples variables en una sola línea:

#### 1. Asignación Paralela

```python
# Asignar diferentes valores a múltiples variables
x, y = 10, 20
print(x)  # 10
print(y)  # 20

# Útil para intercambiar valores
a, b = 5, 10
a, b = b, a  # ¡Intercambio en una línea!
print(a)  # 10
print(b)  # 5

# Con más variables
nombre, edad, ciudad = "Ana", 25, "Buenos Aires"
```

#### 2. Asignación Encadenada

Asignar el mismo valor a múltiples variables:

```python
# Todas las variables tienen el mismo valor
a = b = c = 0
print(a, b, c)  # 0 0 0

# Otro ejemplo
x = y = z = "Python"
print(x)  # Python
print(y)  # Python
print(z)  # Python
```

---

### Asignaciones Aumentadas (Operadores Compuestos)

Los operadores de asignación aumentada combinan una operación aritmética con asignación. Son atajos convenientes:

```python
# Operadores de asignación aumentada
contador = 10
contador += 1    # Equivale a: contador = contador + 1
print(contador)  # 11

contador -= 3    # Equivale a: contador = contador - 3
print(contador)  # 8

precio = 100
precio *= 2      # Equivale a: precio = precio * 2
print(precio)    # 200

precio /= 4      # Equivale a: precio = precio / 4
print(precio)    # 50.0

# Con listas (agregar elementos)
numeros = [1, 2, 3]
numeros += [4, 5]  # Equivale a: numeros = numeros + [4, 5]
print(numeros)     # [1, 2, 3, 4, 5]
```

#### Tabla de Operadores Aumentados

| Operador | Equivalente | Ejemplo | Resultado |
|----------|-------------|---------|-----------|
| `+=` | `x = x + y` | `x = 10; x += 3` | `x = 13` |
| `-=` | `x = x - y` | `x = 10; x -= 3` | `x = 7` |
| `*=` | `x = x * y` | `x = 10; x *= 3` | `x = 30` |
| `/=` | `x = x / y` | `x = 10; x /= 2` | `x = 5.0` |
| `//=` | `x = x // y` | `x = 10; x //= 3` | `x = 3` |
| `%=` | `x = x % y` | `x = 10; x %= 3` | `x = 1` |
| `**=` | `x = x ** y` | `x = 2; x **= 3` | `x = 8` |

---

## 📝 Resumen de la Clase 1

En esta primera clase hemos cubierto los fundamentos esenciales de Python:

✓ **Intérprete de Python:** Aprendiste cómo Python ejecuta tu código a través del proceso de lexing, parsing, compilación a bytecode y ejecución en la PVM.

✓ **Modos de ejecución:** Modo interactivo (REPL) para experimentar y scripts (.py) para programas completos.

✓ **Comentarios:** Cómo documentar tu código usando # y las mejores prácticas para escribir comentarios útiles.

✓ **Tipos de datos:** Los tipos fundamentales (int, float, str, bool, None) y cómo Python determina tipos automáticamente.

✓ **Variables:** Cómo crear y nombrar variables siguiendo convenciones (snake_case), y diferentes formas de asignación.

---

## 🎯 Ejercicios para Practicar

### Ejercicio 1
Abre el intérprete de Python y experimenta con:
- Crear variables de diferentes tipos
- Hacer operaciones matemáticas
- Convertir entre tipos de datos

### Ejercicio 2
Crea un script llamado `mi_info.py` que:
- Guarde tu nombre, edad y ciudad en variables
- Imprima un mensaje presentándote usando esas variables
- Incluya comentarios explicando cada línea

### Ejercicio 3
Escribe código que:
- Cree dos variables numéricas (edad1 y edad2)
- Calcule el promedio usando operadores
- Imprima el resultado con un mensaje descriptivo

### Ejercicio 4
Experimenta con `type()` e `isinstance()`:
- Crea variables de cada tipo básico
- Verifica sus tipos con `type()`
- Usa `isinstance()` para confirmar los tipos

---

## 🚀 Próximos Pasos

En la próxima clase exploraremos:

- **Cadenas de texto avanzadas:** Métodos, formateo, slicing
- **Estructuras condicionales:** if, elif, else
- **Operadores de comparación y lógicos:** ==, !=, and, or, not
- **Introducción a loops:** for y while

---

## 🎉 ¡Felicitaciones!

Has dado tus primeros pasos en Python. La clave del éxito es la **práctica constante**. Experimenta con el código, prueba cosas nuevas y no temas cometer errores - ¡los errores son oportunidades de aprendizaje!

> *"El código es como el humor. Cuando tienes que explicarlo, es malo."* - Cory House

---

**Preparado por:** Mauricio Mercado
**Fecha:** Noviembre 2025
**Clase:** 1 de Python para Principiantes
