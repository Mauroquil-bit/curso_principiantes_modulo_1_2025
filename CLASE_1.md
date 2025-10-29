# Guía Teórica Completa de Python para Principiantes

---

## 1. GETTING STARTED - Comenzando con Python

### 1.1 El Intérprete Interactivo de Python

**Concepto Fundamental:**
Python es un lenguaje interpretado, lo que significa que no necesitas compilar tu código antes de ejecutarlo. El intérprete de Python lee y ejecuta el código línea por línea en tiempo real.

**El Shell Interactivo (REPL):**
REPL significa Read-Eval-Print Loop (Leer-Evaluar-Imprimir-Repetir). Es un entorno donde puedes:
- Escribir código Python línea por línea
- Ver resultados inmediatos
- Experimentar y probar ideas rápidamente
- Explorar funciones y módulos

**Comandos básicos:**

```bash
# Iniciar el shell interactivo
$ python
# o en algunos sistemas:
$ python3

# Dentro del shell verás el prompt:
>>> 

# Para salir del shell:
>>> exit()
# o alternativamente:
>>> quit()
# o presionar Ctrl+D (Linux/Mac) o Ctrl+Z (Windows)
```

**Ejemplo práctico en el shell:**
```python
>>> 2 + 2
4
>>> nombre = "María"
>>> print(f"Hola, {nombre}")
Hola, María
>>> help(print)  # Obtener ayuda sobre una función
```

### 1.2 Ejecutar Scripts de Python

**¿Qué es un script?**
Un script es un archivo de texto con extensión `.py` que contiene código Python. Permite escribir programas más largos y reutilizables.

**Crear y ejecutar un script:**

```python
# Archivo: mi_script.py
print("¡Hola, mundo!")
nombre = input("¿Cómo te llamas? ")
print(f"Encantado de conocerte, {nombre}!")
```

```bash
# Ejecutar el script
$ python mi_script.py

# Ejecutar en modo interactivo (el shell queda abierto después)
$ python -i mi_script.py
```

**Ventajas del modo interactivo (-i):**
- El script se ejecuta completamente
- El shell permanece abierto
- Puedes inspeccionar variables creadas en el script
- Útil para debugging y experimentación

**Ejemplo:**
```python
# Archivo: calculos.py
resultado = 10 * 5
print(f"El resultado es: {resultado}")
```

```bash
$ python -i calculos.py
El resultado es: 50
>>> resultado  # Podemos acceder a la variable
50
>>> resultado * 2  # Y seguir trabajando con ella
100
```

**📚 Documentación Oficial:**
- Tutorial de Python: https://docs.python.org/es/3/tutorial/interpreter.html
- Usando el intérprete: https://docs.python.org/3/tutorial/interpreter.html
- Invocación del intérprete: https://docs.python.org/3/using/cmdline.html

---

## 2. COMMENTS - Comentarios

### 2.1 Teoría de los Comentarios

**¿Qué son los comentarios?**
Los comentarios son líneas de texto en el código que Python ignora completamente durante la ejecución. Son exclusivamente para los humanos que leen el código.

**Propósito de los comentarios:**
1. **Explicar el "por qué"**, no el "qué"
2. Documentar decisiones de diseño
3. Advertir sobre comportamientos inesperados
4. Facilitar el mantenimiento futuro del código
5. Ayudar a otros desarrolladores (o a ti mismo en el futuro)

**Sintaxis:**
```python
# Esto es un comentario de una línea

# Los comentarios pueden estar al final de una línea
print("Hola")  # Esto imprime un saludo

# También puedes comentar código temporalmente
# print("Esto no se ejecutará")
```

### 2.2 Buenas Prácticas

**✅ BUENOS comentarios:**
```python
# Usar promedio ponderado porque los datos más recientes son más confiables
promedio = calcular_promedio_ponderado(datos)

# HACK: Esta solución temporal debe reemplazarse cuando se actualice la API
resultado = workaround_temporal()

# TODO: Agregar validación de entrada aquí
def procesar_datos(datos):
    return datos * 2
```

**❌ MALOS comentarios:**
```python
# Incrementar i en 1
i += 1  # Esto es obvio del código mismo

# Esta función suma dos números
def sumar(a, b):  # El nombre ya lo dice
    return a + b
```

### 2.3 Comentarios Multi-línea

Python no tiene comentarios multi-línea oficiales, pero puedes usar:

