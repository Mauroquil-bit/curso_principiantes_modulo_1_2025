# Clase 3: Números, Matemáticas y Decisiones en Python

## 📚 Índice de Contenidos

1. [Números en Python](#numeros)
2. [Operadores Aritméticos](#operadores)
3. [Funciones Matemáticas Útiles](#funciones)
4. [Condicionales: Tomando Decisiones](#condicionales)
5. [Ejercicios Prácticos](#ejercicios)
6. [Recursos Adicionales](#recursos)
7. [Resumen de Conceptos Clave](#resumen)

---

## 1. Números en Python {#numeros}

En Python, trabajamos constantemente con números. Ya sea para calcular precios, contar elementos, medir distancias o tomar decisiones basadas en valores numéricos, entender cómo funcionan los números es fundamental.

**📖 Documentación Oficial:** [Numeric Types - int, float](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)

### Tipos de números: int y float

Python tiene dos tipos principales de números:

#### **int** (Enteros)
Los **enteros** son números sin decimales. Pueden ser positivos, negativos o cero.

```python
# Ejemplos de enteros
edad = 25
temperatura = -5
poblacion = 1000000
puntos = 0

# Verificar el tipo
print(type(edad))  # <class 'int'>
```

**Casos de uso comunes:**
- Contar elementos (cantidad de estudiantes, productos en stock)
- Representar edades, años
- Números de identificación
- Posiciones o índices

#### **float** (Flotantes)
Los **flotantes** son números con decimales (punto flotante).

```python
# Ejemplos de flotantes
precio = 19.99
pi = 3.14159
temperatura_corporal = 36.5
descuento = 0.15

# Verificar el tipo
print(type(precio))  # <class 'float'>
```

**Casos de uso comunes:**
- Precios y valores monetarios
- Mediciones precisas (peso, altura, temperatura)
- Porcentajes
- Cálculos científicos

⚠️ **Importante:** En Python, usamos el **punto** (`.`) como separador decimal, no la coma.

```python
# ✅ CORRECTO
precio = 19.99

# ❌ INCORRECTO
precio = 19,99  # Esto crea algo diferente (una tupla)
```

### Conversión entre tipos

A veces necesitamos convertir números de un tipo a otro.

**📖 Documentación:** [Built-in Functions - Type Conversion](https://docs.python.org/3/library/functions.html)

```python
# Convertir string a entero
edad_texto = "25"
edad_numero = int(edad_texto)
print(edad_numero + 5)  # 30

# Convertir string a flotante
precio_texto = "19.99"
precio_numero = float(precio_texto)
print(precio_numero * 2)  # 39.98

# Convertir flotante a entero (descarta decimales)
precio = 19.99
precio_entero = int(precio)
print(precio_entero)  # 19

# Convertir entero a flotante
edad = 25
edad_flotante = float(edad)
print(edad_flotante)  # 25.0

# Convertir número a string
puntos = 100
mensaje = "Tienes " + str(puntos) + " puntos"
print(mensaje)  # "Tienes 100 puntos"
```

**Ejemplo práctico con input():**

Recuerda que `input()` siempre devuelve un **string**. Para hacer operaciones matemáticas, debemos convertir:

```python
# Sin conversión (concatena strings)
numero = input("Ingresa un número: ")  # Usuario escribe: 5
resultado = numero + numero
print(resultado)  # "55" (concatenación)

# Con conversión (suma números)
numero = int(input("Ingresa un número: "))  # Usuario escribe: 5
resultado = numero + numero
print(resultado)  # 10 (suma matemática)
```

💡 **Buena Práctica:** Siempre convierte los valores de `input()` al tipo correcto antes de hacer operaciones.

---

## 2. Operadores Aritméticos {#operadores}

Los operadores aritméticos nos permiten realizar cálculos matemáticos. Python soporta todas las operaciones matemáticas básicas y algunas avanzadas.

**📖 Documentación:** [Binary Arithmetic Operations](https://docs.python.org/3/reference/expressions.html#binary-arithmetic-operations)

### Operaciones básicas

#### Suma (+)
```python
# Suma de enteros
resultado = 10 + 3
print(resultado)  # 13

# Suma de flotantes
precio1 = 15.50
precio2 = 8.25
total = precio1 + precio2
print(total)  # 23.75

# Mezcla de int y float (resultado es float)
suma = 10 + 3.5
print(suma)  # 13.5
print(type(suma))  # <class 'float'>
```

**Ejemplo práctico:**
```python
# Calculadora de gastos
desayuno = 5.50
almuerzo = 12.00
cena = 8.75
total_dia = desayuno + almuerzo + cena
print(f"Gastos del día: ${total_dia}")  # Gastos del día: $26.25
```

#### Resta (-)
```python
# Resta básica
resultado = 10 - 3
print(resultado)  # 7

# Números negativos
temperatura_actual = 5
cambio = -3
nueva_temperatura = temperatura_actual + cambio
print(nueva_temperatura)  # 2
```

**Ejemplo práctico:**
```python
# Calcular vuelto
pago = 50
precio = 37.50
vuelto = pago - precio
print(f"Tu vuelto es: ${vuelto}")  # Tu vuelto es: $12.5
```

#### Multiplicación (*)
```python
# Multiplicación básica
resultado = 10 * 3
print(resultado)  # 30

# Calcular área
base = 10
altura = 5
area = base * altura
print(f"El área es {area} m²")  # El área es 50 m²
```

**Ejemplo práctico:**
```python
# Calcular precio total con cantidad
precio_unitario = 25.50
cantidad = 4
total = precio_unitario * cantidad
print(f"Total: ${total}")  # Total: $102.0
```

#### División (/)
⚠️ **Importante:** La división **SIEMPRE** devuelve un **float**, incluso si el resultado es entero.

```python
# División que da entero
resultado = 10 / 2
print(resultado)  # 5.0 (float, no int)
print(type(resultado))  # <class 'float'>

# División con decimales
resultado = 10 / 3
print(resultado)  # 3.3333333333333335

# División exacta
resultado = 15 / 3
print(resultado)  # 5.0
```

**Ejemplo práctico:**
```python
# Calcular promedio
suma_notas = 85
cantidad_examenes = 4
promedio = suma_notas / cantidad_examenes
print(f"Tu promedio es: {promedio}")  # Tu promedio es: 21.25
```

⚠️ **¡Cuidado!** No puedes dividir entre cero:
```python
# ❌ Esto produce un error
resultado = 10 / 0  # ZeroDivisionError
```

### División entera y módulo

#### División Entera (//)
La **división entera** descarta la parte decimal y devuelve solo el número entero.

```python
# División entera
resultado = 10 // 3
print(resultado)  # 3 (descarta .3333...)

# Comparación con división normal
normal = 10 / 3
entera = 10 // 3
print(f"División normal: {normal}")   # 3.3333333333333335
print(f"División entera: {entera}")   # 3

# Otros ejemplos
print(17 // 5)   # 3
print(20 // 6)   # 3
print(15 // 3)   # 5
```

**Ejemplo práctico:**
```python
# Calcular cuántas cajas completas necesitas
total_items = 27
items_por_caja = 5
cajas_completas = total_items // items_por_caja
print(f"Necesitas {cajas_completas} cajas completas")  # 5 cajas
```

#### Módulo (%)
El **módulo** devuelve el **resto** de una división.

```python
# Módulo básico
resto = 10 % 3
print(resto)  # 1 (porque 10 ÷ 3 = 3 con resto 1)

# Otros ejemplos
print(17 % 5)   # 2 (17 = 5×3 + 2)
print(20 % 6)   # 2 (20 = 6×3 + 2)
print(15 % 3)   # 0 (división exacta, sin resto)
```

**Visualización:**
```
10 ÷ 3 = 3 con resto 1
│       │         │
│       │         └─ Módulo (%)
│       └─────────── División entera (//)
└─────────────────── División normal (/)
```

**Usos prácticos del módulo:**

1️⃣ **Verificar si un número es par o impar:**
```python
numero = 8
resto = numero % 2

if resto == 0:
    print(f"{numero} es par")
else:
    print(f"{numero} es impar")
# 8 es par
```

2️⃣ **Verificar divisibilidad:**
```python
numero = 15
if numero % 3 == 0:
    print(f"{numero} es divisible entre 3")
# 15 es divisible entre 3
```

3️⃣ **Calcular items sobrantes:**
```python
total_items = 27
items_por_caja = 5
items_sobrantes = total_items % items_por_caja
print(f"Sobran {items_sobrantes} items")  # Sobran 2 items
```

### Potenciación

El operador de **potencia** (`**`) eleva un número a una potencia.

```python
# Potencia básica
resultado = 2 ** 3
print(resultado)  # 8 (2³ = 2×2×2)

# Más ejemplos
print(5 ** 2)   # 25 (5²)
print(10 ** 3)  # 1000 (10³)
print(2 ** 10)  # 1024 (2¹⁰)
```

**Casos especiales:**
```python
# Potencia de 0
print(5 ** 0)  # 1 (cualquier número elevado a 0 es 1)

# Potencia de 1
print(5 ** 1)  # 5 (cualquier número elevado a 1 es él mismo)

# Potencias negativas (dan fracciones)
print(2 ** -1)  # 0.5 (2⁻¹ = 1/2)
print(10 ** -2) # 0.01 (10⁻² = 1/100)
```

**Ejemplo práctico:**
```python
# Calcular área de un cuadrado
lado = 5
area = lado ** 2
print(f"El área del cuadrado es {area} m²")  # 25 m²

# Calcular interés compuesto (versión simplificada)
capital_inicial = 1000
tasa_interes = 1.05  # 5% anual
años = 3
capital_final = capital_inicial * (tasa_interes ** años)
print(f"Capital final: ${capital_final:.2f}")  # $1157.63
```

### Orden de operaciones

Python sigue el orden matemático estándar (PEMDAS):

1. **P**aréntesis
2. **E**xponentes (potencias)
3. **M**ultiplicación y **D**ivisión (de izquierda a derecha)
4. **A**dición y **S**ustracción (de izquierda a derecha)

```python
# Sin paréntesis
resultado = 2 + 3 * 4
print(resultado)  # 14 (primero 3*4=12, luego 2+12=14)

# Con paréntesis
resultado = (2 + 3) * 4
print(resultado)  # 20 (primero 2+3=5, luego 5*4=20)

# Ejemplo complejo
resultado = 10 + 2 ** 3 * 4 - 5
# Paso 1: 2 ** 3 = 8
# Paso 2: 8 * 4 = 32
# Paso 3: 10 + 32 = 42
# Paso 4: 42 - 5 = 37
print(resultado)  # 37
```

💡 **Buena Práctica:** Usa paréntesis para hacer tu código más legible, incluso si no son estrictamente necesarios.

```python
# Menos claro
total = precio * cantidad + envio

# Más claro
total = (precio * cantidad) + envio
```

---

## 3. Funciones Matemáticas Útiles {#funciones}

Python incluye funciones incorporadas que hacen operaciones matemáticas comunes más fáciles.

**📖 Documentación:** [Built-in Functions](https://docs.python.org/3/library/functions.html)

### abs() - Valor Absoluto

La función `abs()` devuelve el valor **absoluto** de un número (su distancia desde cero, siempre positiva).

```python
# Valores negativos se vuelven positivos
print(abs(-5))    # 5
print(abs(-3.7))  # 3.7

# Valores positivos permanecen igual
print(abs(5))     # 5
print(abs(3.7))   # 3.7

# Cero permanece cero
print(abs(0))     # 0
```

**Ejemplo práctico:**
```python
# Calcular diferencia de temperatura
temperatura_actual = 18
temperatura_ideal = 22
diferencia = abs(temperatura_actual - temperatura_ideal)
print(f"La diferencia de temperatura es {diferencia}°C")  # 4°C

# Calcular error absoluto
valor_esperado = 100
valor_obtenido = 95
error = abs(valor_esperado - valor_obtenido)
print(f"Error: {error}")  # Error: 5
```

### round() - Redondeo

La función `round()` redondea un número al entero más cercano, o a un número específico de decimales.

**Sintaxis:** `round(numero, decimales)`

```python
# Redondear al entero más cercano
print(round(3.7))   # 4
print(round(3.4))   # 3
print(round(3.5))   # 4
print(round(2.5))   # 2 (redondea al par más cercano)

# Redondear a N decimales
print(round(3.14159, 2))  # 3.14
print(round(3.14159, 3))  # 3.142
print(round(3.14159, 4))  # 3.1416

# Con números negativos
print(round(-3.7))  # -4
print(round(-3.4))  # -3
```

**Ejemplos prácticos:**

```python
# Redondear precios
precio = 19.876
precio_final = round(precio, 2)
print(f"Precio: ${precio_final}")  # Precio: $19.88

# Calcular promedio redondeado
suma = 85
cantidad = 4
promedio = round(suma / cantidad, 1)
print(f"Promedio: {promedio}")  # Promedio: 21.2

# Calcular porcentaje
correctas = 17
total = 20
porcentaje = round((correctas / total) * 100, 1)
print(f"Obtuviste {porcentaje}%")  # Obtuviste 85.0%
```

⚠️ **Nota sobre el redondeo:** Python usa "redondeo al par más cercano" (banker's rounding) cuando el número está exactamente a mitad de camino.

```python
print(round(2.5))  # 2 (redondea al par)
print(round(3.5))  # 4 (redondea al par)
```

### min() y max() - Mínimo y Máximo

Las funciones `min()` y `max()` encuentran el valor menor y mayor entre varios números.

```python
# Encontrar el mínimo
print(min(3, 1, 2))  # 1
print(min(10, 5, 8, 3, 12))  # 3

# Encontrar el máximo
print(max(3, 1, 2))  # 3
print(max(10, 5, 8, 3, 12))  # 12

# Con dos valores
print(min(50, 30))  # 30
print(max(50, 30))  # 50

# Con decimales
print(min(3.5, 2.1, 4.7))  # 2.1
print(max(3.5, 2.1, 4.7))  # 4.7
```

**Ejemplos prácticos:**

```python
# Comparar precios
precio1 = 45.99
precio2 = 39.99
precio3 = 42.50
precio_mas_bajo = min(precio1, precio2, precio3)
print(f"El precio más bajo es: ${precio_mas_bajo}")  # $39.99

# Encontrar la temperatura extrema
temp_lunes = 22
temp_martes = 25
temp_miercoles = 19
temp_maxima = max(temp_lunes, temp_martes, temp_miercoles)
temp_minima = min(temp_lunes, temp_martes, temp_miercoles)
print(f"Temperatura máxima: {temp_maxima}°C")  # 25°C
print(f"Temperatura mínima: {temp_minima}°C")  # 19°C

# Limitar un valor entre un rango
valor = 150
minimo_permitido = 0
maximo_permitido = 100
valor_limitado = max(minimo_permitido, min(valor, maximo_permitido))
print(valor_limitado)  # 100 (no puede exceder el máximo)
```

---

## 4. Condicionales: Tomando Decisiones {#condicionales}

Los **condicionales** son estructuras que permiten a tu programa tomar decisiones y ejecutar diferentes bloques de código según las condiciones que establezcas. Son fundamentales en la programación porque permiten que tu código "piense" y actúe de manera diferente según la situación.

**📖 Documentación:** [Control Flow - if Statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)

### La indentación en Python

⚠️ **MUY IMPORTANTE:** Python usa la **indentación** (espacios al inicio de la línea) para definir bloques de código. Esto es diferente de otros lenguajes que usan llaves `{}`.

**Reglas fundamentales:**
1. Usa **4 espacios** por nivel de indentación (estándar oficial PEP 8)
2. **NO mezcles** tabs y espacios
3. Todo el código dentro de un bloque debe tener **la misma indentación**
4. La indentación incorrecta produce **errores**

```python
# ✅ CORRECTO
if edad >= 18:
    print("Eres mayor de edad")
    print("Puedes votar")
print("Este mensaje siempre se muestra")

# ❌ INCORRECTO - Error de indentación
if edad >= 18:
    print("Eres mayor de edad")
  print("Error: indentación inconsistente")  # Solo 2 espacios

# ❌ INCORRECTO - Falta indentación
if edad >= 18:
print("Error: debe estar indentado")  # Sin espacios
```

**Visualización:**
```python
# Código sin indentación (nivel 0)
edad = 20

# Código dentro del if (nivel 1 - 4 espacios)
if edad >= 18:
    print("Mayor de edad")
    
    # Código dentro de otro if (nivel 2 - 8 espacios)
    if edad >= 21:
        print("Puedes beber en USA")
```

💡 **Consejo:** La mayoría de los editores de código están configurados para insertar 4 espacios cuando presionas Tab.

### Estructura if-elif-else

#### if (Si)

La estructura más básica: ejecuta código solo si una condición es verdadera.

```python
# Sintaxis básica
if condicion:
    # Código que se ejecuta si la condición es True
    print("La condición es verdadera")

# Ejemplo real
edad = 20

if edad >= 18:
    print("Eres mayor de edad")
# Salida: Eres mayor de edad

# Otro ejemplo
temperatura = 30

if temperatura > 25:
    print("Hace calor")
# Salida: Hace calor
```

#### if-else (Si-Sino)

Ejecuta un bloque de código si la condición es verdadera, y otro bloque diferente si es falsa.

```python
# Sintaxis
if condicion:
    # Código si la condición es True
else:
    # Código si la condición es False

# Ejemplo: verificar mayoría de edad
edad = 16

if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
# Salida: Eres menor de edad

# Ejemplo: determinar par o impar
numero = 7

if numero % 2 == 0:
    print(f"{numero} es par")
else:
    print(f"{numero} es impar")
# Salida: 7 es impar
```

#### if-elif-else (Si-Sino Si-Sino)

Permite evaluar múltiples condiciones en orden. Cuando encuentra una condición verdadera, ejecuta ese bloque y **sale**.

```python
# Sintaxis
if condicion1:
    # Código si condicion1 es True
elif condicion2:
    # Código si condicion1 es False y condicion2 es True
elif condicion3:
    # Código si condicion1 y condicion2 son False y condicion3 es True
else:
    # Código si todas las condiciones anteriores son False

# Ejemplo: categorizar por edad
edad = 16

if edad < 13:
    categoria = "niño"
elif edad < 20:
    categoria = "adolescente"
elif edad < 65:
    categoria = "adulto"
else:
    categoria = "adulto mayor"

print(f"Categoría: {categoria}")
# Salida: Categoría: adolescente
```

**Ejemplo práctico: Sistema de calificaciones**

```python
nota = 85

if nota >= 90:
    calificacion = "A - Excelente"
    mensaje = "¡Felicitaciones!"
elif nota >= 80:
    calificacion = "B - Muy Bien"
    mensaje = "Buen trabajo"
elif nota >= 70:
    calificacion = "C - Bien"
    mensaje = "Aprobado"
elif nota >= 60:
    calificacion = "D - Suficiente"
    mensaje = "Apenas aprobado"
else:
    calificacion = "F - Insuficiente"
    mensaje = "Debes estudiar más"

print(f"Tu calificación es: {calificacion}")
print(mensaje)
# Salida: 
# Tu calificación es: B - Muy Bien
# Buen trabajo
```

⚠️ **Importante:** Python evalúa las condiciones **en orden** y se detiene en la primera que es verdadera.

```python
# Este código tiene un problema
edad = 25

if edad >= 18:
    print("Mayor de edad")
elif edad >= 21:  # Esta condición NUNCA se evalúa
    print("Puedes beber en USA")
# Solo muestra: Mayor de edad

# ✅ Orden correcto (más específico primero)
if edad >= 21:
    print("Puedes beber en USA")
elif edad >= 18:
    print("Mayor de edad")
# Muestra: Puedes beber en USA
```

### Operadores de Comparación

Los **operadores de comparación** comparan dos valores y devuelven `True` (verdadero) o `False` (falso).

**📖 Documentación:** [Comparisons](https://docs.python.org/3/library/stdtypes.html#comparisons)

#### Tabla de Operadores

| Operador | Significado | Ejemplo | Resultado |
|----------|-------------|---------|-----------|
| `==` | Igual a | `5 == 5` | `True` |
| `!=` | No igual a / Diferente | `5 != 3` | `True` |
| `<` | Menor que | `3 < 5` | `True` |
| `<=` | Menor o igual que | `5 <= 5` | `True` |
| `>` | Mayor que | `5 > 3` | `True` |
| `>=` | Mayor o igual que | `5 >= 5` | `True` |

#### Ejemplos con cada operador

```python
x = 10
y = 5

# Igual a (==)
print(x == y)   # False
print(x == 10)  # True
print(5 == 5)   # True

# No igual a (!=)
print(x != y)   # True
print(x != 10)  # False

# Menor que (<)
print(x < y)    # False
print(y < x)    # True
print(5 < 10)   # True

# Menor o igual que (<=)
print(x <= 10)  # True
print(x <= 5)   # False
print(10 <= 10) # True

# Mayor que (>)
print(x > y)    # True
print(y > x)    # False

# Mayor o igual que (>=)
print(x >= 10)  # True
print(x >= 11)  # False
print(10 >= 10) # True
```

⚠️ **¡CUIDADO!** No confundir `=` con `==`:

```python
# = es ASIGNACIÓN (guardar un valor)
edad = 18  # Asigna el valor 18 a la variable edad

# == es COMPARACIÓN (verificar igualdad)
if edad == 18:  # Compara si edad es igual a 18
    print("Tienes 18 años")
```

#### Comparaciones con strings

También puedes comparar strings:

```python
nombre = "Ana"

# Igualdad exacta (sensible a mayúsculas)
print(nombre == "Ana")  # True
print(nombre == "ana")  # False

# Desigualdad
print(nombre != "Pedro")  # True

# Comparación alfabética
print("a" < "b")  # True (orden alfabético)
print("Ana" < "Pedro")  # True
```

#### Ejemplos prácticos

```python
# Verificar acceso por edad
edad = int(input("Ingresa tu edad: "))

if edad >= 18:
    print("Acceso permitido")
else:
    print("Acceso denegado - Debes ser mayor de edad")

# Verificar contraseña
password = input("Ingresa tu contraseña: ")

if password == "secreta123":
    print("Contraseña correcta")
else:
    print("Contraseña incorrecta")

# Verificar stock
stock = 5
cantidad_solicitada = 10

if cantidad_solicitada <= stock:
    print("Pedido confirmado")
else:
    print(f"Stock insuficiente. Solo tenemos {stock} unidades")
```

### Operadores Lógicos

Los **operadores lógicos** permiten combinar múltiples condiciones. Son fundamentales para crear lógica compleja.

**📖 Documentación:** [Boolean Operations](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)

#### and (y) - Ambas condiciones deben ser verdaderas

El operador `and` devuelve `True` solo si **todas** las condiciones son verdaderas.

**Tabla de verdad:**

| Condición 1 | Condición 2 | Resultado |
|-------------|-------------|-----------|
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

```python
# Sintaxis básica
if condicion1 and condicion2:
    # Se ejecuta solo si AMBAS son verdaderas

# Ejemplo: verificar rango de edad
edad = 25

if edad >= 18 and edad <= 65:
    print("Edad laboral")
# Salida: Edad laboral

# Ejemplo: verificar múltiples requisitos
edad = 20
tiene_licencia = True

if edad >= 18 and tiene_licencia:
    print("Puedes conducir")
else:
    print("No puedes conducir")
# Salida: Puedes conducir

# Múltiples condiciones con and
temperatura = 22
soleado = True
fin_de_semana = True

if temperatura > 20 and soleado and fin_de_semana:
    print("¡Perfecto para ir a la playa!")
# Salida: ¡Perfecto para ir a la playa!
```

**Ejemplos prácticos:**

```python
# Verificar credenciales de login
usuario = "admin"
password = "1234"

if usuario == "admin" and password == "1234":
    print("Acceso concedido")
else:
    print("Usuario o contraseña incorrectos")

# Verificar descuento
precio = 150
es_miembro = True

if precio >= 100 and es_miembro:
    descuento = precio * 0.20
    precio_final = precio - descuento
    print(f"Tienes 20% de descuento. Pagas: ${precio_final}")
else:
    print(f"Pagas: ${precio}")

# Verificar rango de nota
nota = 85

if nota >= 70 and nota < 80:
    print("Calificación: C - Bien")
elif nota >= 80 and nota < 90:
    print("Calificación: B - Muy Bien")
elif nota >= 90 and nota <= 100:
    print("Calificación: A - Excelente")
```

#### or (o) - Al menos una condición debe ser verdadera

El operador `or` devuelve `True` si **al menos una** de las condiciones es verdadera.

**Tabla de verdad:**

| Condición 1 | Condición 2 | Resultado |
|-------------|-------------|-----------|
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

```python
# Sintaxis básica
if condicion1 or condicion2:
    # Se ejecuta si AL MENOS UNA es verdadera

# Ejemplo: día sin trabajo
es_sabado = True
es_domingo = False

if es_sabado or es_domingo:
    print("No hay que trabajar")
else:
    print("Hay que trabajar")
# Salida: No hay que trabajar

# Ejemplo: descuento por edad o membresía
edad = 70
es_estudiante = False

if edad >= 65 or es_estudiante:
    print("Tienes descuento del 20%")
else:
    print("Precio normal")
# Salida: Tienes descuento del 20%

# Múltiples condiciones con or
dia = "martes"

if dia == "sabado" or dia == "domingo" or dia == "feriado":
    print("Día de descanso")
else:
    print("Día laboral")
# Salida: Día laboral
```

**Ejemplos prácticos:**

```python
# Verificar emergencia
temperatura = 40

if temperatura < 0 or temperatura > 38:
    print("¡ALERTA! Temperatura peligrosa")
else:
    print("Temperatura normal")

# Verificar métodos de pago aceptados
metodo_pago = "efectivo"

if metodo_pago == "efectivo" or metodo_pago == "tarjeta" or metodo_pago == "transferencia":
    print("Método de pago aceptado")
else:
    print("Método de pago no válido")

# Acceso especial
es_admin = False
es_moderador = True

if es_admin or es_moderador:
    print("Acceso a panel de administración concedido")
else:
    print("Acceso denegado")
```

#### not (no) - Invierte el valor de verdad

El operador `not` invierte el valor: `True` se convierte en `False` y viceversa.

**Tabla de verdad:**

| Condición | Resultado |
|-----------|-----------|
| True | False |
| False | True |

```python
# Sintaxis básica
if not condicion:
    # Se ejecuta si la condición es FALSE

# Ejemplo básico
esta_lloviendo = False

if not esta_lloviendo:
    print("Puedes salir sin paraguas")
# Salida: Puedes salir sin paraguas

# Equivalente a:
if esta_lloviendo == False:
    print("Puedes salir sin paraguas")

# Ejemplo: usuario no bloqueado
usuario_bloqueado = False

if not usuario_bloqueado:
    print("Acceso permitido")
else:
    print("Acceso denegado")
# Salida: Acceso permitido

# Con variables
activo = True
if not activo:
    print("Inactivo")
else:
    print("Activo")
# Salida: Activo
```

**Ejemplos prácticos:**

```python
# Verificar si NO es fin de semana
es_fin_de_semana = False

if not es_fin_de_semana:
    print("Tienes que ir a trabajar")
else:
    print("¡Es fin de semana!")

# Verificar disponibilidad
agotado = False

if not agotado:
    print("Producto disponible")
else:
    print("Producto agotado")

# Negar una comparación
edad = 15

if not (edad >= 18):
    print("Eres menor de edad")
# Equivale a: if edad < 18:
```

#### Combinando operadores lógicos

Puedes combinar `and`, `or` y `not` para crear lógica compleja. Usa paréntesis para claridad.

```python
# Combinar and y or
edad = 25
tiene_experiencia = True
tiene_titulo = False

if edad >= 18 and (tiene_experiencia or tiene_titulo):
    print("Cumples los requisitos para el trabajo")
else:
    print("No cumples los requisitos")
# Salida: Cumples los requisitos para el trabajo

# Ejemplo: acceso a contenido
es_suscriptor = False
edad = 20
contenido_gratis = True

if (es_suscriptor and edad >= 18) or contenido_gratis:
    print("Puedes ver el contenido")
else:
    print("Contenido bloqueado")
# Salida: Puedes ver el contenido

# Lógica compleja con not
temperatura = 28
hora = 14
es_verano = True
esta_nublado = False

if temperatura > 25 and hora >= 12 and hora <= 18 and es_verano and not esta_nublado:
    print("Momento perfecto para ir a la piscina")
```

**Orden de evaluación:**
1. `not` (más alta prioridad)
2. `and`
3. `or` (más baja prioridad)

```python
# Sin paréntesis
resultado = True or False and False
print(resultado)  # True (primero evalúa False and False = False, luego True or False = True)

# Con paréntesis (más claro)
resultado = True or (False and False)
print(resultado)  # True
```

💡 **Buena Práctica:** Siempre usa paréntesis cuando combines operadores para hacer tu código más legible.

### Valores Truthy y Falsy

En Python, ciertos valores se evalúan como `True` o `False` en contextos booleanos, incluso si no son explícitamente booleanos.

**📖 Documentación:** [Truth Value Testing](https://docs.python.org/3/library/stdtypes.html#truth-value-testing)

#### Valores Falsy (se evalúan como False)

Estos valores se consideran "falsos" en un `if`:

- `False` - El booleano False
- `None` - Representa ausencia de valor
- `0` - Cero entero
- `0.0` - Cero flotante
- `""` - String vacío
- (Otros: listas, diccionarios y tuplas vacías - que veremos más adelante)

```python
# False explícito
if False:
    print("No se imprime")

# None
valor = None
if valor:
    print("No se imprime")
else:
    print("valor es None")  # Esto se imprime

# Cero (entero o flotante)
numero = 0
if numero:
    print("No se imprime")
else:
    print("numero es cero")  # Esto se imprime

# String vacío
nombre = ""
if nombre:
    print("Hola")
else:
    print("No ingresaste un nombre")  # Esto se imprime
```

#### Valores Truthy (se evalúan como True)

**Todo lo demás** se considera "verdadero":

- `True` - El booleano True
- Cualquier número diferente de cero (positivo o negativo)
- Cualquier string no vacío
- Cualquier colección no vacía

```python
# True explícito
if True:
    print("Siempre se imprime")

# Números diferentes de cero
if 42:
    print("Número truthy")  # Se imprime

if -5:
    print("Negativos también son truthy")  # Se imprime

# Strings no vacíos
if "Hola":
    print("String truthy")  # Se imprime

if " ":  # Incluso un espacio
    print("Espacio es truthy")  # Se imprime
```

#### Ejemplos prácticos

```python
# Verificar si un string está vacío
nombre = input("Ingresa tu nombre: ")

if nombre:
    print(f"Hola, {nombre}")
else:
    print("No ingresaste un nombre")

# Verificar si hay saldo
saldo = 0

if saldo:
    print(f"Tu saldo es ${saldo}")
else:
    print("Tu saldo está vacío")

# Verificar input del usuario
respuesta = input("¿Continuar? (s/n): ")

if respuesta:  # Verificar que no esté vacío
    if respuesta == "s":
        print("Continuando...")
    else:
        print("Cancelado")
else:
    print("No ingresaste nada")
```

💡 **Consejo:** Aprovecha los valores truthy/falsy para escribir código más conciso:

```python
# ❌ Redundante
if nombre != "":
    print(f"Hola, {nombre}")

# ✅ Más pythónico
if nombre:
    print(f"Hola, {nombre}")

# ❌ Redundante
if numero != 0:
    print("Número válido")

# ✅ Más pythónico
if numero:
    print("Número válido")
```

---

## 5. Ejercicios Prácticos {#ejercicios}

### Ejercicio 1: Calculadora de IMC (Índice de Masa Corporal) ⭐

**Objetivo:** Practicar operaciones matemáticas básicas y formateo.

Crea un programa que:
1. Pida el peso en kilogramos
2. Pida la altura en metros
3. Calcule el IMC usando la fórmula: `IMC = peso / (altura ** 2)`
4. Muestre el resultado con 2 decimales

```python
# Ejemplo esperado:
# Entrada: peso = 70, altura = 1.75
# Salida: Tu IMC es: 22.86
```

**Pistas:**
- Usa `float(input())` para convertir a número decimal
- Usa `round()` o f-strings con `:.2f` para 2 decimales
- Recuerda usar `**` para elevar al cuadrado

---

### Ejercicio 2: Calculadora de Propinas con Divisiones ⭐⭐

**Objetivo:** Practicar división, división entera y módulo.

Crea un programa que:
1. Pida el monto total de la cuenta
2. Pida cuántas personas van a dividir la cuenta
3. Calcule cuánto debe pagar cada persona (sin propina)
4. Calcule la propina del 15% del total
5. Calcule cuánto debe pagar cada persona CON propina incluida
6. Muestre todos los resultados con 2 decimales

```python
# Ejemplo esperado:
# Entrada: cuenta = 150, personas = 4
# Salida:
# Total de la cuenta: $150.00
# Propina (15%): $22.50
# Total con propina: $172.50
# Cada persona paga: $43.13
```

**Pistas:**
- Propina = cuenta * 0.15
- Total con propina = cuenta + propina
- Por persona = total_con_propina / personas

---

### Ejercicio 3: Verificador de Año Bisiesto ⭐⭐

**Objetivo:** Practicar condicionales y operadores lógicos complejos.

Un año es bisiesto si:
- Es divisible entre 4 Y
- NO es divisible entre 100, A MENOS QUE también sea divisible entre 400

Crea un programa que:
1. Pida un año
2. Determine si es bisiesto o no
3. Muestre un mensaje apropiado

```python
# Ejemplos:
# año = 2024 → "2024 es un año bisiesto"
# año = 1900 → "1900 NO es un año bisiesto"
# año = 2000 → "2000 es un año bisiesto"
# año = 2023 → "2023 NO es un año bisiesto"
```

**Pistas:**
- Usa el operador `%` para verificar divisibilidad
- Un número es divisible entre X si `numero % X == 0`
- Combina condiciones con `and` y `or`
- Puedes necesitar paréntesis para agrupar condiciones

---

### Ejercicio 4: Sistema de Descuentos por Edad y Compra ⭐⭐

**Objetivo:** Practicar condicionales anidados y operadores lógicos.

Crea un programa que calcule el precio final de una compra con estos descuentos:
- Niños (< 12 años): 50% de descuento
- Adultos mayores (>= 65 años): 30% de descuento
- Si la compra es mayor a $100: 10% de descuento adicional (se suma al anterior)
- Si no aplica descuento por edad pero la compra es > $200: 15% de descuento

El programa debe:
1. Pedir la edad
2. Pedir el monto de la compra
3. Calcular el descuento correspondiente
4. Mostrar el descuento aplicado y el precio final

```python
# Ejemplo 1:
# edad = 10, compra = 150
# Salida:
# Descuento: 50% (niño) + 10% (compra mayor a $100) = 60%
# Precio original: $150.00
# Precio final: $60.00

# Ejemplo 2:
# edad = 30, compra = 250
# Salida:
# Descuento: 15% (compra mayor a $200)
# Precio original: $250.00
# Precio final: $212.50
```

**Pistas:**
- Primero verifica descuentos por edad
- Luego verifica descuentos por monto de compra
- Acumula los porcentajes de descuento
- Precio final = precio - (precio * descuento_total)

---

### Ejercicio 5: Validador de Contraseña Segura ⭐⭐⭐

**Objetivo:** Integrar múltiples conceptos: strings, condicionales, operadores lógicos.

Crea un programa que valide si una contraseña es segura. Una contraseña es segura si cumple TODAS estas condiciones:
- Tiene al menos 8 caracteres
- NO contiene espacios
- NO es una contraseña común ("password", "12345678", "qwerty")

El programa debe:
1. Pedir una contraseña
2. Verificar cada condición
3. Mostrar qué condiciones cumple y cuáles no
4. Indicar si la contraseña es segura o no

```python
# Ejemplo 1:
# contraseña = "MiClave2024"
# Salida:
# ✓ Tiene al menos 8 caracteres
# ✓ No tiene espacios
# ✓ No es una contraseña común
# Resultado: CONTRASEÑA SEGURA

# Ejemplo 2:
# contraseña = "hola"
# Salida:
# ✗ Debe tener al menos 8 caracteres
# ✓ No tiene espacios
# ✓ No es una contraseña común
# Resultado: CONTRASEÑA NO SEGURA

# Ejemplo 3:
# contraseña = "password"
# Salida:
# ✓ Tiene al menos 8 caracteres
# ✓ No tiene espacios
# ✗ Es una contraseña común
# Resultado: CONTRASEÑA NO SEGURA
```

**Pistas:**
- Usa `len()` para verificar longitud
- Usa `in` para verificar si contiene espacios: `" " in password`
- Compara contra las contraseñas comunes con `==` o `in`
- Usa variables booleanas para rastrear cada condición

---

## 6. Recursos Adicionales {#recursos}

### Documentación Oficial de Python
- [Tutorial Oficial - Control Flow](https://docs.python.org/3/tutorial/controlflow.html)
- [Built-in Functions](https://docs.python.org/3/library/functions.html)
- [Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
- [Comparisons](https://docs.python.org/3/library/stdtypes.html#comparisons)
- [Boolean Operations](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)

### Real Python (Artículos recomendados)
- [Python Operators and Expressions](https://realpython.com/python-operators-expressions/)
- [Conditional Statements in Python](https://realpython.com/python-conditional-statements/)
- [Python's math module](https://realpython.com/python-math-module/)

### Para Practicar
- [LeetCode - Easy Problems](https://leetcode.com/problemset/) - Filtra por "Easy" y "Math"
- [HackerRank - Python Basics](https://www.hackerrank.com/domains/python)
- [Exercism - Python Track](https://exercism.org/tracks/python)

---

## 7. Resumen de Conceptos Clave {#resumen}

### 📊 Números y Operadores

✅ **Tipos de números:**
- `int` - Números enteros sin decimales
- `float` - Números con decimales
- Conversión: `int()`, `float()`, `str()`

✅ **Operadores aritméticos:**
- `+` suma, `-` resta, `*` multiplicación
- `/` división (siempre devuelve float)
- `//` división entera (descarta decimales)
- `%` módulo (devuelve el resto)
- `**` potencia

✅ **Funciones matemáticas:**
- `abs()` - valor absoluto
- `round()` - redondeo
- `min()` / `max()` - mínimo/máximo

---

### 🔀 Condicionales

✅ **Indentación:**
- Python usa 4 espacios para definir bloques
- La indentación es obligatoria y debe ser consistente

✅ **Estructura if-elif-else:**
```python
if condicion1:
    # código
elif condicion2:
    # código
else:
    # código
```

✅ **Operadores de comparación:**
- `==` igual, `!=` diferente
- `<` menor, `<=` menor o igual
- `>` mayor, `>=` mayor o igual

✅ **Operadores lógicos:**
- `and` - Ambas condiciones deben ser True
- `or` - Al menos una condición debe ser True
- `not` - Invierte el valor de verdad

✅ **Valores Falsy:**
- `False`, `None`, `0`, `0.0`, `""`

✅ **Valores Truthy:**
- Todo lo demás (números ≠ 0, strings no vacíos, etc.)

---

### 💡 Consejos Finales

1. **Siempre convierte los datos de `input()`** al tipo correcto antes de operar
2. **Usa paréntesis** para hacer operaciones complejas más claras
3. **Ten cuidado con la indentación** - Python es estricto con esto
4. **Escribe condiciones específicas primero** en if-elif-else
5. **No confundas `=` (asignación) con `==` (comparación)**
6. **Usa nombres de variables descriptivos** para hacer tu código más legible
7. **Prueba casos extremos** (cero, negativos, strings vacíos)

---

**¡Éxito en tu aprendizaje de Python! 🐍✨**

*Recuerda: La práctica hace al maestro. Intenta resolver todos los ejercicios y experimenta con variaciones.*
