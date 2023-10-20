# REPO8.
#  1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
```
for numero in range(1, 101):
    cuadrado = numero * numero
    print(f"Número: {numero}, Cuadrado: {cuadrado}")
```
# 2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000:
```
print("Números impares:")
for i in range(1, 1000, 2):
    print(i)
print("Números pares:")
for j in range (2, 1001, 2):
    print(j)
```

#  3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado:
```
n  = int(input("Ingrese un número natural mayor o igual a 2: "))
print("Los números pares en forma descendente desde " +str(n)+ " hasta 2 son:")
if n % 2 != 0:
    n = n - 1
else:
    n = n
for i in range(n, 1, -2):
    print(str(i))
```
#  4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial:

```
numero = int(input("Ingrese un numero natural: "))
inicio : int = 1
fact : int = 1
for inicio in range(1, numero + 1,1):
  for i in range(1, inicio +1):
    fact = fact*i
  print("Fatorial de " +str(inicio)+ " es " +str(fact))
  fact = 1
```

#  5. Calcular el valor de 2 elevado a la potencia n usando ciclos for:
```
num_c : int = 2
potencia = int(input("Ingresa el número que desees: "))
numero : int = 2
for i in range(1, potencia, 1):
  num_c = num_c *numero
print("2 elevado a la potencia " +str(potencia)+ " es igual a " +str(num_c))
```

# 6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. Disclaimer: Trate de no utilizar el operador de potencia (**):

```
numero_b = float(input("Ingresa un número real: "))
numero_a = int(input("Ingresa un número natural: "))
b = numero_b
for i in range(1,numero_a):
  numero_b = numero_b * b
print("El numero " +str(b)+" elevado a la potencia " +str(numero_a)+ " es : " +str(numero_b))
```

# 7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9:
```
mult=1
for i in range(1, 10):
  print("------------------------------------------------")
  print("Tabla de multiplicar del " + str(i))
  for j in range (1, 11):
    mult=i*j
    print(str(i) + " x " + str(j) + " = " + str(mult))

```

#  8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación:

```

import math
from math import exp, factorial
def AproxFuncionExponencial(x: float, n:int) -> float:
  suma: float = 0
  for i in range(0, n+1):
    y = ((x**i)/factorial(i))
    suma += y
  return suma
if __name__ == "__main__":
  x = float(input("Ingrese un número real: "))
  n: int = 1
  rta1: float = AproxFuncionExponencial(x, n)
  aprox: float = AproxFuncionExponencial(x, n)
  valorReal: float = exp(x)
  while ((abs(valorReal - aprox)/valorReal * 100)>0.1):
    aprox: float = AproxFuncionExponencial(x, n)
    n += 1
  print("El valor de n para tener un error menor a 0.1: " + str(n))
  print("La aproximación es: " + str(aprox))
  print("El valor real es: " + str(valorReal))

```
#  9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función seno y mostrar la diferencia entre el valor real y la aproximación:
```
import math
def seno(x, n):
    aproximacion = 0
    for i in range(n):
        aproximacion += ((-1) ** i) * (x ** (2 * i + 1)) / math.factorial(2 * i + 1)
    return aproximacion
x = float(input("Ingrese el valor de x: "))
n = int(input("Ingrese el número de términos de la serie de maclaurin a utilizar: "))
aproximacion = seno(x, n)
valor_real = math.sin(x)
diferencia = valor_real - aproximacion
print("La aproximación de la función seno para x = " +str(x)+ " utilizando los primeros " +str(n)+ " términos de la serie de maclaurin: " +str(aproximacion))
print("El valor real de la función seno para x = " +str(x)+ " es: " +str(valor_real))
print("La diferencia entre la aproximación y el valor real es: " +str(diferencia))
```

#  10. Diseñar una función que permita calcular una aproximación de la función arcotangente alrededor de 0 para cualquier valor x en el rango [-1, 1], utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función arctan y mostrar la diferencia entre el valor real y la aproximación:
```
import math
#función para calcular la aproximación de la función arcotangente
def aproxarctan(x, n):
    if abs(x) >= 1:
        raise ValueError("El valor de x debe estar en el rango [-1, 1].")
    aproximacion = 0
    for i in range(n):
        termino = ((-1) ** i) * (x ** (2 * i + 1)) / (2 * i + 1)
        aproximacion += termino
    valor_real = math.atan(x)
    diferencia = abs(valor_real - aproximacion)
    return aproximacion, diferencia
#pedir que ingrese el valor de x en el rango [-1, 1] y el número de términos n.
x = float(input("Ingresa el valor de x en el rango [-1, 1]: "))
n = int(input("Ingresa el número de términos n: "))
#si x esté dentro del rango permitido [-1, 1].
if abs(x) > 1:
    print("El valor de x está fuera del rango permitido.")
else:
    #calcular la aproximación, la diferencia con el valor real e imprimir los resultados.
    aproximacion, diferencia = aproxarctan(x, n)
    print(f"Aproximación de arctan({x}) con {n} términos: {aproximacion}")
    print(f"Valor real de arctan({x}): {math.atan(x)}")
    print(f"Diferencia con el valor real: {diferencia:.4f}")
```