```python
# Opción 1: Múltiples comentarios de línea
# Esta es una explicación
# que ocupa varias líneas
# para describir algo complejo

# Opción 2: String de documentación (no es técnicamente un comentario)
"""
Esta es una cadena de documentación.
Se usa frecuentemente como comentario multi-línea,
aunque técnicamente es una cadena no asignada.
"""

def mi_funcion():
    """
    Esta es una docstring.
    Documenta qué hace la función.
    Es la forma oficial de documentar funciones en Python.
    """
    pass
```

### 2.4 Convención PEP 8

**Estilo de comentarios según PEP 8:**
- Siempre incluir un espacio después del `#`
- Los comentarios deben estar en oraciones completas
- Usar dos espacios antes de comentarios en línea
- Limitar comentarios a 72 caracteres por línea

```python
# ✅ Correcto: espacio después del #
x = 5  # Correcto: dos espacios antes del comentario

#❌ Incorrecto: sin espacio después del #
x=5# Incorrecto: sin espacios
```

**📚 Documentación Oficial:**
- PEP 8 - Guía de Estilo: https://peps.python.org/pep-0008/#comments
- Comentarios en Python: https://docs.python.org/3/reference/lexical_analysis.html#comments
- Docstrings (PEP 257): https://peps.python.org/pep-0257/

---

## 3. DATA TYPES - Tipos de Datos

### 3.1 Python es Dinámicamente Tipado

**Concepto Fundamental:**
A diferencia de lenguajes como Java o C++, en Python **no necesitas declarar el tipo de una variable**. El tipo se determina automáticamente en tiempo de ejecución según el valor asignado.

```python
# Python determina automáticamente que x es un entero
x = 42

# Podemos cambiar el tipo de x sin problemas
x = "ahora soy un string"

# Y cambiar nuevamente
x = 3.14
```

### 3.2 Tipos de Datos Fundamentales

**Tipos Numéricos:**
```python
# int - Números enteros (tamaño ilimitado en Python 3)
edad = 25
grande = 999999999999999999999

# float - Números de punto flotante (decimales)
pi = 3.14159
temperatura = -15.5

# complex - Números complejos
complejo = 3 + 4j
```

**Tipo Booleano:**
```python
# bool - Valores de verdad (True o False)
es_mayor = True
tiene_descuento = False

# Los booleanos son subclase de int
print(True + True)  # 2
print(False * 10)   # 0
```

**Tipo None:**
```python
# NoneType - Representa ausencia de valor
resultado = None  # Similar a null en otros lenguajes

# Usado para:
# - Valores opcionales
# - Inicialización de variables
# - Indicar que una función no retorna nada explícitamente
```

**Tipo Cadena:**
```python
# str - Cadenas de texto (secuencias de caracteres)
nombre = "Python"
mensaje = 'También con comillas simples'
```

### 3.3 Investigación de Tipos

**Función type():**
```python
>>> type(42)
<class 'int'>

>>> type(3.14)
<class 'float'>

>>> type("Hello")
<class 'str'>

>>> type(True)
<class 'bool'>

>>> type(None)
<class 'NoneType'>

# type() retorna el tipo, no un string
>>> mi_tipo = type(42)
>>> print(mi_tipo)
<class 'int'>
```

**Función isinstance():**
Verifica si un objeto es instancia de una clase específica.

```python
>>> isinstance(3.14, float)
True

>>> isinstance(3.14, int)
False

# Ventaja: funciona con herencia
>>> isinstance(True, int)  # bool hereda de int
True

# Puede verificar múltiples tipos
>>> isinstance(42, (int, float, str))
True
```

**Función issubclass():**
Verifica relaciones de herencia entre clases.

```python
>>> issubclass(bool, int)
True

>>> issubclass(int, object)
True  # Todo hereda de object en Python

>>> issubclass(str, int)
False
```

### 3.4 Conversión de Tipos (Type Casting)

**Conversión Explícita:**
```python
# String a número
num_str = "42"
num_int = int(num_str)        # 42
num_float = float(num_str)    # 42.0

# Número a string
edad = 25
texto = str(edad)             # "25"

# A booleano (importante: valores "falsy" y "truthy")
bool(1)          # True
bool(0)          # False
bool("")         # False (string vacío)
bool("Python")   # True (string no vacío)
bool([])         # False (lista vacía)
bool([1, 2])     # True (lista con elementos)

# String a lista
letras = list("abc")  # ["a", "b", "c"]

# Conversiones que pueden fallar
int("3.14")       # ValueError: invalid literal
int("cuarenta")   # ValueError: invalid literal
```

