# Clase 2: Python Básico - Strings, Matemáticas y Condicionales

## 📚 Índice de Contenidos

1. [Strings (Cadenas de Texto)](#strings)
2. [Numbers & Math (Números y Matemáticas)](#numbers-math)
3. [Conditionals (Condicionales)](#conditionals)
4. [Ejercicios Prácticos](#ejercicios)

---

## 1. Strings (Cadenas de Texto) {#strings}

### ¿Qué es un String?

Un **string** (cadena) es una secuencia de caracteres. En Python, los strings se utilizan para representar texto. Piensa en un string como una caja que contiene palabras, letras, números o símbolos.

**📖 Documentación Oficial:** [Python Strings](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)

### 1.1 Creando Strings

En Python, puedes crear strings usando comillas simples (`'`), comillas dobles (`"`), o comillas triples (`"""` o `'''`).

```python
# Comillas simples
simple = 'Hola'

# Comillas dobles (RECOMENDADO)
doble = "Mundo"

# Comillas triples para múltiples líneas
multi = """Esta es una cadena
que ocupa varias
líneas de texto"""
```

**💡 Buena Práctica:** Se recomienda usar **comillas dobles** por convención y consistencia.

**¿Cuándo usar cada tipo?**
- **Comillas simples o dobles:** Para texto en una sola línea
- **Comillas triples:** Para texto que ocupa múltiples líneas o docstrings

**Ejemplo práctico:**
```python
nombre = "María"
mensaje = "Hola, ¿cómo estás?"
parrafo = """Python es un lenguaje de programación
muy versátil y fácil de aprender.
Es perfecto para principiantes."""

print(nombre)    # María
print(mensaje)   # Hola, ¿cómo estás?
print(parrafo)   # Imprime las tres líneas
```

### 1.2 Operaciones con Strings

#### Concatenación (+)
Unir dos o más strings usando el operador `+`:

```python
saludo = "Hola" + " " + "Mundo"
print(saludo)  # "Hola Mundo"

# Ejemplo práctico
nombre = "Ana"
apellido = "García"
nombre_completo = nombre + " " + apellido
print(nombre_completo)  # "Ana García"
```

#### Repetición (*)
Repetir un string múltiples veces usando el operador `*`:

```python
risa = "ja" * 3
print(risa)  # "jajaja"

separador = "-" * 20
print(separador)  # "--------------------"
```

#### Longitud (len)
Contar cuántos caracteres tiene un string:

```python
palabra = "Python"
longitud = len(palabra)
print(longitud)  # 6

# Los espacios también cuentan
frase = "Hola Mundo"
print(len(frase))  # 10 (incluye el espacio)
```

### 1.3 Métodos de Strings

Los strings tienen métodos incorporados que nos permiten manipularlos. Un **método** es una función que pertenece a un objeto.

**📖 Documentación:** [String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods)

#### Cambiar Mayúsculas/Minúsculas

```python
texto = "hola mundo"

# Convertir a mayúsculas
print(texto.upper())  # "HOLA MUNDO"

# Convertir a minúsculas
texto2 = "HOLA MUNDO"
print(texto2.lower())  # "hola mundo"

# Primera letra en mayúscula
print(texto.capitalize())  # "Hola mundo"

# Cada palabra con mayúscula inicial
print(texto.title())  # "Hola Mundo"
```

#### Eliminar Espacios

```python
# strip() elimina espacios al inicio y final
texto = "   hola   "
print(texto.strip())  # "hola"

# lstrip() elimina espacios a la izquierda
print(texto.lstrip())  # "hola   "

# rstrip() elimina espacios a la derecha
print(texto.rstrip())  # "   hola"
```

#### Reemplazar Texto

```python
frase = "Me gusta Python"
nueva_frase = frase.replace("Python", "programar")
print(nueva_frase)  # "Me gusta programar"

# Ejemplo: corregir errores de escritura
texto = "Hola mundu"
texto_corregido = texto.replace("mundu", "mundo")
print(texto_corregido)  # "Hola mundo"
```

#### Dividir y Unir Strings

```python
# split() divide un string en una lista
frase = "Python es genial"
palabras = frase.split()
print(palabras)  # ["Python", "es", "genial"]

# Dividir por un separador específico
fecha = "15-03-2024"
partes = fecha.split("-")
print(partes)  # ["15", "03", "2024"]

# join() une elementos de una lista
palabras = ["Hola", "a", "todos"]
frase = " ".join(palabras)
print(frase)  # "Hola a todos"

# Unir con otro separador
numeros = ["1", "2", "3"]
resultado = "-".join(numeros)
print(resultado)  # "1-2-3"
```

#### Buscar en Strings

```python
texto = "Python es poderoso"

# Verificar si contiene algo
print("Python" in texto)  # True
print("Java" in texto)    # False

# Encontrar la posición
print(texto.find("es"))  # 7 (índice donde empieza)
print(texto.find("Java"))  # -1 (no encontrado)

# Contar ocurrencias
frase = "la casa de la esquina de la ciudad"
print(frase.count("la"))  # 3
```

### 1.4 Indexing y Slicing (Indexación y Rebanado)

Los strings son **secuencias**, lo que significa que podemos acceder a caracteres individuales o grupos de caracteres.

**📖 Documentación:** [Sequence Types](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)

#### Indexación (Acceder a caracteres individuales)

En Python, los índices comienzan en **0**.

```python
texto = "Python"

# Acceder por índice positivo (de izquierda a derecha)
print(texto[0])  # "P" (primer carácter)
print(texto[1])  # "y" (segundo carácter)
print(texto[5])  # "n" (último carácter)

# Acceder por índice negativo (de derecha a izquierda)
print(texto[-1])  # "n" (último carácter)
print(texto[-2])  # "o" (penúltimo carácter)
print(texto[-6])  # "P" (primer carácter)
```

**Visualización de índices:**
```
Palabra:  P  y  t  h  o  n
Positivo: 0  1  2  3  4  5
Negativo:-6 -5 -4 -3 -2 -1
```

#### Slicing (Rebanado)

El slicing permite extraer sub-strings (porciones de texto).

**Sintaxis:** `texto[inicio:fin:paso]`
- `inicio`: donde comienza (incluido)
- `fin`: donde termina (NO incluido)
- `paso`: de cuánto en cuánto (opcional)

```python
texto = "Python"

# Slicing básico
print(texto[1:4])   # "yth" (índices 1, 2, 3)
print(texto[0:3])   # "Pyt" (índices 0, 1, 2)

# Omitir el inicio (comienza desde 0)
print(texto[:3])    # "Pyt" (equivalente a [0:3])

# Omitir el fin (va hasta el final)
print(texto[3:])    # "hon" (desde índice 3 hasta el final)

# Con paso
print(texto[::2])   # "Pto" (cada 2 caracteres)
print(texto[::3])   # "Ph" (cada 3 caracteres)

# Invertir un string
print(texto[::-1])  # "nohtyP" (paso negativo invierte)
```

**Ejemplos prácticos:**

```python
email = "usuario@ejemplo.com"

# Extraer el usuario
usuario = email[:email.find("@")]
print(usuario)  # "usuario"

# Extraer el dominio
dominio = email[email.find("@")+1:]
print(dominio)  # "ejemplo.com"

# Obtener solo las vocales
palabra = "programacion"
vocales = palabra[::2]  # No es la mejor forma, solo ejemplo
print(vocales)
```

### 1.5 String Formatting (Formateo de Strings)

El formateo nos permite insertar valores dentro de strings de manera dinámica.

**📖 Documentación:** [f-strings](https://docs.python.org/3/reference/lexical_analysis.html#f-strings) | [format()](https://docs.python.org/3/library/stdtypes.html#str.format)

#### F-Strings (Recomendado) ⭐

Las **f-strings** son la forma moderna y más legible de formatear strings en Python (Python 3.6+).

```python
nombre = "Carlos"
edad = 25

# Sintaxis básica
mensaje = f"Hola, me llamo {nombre}"
print(mensaje)  # "Hola, me llamo Carlos"

# Con múltiples variables
presentacion = f"{nombre} tiene {edad} años"
print(presentacion)  # "Carlos tiene 25 años"

# Con expresiones
precio = 100
mensaje = f"El total es ${precio * 1.21} con IVA"
print(mensaje)  # "El total es $121.0 con IVA"

# Debug (muestra nombre y valor)
print(f"{edad=}")  # "edad=25"
```

**Formateo de números:**

```python
pi = 3.14159265359

# Limitar decimales
print(f"Pi es aproximadamente {pi:.2f}")  # "Pi es aproximadamente 3.14"

# Ancho fijo
numero = 42
print(f"Número: {numero:5}")  # "Número:    42" (5 espacios totales)

# Con separador de miles
grande = 1000000
print(f"Un millón: {grande:,}")  # "Un millón: 1,000,000"
```

#### Método format()

```python
# Sintaxis básica
template = "Hola, {nombre}! Tienes {edad} años."
resultado = template.format(nombre="Ana", edad=30)
print(resultado)  # "Hola, Ana! Tienes 30 años."

# Por posición
mensaje = "Me gusta {} y {}".format("Python", "JavaScript")
print(mensaje)  # "Me gusta Python y JavaScript"

# Por índice
texto = "{1} viene antes que {0}".format("primero", "segundo")
print(texto)  # "segundo viene antes que primero"
```

### 1.6 Raw Strings (Strings Crudos)

Los **raw strings** tratan las barras invertidas `\` de forma literal, sin interpretarlas como caracteres de escape.

```python
# String normal (interpreta \t como tabulación)
normal = "Ruta: C:\nueva\carpeta"
print(normal)  # Puede mostrar caracteres extraños

# Raw string (trata \ como carácter literal)
raw = r"Ruta: C:\nueva\carpeta"
print(raw)  # "Ruta: C:\nueva\carpeta"

# Útil para expresiones regulares y rutas de Windows
ruta = r"C:\Users\Usuario\Documents"
print(ruta)  # "C:\Users\Usuario\Documents"
```

**Caracteres de escape comunes:**
- `\n` - Nueva línea
- `\t` - Tabulación
- `\\` - Barra invertida literal
- `\"` - Comilla doble literal
- `\'` - Comilla simple literal

```python
# Con caracteres de escape
print("Línea 1\nLínea 2")  # Imprime en dos líneas
print("Columna1\tColumna2")  # Con tabulación

# Para incluir comillas
print("Él dijo: \"Hola\"")  # Él dijo: "Hola"
```

---

## 2. Numbers & Math (Números y Matemáticas) {#numbers-math}

### Tipos de Números en Python

Python tiene principalmente dos tipos de números:
- **int** (enteros): números sin decimales
- **float** (flotantes): números con decimales

**📖 Documentación:** [Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)

```python
# Enteros
edad = 25
temperatura = -5
grande = 1000000

# Flotantes
precio = 19.99
pi = 3.14159
temperatura_celsius = 36.5

# Verificar tipo
print(type(10))    # <class 'int'>
print(type(10.0))  # <class 'float'>
```

### 2.1 Operadores Aritméticos

**📖 Documentación:** [Arithmetic Operators](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)

```python
# Suma (+)
resultado = 10 + 3
print(resultado)  # 13

# Resta (-)
resultado = 10 - 3
print(resultado)  # 7

# Multiplicación (*)
resultado = 10 * 3
print(resultado)  # 30

# División (/) - SIEMPRE devuelve float
resultado = 10 / 3
print(resultado)  # 3.3333333333333335

# División entera (//) - descarta decimales
resultado = 10 // 3
print(resultado)  # 3

# Módulo (%) - devuelve el resto de la división
resultado = 10 % 3
print(resultado)  # 1

# Potencia (**)
resultado = 2 ** 3
print(resultado)  # 8 (2 elevado a 3)
```

**Ejemplos prácticos:**

```python
# Calcular área de un rectángulo
base = 10
altura = 5
area = base * altura
print(f"El área es {area} metros cuadrados")

# Calcular promedio
nota1 = 8
nota2 = 7
nota3 = 9
promedio = (nota1 + nota2 + nota3) / 3
print(f"El promedio es {promedio:.2f}")

# Verificar si un número es par
numero = 8
es_par = numero % 2 == 0
print(f"¿{numero} es par? {es_par}")  # True

# Calcular cuántos paquetes se necesitan
total_items = 27
items_por_paquete = 5
paquetes = total_items // items_por_paquete + (1 if total_items % items_por_paquete > 0 else 0)
print(f"Se necesitan {paquetes} paquetes")  # 6 paquetes
```

### 2.2 Funciones Matemáticas Útiles

**📖 Documentación:** [Built-in Functions](https://docs.python.org/3/library/functions.html)

#### abs() - Valor Absoluto

```python
# Devuelve el valor sin signo
print(abs(-5))   # 5
print(abs(5))    # 5
print(abs(-3.7)) # 3.7

# Útil para calcular diferencias
temperatura_actual = 18
temperatura_ideal = 22
diferencia = abs(temperatura_actual - temperatura_ideal)
print(f"Diferencia: {diferencia}°C")  # 4°C
```

#### round() - Redondear

```python
# Redondear al entero más cercano
print(round(3.7))  # 4
print(round(3.4))  # 3
print(round(3.5))  # 4

# Redondear a N decimales
print(round(3.14159, 2))  # 3.14
print(round(3.14159, 4))  # 3.1416

# Uso práctico: redondear precios
precio = 19.876
precio_final = round(precio, 2)
print(f"Precio: ${precio_final}")  # $19.88
```

#### min() y max() - Mínimo y Máximo

```python
# Encontrar el menor
print(min(3, 1, 2))  # 1
print(min(10, 5, 8, 3, 12))  # 3

# Encontrar el mayor
print(max(3, 1, 2))  # 3
print(max(10, 5, 8, 3, 12))  # 12

# Con listas
temperaturas = [22, 25, 19, 30, 18]
print(f"Temperatura mínima: {min(temperaturas)}°C")  # 18°C
print(f"Temperatura máxima: {max(temperaturas)}°C")  # 30°C
```

#### sum() - Suma de elementos

```python
# Sumar elementos de una lista
numeros = [1, 2, 3, 4, 5]
total = sum(numeros)
print(total)  # 15

# Calcular promedio combinando sum() y len()
notas = [8, 7, 9, 6, 10]
promedio = sum(notas) / len(notas)
print(f"Promedio: {promedio}")  # 8.0

# Sumar precios
precios = [19.99, 5.50, 12.30]
total_compra = sum(precios)
print(f"Total: ${total_compra:.2f}")  # $37.79
```

### 2.3 El Módulo math

Para operaciones más avanzadas, Python tiene el módulo `math`:

**📖 Documentación:** [math module](https://docs.python.org/3/library/math.html)

```python
import math

# Raíz cuadrada
print(math.sqrt(16))  # 4.0

# Potencia (alternativa a **)
print(math.pow(2, 3))  # 8.0

# Redondear hacia arriba y hacia abajo
print(math.ceil(3.2))   # 4 (techo)
print(math.floor(3.8))  # 3 (piso)

# Constantes
print(math.pi)  # 3.141592653589793
print(math.e)   # 2.718281828459045
```

---

## 3. Conditionals (Condicionales) {#conditionals}

Los **condicionales** permiten que tu programa tome decisiones y ejecute diferentes bloques de código según las condiciones.

**📖 Documentación:** [Control Flow](https://docs.python.org/3/tutorial/controlflow.html)

### 3.1 Indentación en Python

⚠️ **MUY IMPORTANTE:** Python usa **indentación** (espacios al inicio) para definir bloques de código.

**Reglas:**
- Usa **4 espacios** por nivel de indentación (estándar PEP 8)
- NO mezcles tabs y espacios
- Todo el código dentro de un bloque debe tener la misma indentación

```python
# ✅ CORRECTO
if edad >= 18:
    print("Eres mayor de edad")
    print("Puedes votar")

# ❌ INCORRECTO (diferente indentación)
if edad >= 18:
    print("Eres mayor de edad")
  print("Error: indentación inconsistente")
```

### 3.2 If-Elif-Else

#### Estructura básica: if

```python
edad = 20

if edad >= 18:
    print("Eres mayor de edad")
```

#### If-Else (Si-Sino)

```python
temperatura = 15

if temperatura > 25:
    print("Hace calor")
else:
    print("No hace calor")
```

#### If-Elif-Else (Si-Sino Si-Sino)

```python
edad = 16

if edad < 13:
    categoria = "niño"
elif edad < 20:
    categoria = "adolescente"
else:
    categoria = "adulto"

print(f"Categoría: {categoria}")
```

**Ejemplo práctico: Sistema de calificaciones**

```python
nota = 85

if nota >= 90:
    calificacion = "A - Excelente"
elif nota >= 80:
    calificacion = "B - Muy Bien"
elif nota >= 70:
    calificacion = "C - Bien"
elif nota >= 60:
    calificacion = "D - Suficiente"
else:
    calificacion = "F - Insuficiente"

print(f"Tu calificación es: {calificacion}")
```

### 3.3 Operadores de Comparación

Estos operadores devuelven `True` o `False`:

**📖 Documentación:** [Comparisons](https://docs.python.org/3/library/stdtypes.html#comparisons)

```python
x = 10
y = 5

# Igual a (==)
print(x == y)  # False
print(x == 10)  # True

# No igual a (!=)
print(x != y)  # True

# Menor que (<)
print(x < y)  # False

# Menor o igual que (<=)
print(x <= 10)  # True

# Mayor que (>)
print(x > y)  # True

# Mayor o igual que (>=)
print(x >= 10)  # True
```

**⚠️ Cuidado:** No confundir `=` (asignación) con `==` (comparación)

```python
# = es asignación
edad = 18  # Asigna el valor 18 a edad

# == es comparación
if edad == 18:  # Compara si edad es igual a 18
    print("Tienes 18 años")
```

### 3.4 Operadores Lógicos

Los operadores lógicos combinan múltiples condiciones:

**📖 Documentación:** [Boolean Operations](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)

#### AND (y)
Ambas condiciones deben ser verdaderas:

```python
edad = 20
tiene_licencia = True

# Ambas condiciones deben cumplirse
if edad >= 18 and tiene_licencia:
    print("Puedes conducir")
else:
    print("No puedes conducir")

# Múltiples condiciones
temperatura = 22
soleado = True
fin_de_semana = True

if temperatura > 20 and soleado and fin_de_semana:
    print("¡Perfecto para ir a la playa!")
```

#### OR (o)
Al menos una condición debe ser verdadera:

```python
es_fin_de_semana = True
es_feriado = False

if es_fin_de_semana or es_feriado:
    print("No hay que trabajar")
else:
    print("Hay que trabajar")

# Ejemplo: descuento
edad = 70
es_estudiante = False

if edad >= 65 or es_estudiante:
    print("Tienes descuento del 20%")
```

#### NOT (no)
Invierte el valor de verdad:

```python
esta_lloviendo = False

if not esta_lloviendo:
    print("Puedes salir sin paraguas")

# Equivalente a:
if esta_lloviendo == False:
    print("Puedes salir sin paraguas")

# Ejemplo práctico
usuario_bloqueado = False

if not usuario_bloqueado:
    print("Acceso permitido")
else:
    print("Acceso denegado")
```

#### Combinando operadores

```python
edad = 25
tiene_experiencia = True
tiene_titulo = False

# Combinar AND y OR
if edad >= 18 and (tiene_experiencia or tiene_titulo):
    print("Cumples los requisitos para el trabajo")
else:
    print("No cumples los requisitos")

# Otro ejemplo
temperatura = 28
hora = 14
es_verano = True

if temperatura > 25 and (hora >= 12 and hora <= 18) and es_verano:
    print("Hora perfecta para ir a la piscina")
```

### 3.5 Valores Truthy y Falsy

En Python, algunos valores se consideran "falsos" en contextos booleanos:

**📖 Documentación:** [Truth Value Testing](https://docs.python.org/3/library/stdtypes.html#truth-value-testing)

**Valores Falsy (se evalúan como False):**
- `False`
- `None`
- `0` (cero)
- `0.0` (cero flotante)
- `""` (string vacío)
- `[]` (lista vacía)
- `{}` (diccionario vacío)
- `()` (tupla vacía)

**Valores Truthy (se evalúan como True):**
- Todo lo demás

```python
# String vacío es falsy
nombre = ""
if nombre:
    print(f"Hola, {nombre}")
else:
    print("No ingresaste un nombre")

# Lista vacía es falsy
tareas = []
if tareas:
    print(f"Tienes {len(tareas)} tareas pendientes")
else:
    print("No tienes tareas pendientes")

# Número cero es falsy
saldo = 0
if saldo:
    print(f"Tu saldo es ${saldo}")
else:
    print("Tu saldo está vacío")
```

### 3.6 Operador Ternario (Condicional en una línea)

```python
# Sintaxis: valor_si_true if condicion else valor_si_false
edad = 20
mensaje = "Mayor" if edad >= 18 else "Menor"
print(mensaje)  # "Mayor"

# Ejemplo: calcular precio con descuento
precio = 100
es_miembro = True
precio_final = precio * 0.8 if es_miembro else precio
print(f"Precio: ${precio_final}")  # $80.0 si es miembro

# Comparar números
a = 10
b = 5
mayor = a if a > b else b
print(f"El mayor es: {mayor}")  # 10
```

---

## 4. Ejercicios Prácticos {#ejercicios}

### Ejercicio 1: Manipulación de Strings ⭐

**Objetivo:** Practicar métodos de strings y slicing.

Escribe un programa que:
1. Pida al usuario su nombre completo
2. Convierta el nombre a mayúsculas
3. Cuente cuántos caracteres tiene (sin espacios)
4. Muestre solo las iniciales del nombre

```python
# Ejemplo de solución esperada
# Entrada: "Juan Carlos Pérez"
# Salida:
# Nombre en mayúsculas: JUAN CARLOS PÉREZ
# Cantidad de caracteres (sin espacios): 15
# Iniciales: JCP
```

**Pistas:**
- Usa `.upper()` para mayúsculas
- Usa `.replace(" ", "")` para eliminar espacios
- Usa `.split()` para separar las palabras
- Usa slicing `[0]` para obtener la primera letra

---

### Ejercicio 2: Calculadora de Propinas ⭐⭐

**Objetivo:** Practicar operaciones matemáticas y formateo.

Crea un programa que:
1. Pida el monto total de una cuenta
2. Pida el porcentaje de propina (10, 15 o 20)
3. Calcule la propina y el total a pagar
4. Muestre los resultados con 2 decimales

```python
# Ejemplo esperado:
# Entrada: monto = 150, propina = 15%
# Salida:
# Subtotal: $150.00
# Propina (15%): $22.50
# Total: $172.50
```

**Pistas:**
- Propina = monto * (porcentaje / 100)
- Usa f-strings con `:.2f` para formatear

---

### Ejercicio 3: Validador de Contraseñas ⭐⭐

**Objetivo:** Practicar condicionales y operadores lógicos.

Crea un validador de contraseñas que verifique:
1. La contraseña tiene al menos 8 caracteres
2. Contiene al menos un número
3. No es igual a "password123"

Si cumple todas las condiciones, muestra "Contraseña válida", sino "Contraseña inválida".

```python
# Ejemplo:
# contraseña = "MiClave2024"
# Salida: Contraseña válida (cumple todas las condiciones)

# contraseña = "corta"
# Salida: Contraseña inválida (menos de 8 caracteres)
```

**Pistas:**
- Usa `len()` para verificar longitud
- Usa `.isdigit()` o `any()` para verificar números
- Combina condiciones con `and`

---

### Ejercicio 4: Clasificador de Edades ⭐⭐

**Objetivo:** Practicar if-elif-else y operadores de comparación.

Crea un programa que clasifique personas según su edad:
- 0-12 años: Niño
- 13-17 años: Adolescente  
- 18-64 años: Adulto
- 65+ años: Adulto Mayor

Además, indica si puede votar (18+) y si tiene descuento (< 12 o >= 65).

```python
# Ejemplo:
# edad = 70
# Salida:
# Categoría: Adulto Mayor
# ¿Puede votar?: Sí
# ¿Tiene descuento?: Sí
```

---

### Ejercicio 5: Formateador de Emails ⭐⭐⭐

**Objetivo:** Integrar strings, métodos y condicionales.

Crea un programa que:
1. Pida nombre y apellido al usuario
2. Genere un email corporativo con el formato: `nombre.apellido@empresa.com`
3. Todo en minúsculas y sin espacios extras
4. Si el nombre o apellido tiene más de 10 letras, use solo las primeras 10

```python
# Ejemplo 1:
# nombre = "María José"
# apellido = "González"
# Salida: mariajose.gonzalez@empresa.com

# Ejemplo 2:
# nombre = "Maximiliano"
# apellido = "Hernández"
# Salida: maximilian.hernandez@empresa.com
```

**Pistas:**
- Usa `.lower()` y `.strip()`
- Usa `.replace(" ", "")` para eliminar espacios
- Usa slicing `[:10]` para limitar caracteres
- Usa f-strings para construir el email

---

## 📚 Recursos Adicionales

### Documentación Oficial Python
- [Tutorial Oficial de Python](https://docs.python.org/3/tutorial/)
- [Strings en Python](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)
- [Operadores Numéricos](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
- [Estructuras de Control](https://docs.python.org/3/tutorial/controlflow.html)

### Para Practicar
- [Real Python - Strings and Character Data](https://realpython.com/python-strings/)
- [Real Python - Operators and Expressions](https://realpython.com/python-operators-expressions/)
- [Real Python - Conditional Statements](https://realpython.com/python-conditional-statements/)

---

## 🎯 Resumen de Conceptos Clave

### Strings
✅ Los strings son secuencias de caracteres  
✅ Usa comillas dobles por convención  
✅ Métodos útiles: `.upper()`, `.lower()`, `.strip()`, `.replace()`, `.split()`, `.join()`  
✅ Slicing: `texto[inicio:fin:paso]`  
✅ F-strings son la mejor forma de formatear: `f"Hola {nombre}"`  

### Numbers & Math
✅ Operadores: `+`, `-`, `*`, `/`, `//`, `%`, `**`  
✅ Funciones útiles: `abs()`, `round()`, `min()`, `max()`, `sum()`  
✅ División `/` siempre devuelve float  
✅ División entera `//` descarta decimales  

### Conditionals
✅ Python usa indentación (4 espacios)  
✅ Estructura: `if`, `elif`, `else`  
✅ Operadores de comparación: `==`, `!=`, `<`, `>`, `<=`, `>=`  
✅ Operadores lógicos: `and`, `or`, `not`  
✅ Valores falsy: `False`, `None`, `0`, `""`, `[]`, `{}`  

---

**¡Éxito en tu aprendizaje de Python! 🐍✨**