**Conversiones Seguras con Manejo de Errores:**
```python
def convertir_a_entero(valor):
    try:
        return int(valor)
    except ValueError:
        print(f"No se puede convertir '{valor}' a entero")
        return None

resultado = convertir_a_entero("123")    # 123
resultado = convertir_a_entero("abc")    # None (con mensaje de error)
```

### 3.5 Jerarquía de Tipos en Python

```
object (todos heredan de object)
  ├── NoneType
  ├── números
  │   ├── int
  │   │   └── bool
  │   ├── float
  │   └── complex
  ├── str
  ├── bytes
  ├── collections
  │   ├── list
  │   ├── tuple
  │   ├── dict
  │   └── set
  └── ...
```

**📚 Documentación Oficial:**
- Tipos integrados: https://docs.python.org/es/3/library/stdtypes.html
- Funciones integradas (type, isinstance): https://docs.python.org/3/library/functions.html
- Sistema de tipos: https://docs.python.org/3/reference/datamodel.html

---

## 4. VARIABLES & ASSIGNMENT - Variables y Asignación

### 4.1 Concepto de Variables

**¿Qué es una variable?**
Una variable es un **nombre que hace referencia a un valor en memoria**. En Python, las variables son etiquetas o referencias, no "cajas" que contienen valores.

**Modelo Mental Correcto:**
```python
# No pienses: "x contiene el valor 42"
# Piensa: "x es una etiqueta que apunta al objeto 42"
x = 42
```

**Demostración:**
```python
>>> a = [1, 2, 3]
>>> b = a  # b apunta al MISMO objeto que a
>>> b.append(4)
>>> print(a)  # ¡a también cambió!
[1, 2, 3, 4]

>>> id(a) == id(b)  # Mismo objeto en memoria
True
```

### 4.2 Creación de Variables

**Asignación Básica:**
```python
# La variable se crea en el momento de la asignación
nombre = "Leo"        # Se crea 'nombre'
edad = 7              # Se crea 'edad'
altura = 5.6          # Se crea 'altura'
es_gato = True        # Se crea 'es_gato'
defectos = None       # Se crea 'defectos'

# No necesitas declaración previa (como en C o Java)
# int edad;  // ← Esto NO es necesario en Python
```

### 4.3 Convenciones de Nombres

**snake_case (lo recomendado para variables):**
```python
# ✅ Correcto - snake_case
nombre_completo = "Juan Pérez"
edad_usuario = 30
total_ventas_2024 = 150000

# ❌ Incorrecto para Python (aunque válido)
nombreCompleto = "Juan Pérez"     # camelCase (usado en Java/JavaScript)
NombreCompleto = "Juan Pérez"     # PascalCase (usado para clases)
nombre-completo = "Juan Pérez"    # ¡ERROR! guiones no permitidos
```

**Reglas para nombres de variables:**
```python
# ✅ Válido
_privado = 10
numero1 = 20
CONSTANTE = 100

# ❌ Inválido
1numero = 20      # No puede empezar con número
mi-variable = 30  # No puede contener guiones
class = 40        # No puede ser palabra reservada
```

**Nombres Descriptivos:**
```python
# ❌ Mal - no descriptivo
x = 25
d = 30
t = x * d

# ✅ Bien - descriptivo
precio_unitario = 25
cantidad = 30
total = precio_unitario * cantidad
```

### 4.4 Asignaciones Múltiples

**Asignación Paralela (Unpacking):**
```python
# Asignar múltiples valores simultáneamente
x, y = 10, 20
print(x)  # 10
print(y)  # 20

# Intercambiar valores (¡sin variable temporal!)
a, b = 5, 10
a, b = b, a  # Pythonic way
print(a, b)  # 10, 5

# Con más valores
nombre, edad, ciudad = "Ana", 28, "Madrid"

# Desempacar una lista o tupla
coordenadas = (3, 4)
x, y = coordenadas
```

**Asignación Encadenada:**
```python
# Dar el mismo valor a múltiples variables
a = b = c = 0
print(a, b, c)  # 0 0 0

# ⚠️ CUIDADO con objetos mutables
lista1 = lista2 = []  # ¡Apuntan a la MISMA lista!
lista1.append(1)
print(lista2)  # [1] - ¡también se modificó!

# Mejor manera con objetos mutables:
lista1 = []
lista2 = []  # Listas diferentes
```

**Desempaquetado Extendido:**
```python
# Con el operador * (Python 3+)
primero, *resto = [1, 2, 3, 4, 5]
print(primero)  # 1
print(resto)    # [2, 3, 4, 5]

# Ignorar valores con _
nombre, _, edad = ("Ana", "García", 28)
print(nombre, edad)  # Ana 28

# En el medio
primero, *medio, ultimo = [1, 2, 3, 4, 5]
print(primero)  # 1
print(medio)    # [2, 3, 4]
print(ultimo)   # 5
```

### 4.5 Asignaciones Aumentadas

**Operadores Aumentados:**
```python
# Forma larga
contador = 0
contador = contador + 1

# Forma corta (preferida)
contador = 0
contador += 1  # Equivalente a: contador = contador + 1

# Otros operadores aumentados
x = 10
x -= 3   # x = x - 3      → 7
x *= 2   # x = x * 2      → 14
x /= 7   # x = x / 7      → 2.0
x //= 2  # x = x // 2     → 1
x %= 3   # x = x % 3      → 1
x **= 3  # x = x ** 3     → 1

# Con strings
saludo = "Hola"
saludo += " Mundo"  # "Hola Mundo"

# Con listas
numeros = [1, 2]
numeros += [3, 4]  # [1, 2, 3, 4]

# Con operadores bit a bit
permisos = 0b1000
permisos |= 0b0100  # OR bit a bit
permisos &= 0b1100  # AND bit a bit
```

### 4.6 El Operador Walrus (:=) - Python 3.8+

**Asignación en Expresiones:**
```python
# Antes de Python 3.8
datos = input("Escribe algo: ")
if len(datos) > 10:
    print(f"Demasiado largo: {len(datos)}")

# Con el operador walrus (Python 3.8+)
if (n := len(input("Escribe algo: "))) > 10:
    print(f"Demasiado largo: {n}")

# Útil en while loops
while (linea := archivo.readline()) != "":
    procesar(linea)

# En comprehensions
[y for x in datos if (y := procesar(x)) > 0]
```

### 4.7 Ámbito (Scope) de Variables

```python
# Variable global
global_var = "Soy global"

def mi_funcion():
    # Variable local
    local_var = "Soy local"
    print(global_var)  # Puede leer globales
    print(local_var)

mi_funcion()
# print(local_var)  # ¡ERROR! No existe fuera de la función
```

**📚 Documentación Oficial:**
- Tutorial sobre variables: https://docs.python.org/es/3/tutorial/introduction.html#using-python-as-a-calculator
- Asignaciones: https://docs.python.org/3/reference/simple_stmts.html#assignment-statements
- PEP 8 - Convenciones de nombres: https://peps.python.org/pep-0008/#naming-conventions
- Operador Walrus (PEP 572): https://peps.python.org/pep-0572/

---

## 5. STRINGS - Cadenas de Texto

### 5.1 Fundamentos de Strings

**¿Qué es un string?**
Un string es una **secuencia inmutable de caracteres Unicode**. "Inmutable" significa que una vez creado, no puedes modificar sus caracteres individuales.

```python
texto = "Python"
# texto[0] = "J"  # ¡ERROR! Los strings son inmutables

# Para "modificar", creas un nuevo string
texto = "J" + texto[1:]  # "Jython"
```

### 5.2 Crear Strings

**Comillas Simples vs Dobles:**
```python
# Ambas formas son válidas
simple = 'Hola'
doble = "Mundo"

# PEP 8 recomienda ser consistente (Real Python prefiere dobles)
recomendado = "Python"

# Útil cuando el texto contiene comillas
con_apostrofe = "It's a beautiful day"
con_comillas = 'Él dijo: "Hola"'

# O escapar
con_escape = 'It\'s a beautiful day'
```

**Strings Multi-línea:**
```python
# Con triple comillas (''' o """)
poema = """
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
"""

# Mantiene saltos de línea y espacios
sql = """
SELECT nombre, edad
FROM usuarios
WHERE edad > 18
"""
```

**Caracteres de Escape:**
```python
# Saltos de línea y tabulaciones
texto = "Línea 1\nLínea 2\tcon tab"

# Barra invertida
ruta = "C:\\Users\\Documents"  # Windows path

# Comillas dentro de strings
dialogo = "Ella dijo: \"¡Hola!\""
```

### 5.3 Operaciones con Strings

**Concatenación:**
```python
# Con el operador +
saludo = "Hola" + " " + "Mundo"  # "Hola Mundo"

# Concatenación implícita (literales adyacentes)
largo = "Este es un texto " "muy largo"

# ⚠️ Evita concatenar en loops (ineficiente)
# ❌ Mal
resultado = ""
for palabra in palabras:
    resultado += palabra  # Crea un nuevo string cada vez

# ✅ Mejor
resultado = "".join(palabras)
```

**Repetición:**
```python
# Con el operador *
linea = "-" * 50  # "--------------------------------------------------"
eco = "Eco! " * 3  # "Eco! Eco! Eco! "

# Útil para separadores
print("=" * 20)
print("Título")
print("=" * 20)
```

**Longitud:**
```python
texto = "Python"
longitud = len(texto)  # 6

# Útil para validaciones
password = input("Password: ")
if len(password) < 8:
    print("Password muy corto")
```

### 5.4 Métodos de Strings

**Cambio de Mayúsculas/Minúsculas:**
```python
texto = "Python Programming"

texto.upper()        # "PYTHON PROGRAMMING"
texto.lower()        # "python programming"
texto.capitalize()   # "Python programming"
texto.title()        # "Python Programming"
texto.swapcase()     # "pYTHON pROGRAMMING"

# Verificación
"python".islower()   # True
"PYTHON".isupper()   # True
"Python".istitle()   # True
```

**Limpieza de Espacios:**
```python
texto = "  espacios  "

texto.strip()    # "espacios" (ambos lados)
texto.lstrip()   # "espacios  " (izquierda)
texto.rstrip()   # "  espacios" (derecha)

# Remover caracteres específicos
"www.ejemplo.com".strip("cmowz.")  # "ejemplo"
```

**Búsqueda y Reemplazo:**
```python
texto = "Python es genial"

texto.replace("genial", "asombroso")  # "Python es asombroso"
texto.find("es")                       # 7 (índice donde comienza)
texto.find("Java")                     # -1 (no encontrado)
"es" in texto                          # True (más Pythonic)
texto.count("n")                       # 1 (cuántas veces aparece)

# startswith y endswith
archivo = "documento.pdf"
archivo.endswith(".pdf")    # True
archivo.startswith("doc")   # True
```

**División y Unión:**
```python
# split() - dividir string en lista
frase = "Python es genial"
palabras = frase.split()  # ["Python", "es", "genial"]

csv = "nombre,edad,ciudad"
datos = csv.split(",")  # ["nombre", "edad", "ciudad"]

# splitlines() - dividir por líneas
texto = "Línea 1\nLínea 2\nLínea 3"
lineas = texto.splitlines()  # ["Línea 1", "Línea 2", "Línea 3"]

# join() - unir lista en string
palabras = ["Python", "es", "genial"]
frase = " ".join(palabras)  # "Python es genial"

ruta = "/".join(["home", "user", "documents"])  # "home/user/documents"
```

### 5.5 Indexing y Slicing

**Indexación:**
```python
texto = "Python"

# Índices positivos (desde el inicio)
texto[0]   # "P" (primer carácter)
texto[1]   # "y"
texto[5]   # "n" (último)

# Índices negativos (desde el final)
texto[-1]  # "n" (último)
texto[-2]  # "o" (penúltimo)
texto[-6]  # "P" (primer carácter)

# IndexError si el índice no existe
# texto[10]  # ¡ERROR!
```

**Slicing (Rebanadas):**
```python
texto = "Python Programming"

# Sintaxis: [inicio:fin:paso]
texto[0:6]    # "Python" (caracteres 0 a 5)
texto[7:18]   # "Programming"

# Omitir inicio (desde el principio)
texto[:6]     # "Python"

# Omitir fin (hasta el final)
texto[7:]     # "Programming"

# Con paso
texto[::2]    # "Pto rgamn" (cada 2do carácter)
texto[1::2]   # "yhnPoamig" (cada 2do desde índice 1)

# Invertir string
texto[::-1]   # "gnimmargorP nohtyP"

# Rangos negativos
texto[-11:-1] # "Programmin"
texto[:-1]    # "Python Programmin" (sin último carácter)
```

**Ejemplos Prácticos:**
```python
# Extraer extensión de archivo
archivo = "documento.pdf"
extension = archivo[-3:]  # "pdf"

# Verificar prefijo
url = "https://ejemplo.com"
if url[:8] == "https://":
    print("URL segura")

# Censurar parte de un string
tarjeta = "1234-5678-9012-3456"
censurada = "****-****-****-" + tarjeta[-4:]  # "****-****-****-3456"
```

### 5.6 Formateo de Strings

**f-strings (Python 3.6+) - RECOMENDADO:**
```python
nombre = "Ana"
edad = 28

# Básico
mensaje = f"Hola, {nombre}"  # "Hola, Ana"

# Expresiones
resultado = f"{nombre} tiene {edad} años"  # "Ana tiene 28 años"

# Operaciones dentro de {}
precio = 19.99
iva = f"Total con IVA: ${precio * 1.21:.2f}"  # "Total con IVA: $24.19"

# Debug (Python 3.8+)
x = 10
print(f"{x=}")  # "x=10"

# Formato de números
pi = 3.14159
f"{pi:.2f}"      # "3.14" (2 decimales)
f"{pi:10.2f}"    # "      3.14" (10 caracteres, 2 decimales)
f"{pi:010.2f}"   # "0000003.14" (rellenar con ceros)

# Formato de enteros
numero = 42
f"{numero:05d}"  # "00042" (5 dígitos con ceros)
f"{numero:b}"    # "101010" (binario)
f"{numero:x}"    # "2a" (hexadecimal)

# Alineación
f"{'izq':<10}"   # "izq       " (izquierda)
f"{'centro':^10}"  # "  centro  " (centro)
f"{'der':>10}"   # "       der" (derecha)
```

**Método .format():**
```python
# Básico
"Hola, {}".format("Mundo")  # "Hola, Mundo"

# Con nombres
plantilla = "Hola, {nombre}. Tienes {edad} años"
plantilla.format(nombre="Carlos", edad=30)

# Por posición
"{0} y {1}".format("A", "B")   # "A y B"
"{1} y {0}".format("A", "B")   # "B y A"

# Con formato
"Pi: {:.2f}".format(3.14159)  # "Pi: 3.14"
```

**%-formatting (estilo antiguo, no recomendado):**
```python
# Aún funcional pero obsoleto
"Hola, %s" % "Mundo"           # "Hola, Mundo"
"%d + %d = %d" % (5, 3, 8)     # "5 + 3 = 8"
"Pi: %.2f" % 3.14159           # "Pi: 3.14"
```

### 5.7 Raw Strings

**Strings Crudos (Raw):**
```python
# Normal string - interpreta escapes
normal = "C:\new\test"  # \n y \t son interpretados
print(normal)  # C:
               # ew	est

# Raw string - NO interpreta escapes
raw = r"C:\new\test"
print(raw)  # C:\new\test

# Útil para:
# - Rutas de Windows
ruta = r"C:\Users\Documents\file.txt"

# - Expresiones regulares
patron = r"\d{3}-\d{3}-\d{4}"  # Patrón de teléfono

# - Strings con muchos backslashes
latex = r"\begin{equation} x^2 + y^2 = r^2 \end{equation}"
```

### 5.8 Verificación de Contenido

```python
texto = "Python3"

# Tipo de contenido
texto.isalpha()    # False (contiene número)
texto.isdigit()    # False (contiene letras)
texto.isalnum()    # True (alfanumérico)
texto.isspace()    # False
"123".isdigit()    # True
"   ".isspace()    # True

# Verificaciones de formato
"python".islower()  # True
"PYTHON".isupper()  # True
"123abc".isalnum()  # True
```

### 5.9 Strings son Inmutables

```python
# Importante: los strings NO se pueden modificar
texto = "Python"

# ❌ Esto NO funciona
# texto[0] = "J"  # TypeError

# ✅ Debes crear un nuevo string
texto = "J" + texto[1:]  # "Jython"

# Los métodos retornan NUEVOS strings
original = "python"
mayuscula = original.upper()  # Nuevo string
print(original)   # "python" (sin cambios)
print(mayuscula)  # "PYTHON"
```

**📚 Documentación Oficial:**
- Tutorial de Strings: https://docs.python.org/es/3/tutorial/introduction.html#strings
- Métodos de strings: https://docs.python.org/3/library/stdtypes.html#string-methods
- Formateo de strings: https://docs.python.org/3/library/string.html#formatstrings
- f-strings (PEP 498): https://peps.python.org/pep-0498/

---

