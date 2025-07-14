# Reto-8


1. De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.

Reto 5:Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.
```python
def calcular_carne_aves(n_gallinas: int, m_gallos: int, k_pollitos: int) -> int:
    """
    Calcula la cantidad total de carne de aves en kilogramos.
    
    Parámetros:
    - n_gallinas: número de gallinas
    - m_gallos: número de gallos
    - k_pollitos: número de pollitos
    
    Retorna:
    - Cantidad total de carne en kg
    """
    peso_total = (n_gallinas * 6) + (m_gallos * 7) + (k_pollitos * 1)
    return peso_total


if __name__ == "__main__":
    n = int(input("Ingrese la cantidad de gallinas: "))
    m = int(input("Ingrese la cantidad de gallos: "))
    k = int(input("Ingrese la cantidad de pollitos: "))

    total_kg = calcular_carne_aves(n, m, k)
    print("La cantidad total de carne es: " + str(total_kg) + " kg")
```
Con Lambda
```python
# Función lambda que calcula el total de carne de aves en kilogramos
calcular_carne_aves = lambda cantidad_gallinas, cantidad_gallos, cantidad_pollitos: \
    (cantidad_gallinas * 6) + (cantidad_gallos * 7) + (cantidad_pollitos * 1)

# Entrada de datos desde el usuario
cantidad_gallinas = int(input("Ingrese la cantidad de gallinas: "))
cantidad_gallos = int(input("Ingrese la cantidad de gallos: "))
cantidad_pollitos = int(input("Ingrese la cantidad de pollitos: "))

# Cálculo del peso total
peso_total_en_kilos = calcular_carne_aves(cantidad_gallinas, cantidad_gallos, cantidad_pollitos)

# Mostrar el resultado
print("La cantidad total de carne es:", peso_total_en_kilos, "kg")
```
Reto 5: Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
```python
def calcular_valor_prestamo(C: float, i: float, n: int) -> float:
    """
    Calcula el valor futuro de un préstamo con interés compuesto.

    Parámetros:
    - C: capital inicial
    - i: tasa de interés mensual (por ejemplo, 0.05 para 5%)
    - n: número de meses

    Retorna:
    - Valor final del préstamo
    """
    return C * (1 + i) ** n

if __name__ == "__main__":
    C = float(input("Ingrese el monto del préstamo (capital inicial): "))
    i = float(input("Ingrese la tasa de interés mensual (por ejemplo, 0.05 para 5%): "))
    n = int(input("Ingrese el número de meses: "))

    valor_final = calcular_valor_prestamo(C, i, n)
print("El valor final del préstamo después de " + str(n) + " meses es: " + str(round(valor_final, 2)))
```
con Lambdas:
```python
# Función lambda para calcular el valor futuro de un préstamo con interés compuesto
calcular_valor_prestamo = lambda capital_inicial, tasa_interes_mensual, cantidad_meses: \
    capital_inicial * (1 + tasa_interes_mensual) ** cantidad_meses

# Solicitar datos al usuario
capital_inicial = float(input("Ingrese el monto del préstamo (capital inicial): "))
tasa_interes_mensual = float(input("Ingrese la tasa de interés mensual (por ejemplo, 0.05 para 5%): "))
cantidad_meses = int(input("Ingrese el número de meses: "))

# Calcular el valor final del préstamo
valor_total_prestamo = calcular_valor_prestamo(capital_inicial, tasa_interes_mensual, cantidad_meses)

# Mostrar el resultado redondeado a 2 decimales
print("El valor final del préstamo después de " + str(cantidad_meses) + " meses es: " + str(round(valor_total_prestamo, 2)))
```
Reto 4:
Dado un número real x, construya un programa que permita determinar si el número es positivo, negativo o cero. Para cada caso de debe imprimir el texto que se especifica a continuación:

```python
# Paso 1: Leer un número real desde el teclado
x = float(input("Ingresa un número real: "))

# Paso 2: Determinar si el número es positivo, negativo o cero
if x > 0:
    print("El número es positivo.")
elif x < 0:
    print("El número es negativo.")
else:
    print("El número es cero.")
```
Con Lambdas
```python
# Función lambda para clasificar un número real
clasificar_numero = lambda numero: (
    "El número es positivo." if numero > 0 else
    "El número es negativo." if numero < 0 else
    "El número es cero."
)

# Entrada del usuario
numero_real = float(input("Ingresa un número real: "))

# Clasificación e impresión del resultado
print(clasificar_numero(numero_real))
```
2. De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args).


Reto 5:Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.
Version con (*ARGS)
```python
def calcular_carne(*args):
    # Desempaquetamos los argumentos: gallinas, gallos y pollitos
    cantidad_gallinas, cantidad_gallos, cantidad_pollitos = args
    # Calculamos el total de carne en kilogramos
    total_kilos = (cantidad_gallinas * 6) + (cantidad_gallos * 7) + (cantidad_pollitos * 1)
    return total_kilos

# Entrada de datos del usuario
cantidad_gallinas = int(input("Ingrese el número de gallinas: "))
cantidad_gallos = int(input("Ingrese el número de gallos: "))
cantidad_pollitos = int(input("Ingrese el número de pollitos: "))

# Llamada a la función usando los valores ingresados
carne_total = calcular_carne(cantidad_gallinas, cantidad_gallos, cantidad_pollitos)

# Mostrar el resultado
print("La cantidad total de carne es: " + str(carne_total) + " kilos")
```
Reto 5: Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
```python
def calcular_valor_prestamo(*args):
    # Desempaquetamos los argumentos: capital, tasa de interés y número de meses
    capital_inicial, tasa_interes_mensual, cantidad_meses = args
    # Fórmula de interés compuesto
    valor_final = capital_inicial * (1 + tasa_interes_mensual) ** cantidad_meses
    return valor_final

# Entrada de datos del usuario
capital = float(input("Ingrese el monto del préstamo (capital inicial): "))
tasa = float(input("Ingrese la tasa de interés mensual (por ejemplo, 0.05 para 5%): "))
meses = int(input("Ingrese el número de meses: "))

# Llamada a la función usando los valores ingresados
monto_final = calcular_valor_prestamo(capital, tasa, meses)

# Mostrar el resultado redondeado a 2 decimales
print("El valor final del préstamo después de " + str(meses) + " meses es: " + str(round(monto_final, 2)))
```
Reto 4:
Dado un número real x, construya un programa que permita determinar si el número es positivo, negativo o cero. Para cada caso de debe imprimir el texto que se especifica a continuación:
```python
def clasificar_numero(*args):
    # Desempaquetamos el único argumento recibido
    numero_real = args[0]
    
    # Clasificamos el número según su valor
    if numero_real > 0:
        return "El número es positivo."
    elif numero_real < 0:
        return "El número es negativo."
    else:
        return "El número es cero."

# Entrada del usuario
numero_ingresado = float(input("Ingresa un número real: "))

# Llamamos la función usando *args
resultado = clasificar_numero(numero_ingresado)

# Mostramos el resultado
print(resultado)
```

3. Escriba una función recursiva para calcular la operación de la potencia.
```python
# Definimos una función recursiva para calcular la potencia
def potencia(base, exponente):
    # Caso base: cualquier número elevado a 0 es 1
    if exponente == 0:
        return 1
    else:
        # Llamada recursiva: multiplicamos la base por la función con exponente reducido en 1
        return base * potencia(base, exponente - 1)
# Entrada de datos por teclado
# Pedimos al usuario que ingrese la base como número decimal
base = float(input("Ingrese la base: "))

# Pedimos al usuario que ingrese el exponente como número entero
exponente = int(input("Ingrese el exponente: "))
# Cálculo usando la función
# Llamamos a la función potencia con los valores ingresados
resultado = potencia(base, exponente)
# Imprimimos el resultado cccon el mensaje 
print("El resultado de " + str(base) + " elevado a la " + str(exponente) + " es " + str(resultado))
```

4. Utilice la siguiente plantilla de code para contar el tiempo:
```python
import time

start_time = time.time()
# instrucciones sobre las cuales se quiere medir tiempo de ejecución
end_time = time.time()

timer = end_time - start_time
print(timer)
```
Realice pruebas para calcular fibonacci con iteración o con recursión. Determine desde que número de la serie la diferencia de tiempo se vuelve significativa.
Con Iteracion:
```python
import time  # Importamos el módulo para medir tiempo

# Definimos la función recursiva
def fibonacci_recursivo(numero):
    # Caso base 1: si el número es 0, devolvemos 0
    if numero == 0:
        return 0
    # Caso base 2: si el número es 1, devolvemos 1
    elif numero == 1:
        return 1
    else:
        # Llamada recursiva: sumamos el resultado de los dos anteriores
        return fibonacci_recursivo(numero - 1) + fibonacci_recursivo(numero - 2)

# Ingresar número de la serie a calcular
numero_usuario = int(input("Ingrese un número para calcular Fibonacci (recursivo): "))

# Medir tiempo de ejecución
tiempo_inicial = time.time()  # Guardamos el tiempo antes de ejecutar
resultado = fibonacci_recursivo(numero_usuario)  # Ejecutamos la función
tiempo_final = time.time()  # Guardamos el tiempo después de ejecutar

# Calculamos cuánto tiempo tardó
duracion = tiempo_final - tiempo_inicial

# Mostrar resultados
print("El número Fibonacci en la posición", numero_usuario, "es", resultado)
print("Tiempo de ejecución (recursivo):", duracion, "segundos")
```
Con recursión:
```python
import time  # Importamos el módulo para medir tiempo

# Definimos la función iterativa
def fibonacci_iterativo(numero):
    valor_anterior = 0  # F(0)
    valor_actual = 1    # F(1)

    # Si el número es 0, devolvemos 0
    if numero == 0:
        return valor_anterior

    # Repetimos el cálculo hasta llegar al número deseado
    for contador in range(1, numero):
        suma = valor_anterior + valor_actual  # Sumamos los dos últimos valores
        valor_anterior = valor_actual         # Avanzamos los valores
        valor_actual = suma

    return valor_actual  # Este es el número de Fibonacci en esa posición

# Ingresar número de la serie a calcular
numero_usuario = int(input("Ingrese un número para calcular Fibonacci (iterativo): "))

# Medir tiempo de ejecución
tiempo_inicial = time.time()
resultado = fibonacci_iterativo(numero_usuario)
tiempo_final = time.time()

# Calculamos cuánto tiempo tardó
duracion = tiempo_final - tiempo_inicial

# Mostrar resultados
print("El número Fibonacci en la posición", numero_usuario, "es", resultado)
print("Tiempo de ejecución (iterativo):", duracion, "segundos")
```
5. Crear cuenta en [stackoverflow](https://stackoverflow.com/) y adjuntar imagen en el repo
<img width="1154" height="571" alt="{59F7EE2F-1B02-43E6-AE40-EC78B07C4006}" src="https://github.com/user-attachments/assets/f5c32392-05ef-4139-97fc-5d2b61a12912" />

6. Cosas de adultos....ir a [linkedin](https://www.linkedin.com/) y crear perfil....NO IMPORTA que estén iniciando, si tienen tiempo para redes poco útiles como fb, insta, o tiktok tienen tiempo para crear un perfil mamalón. Dejar enlace en el repo.
   https://www.linkedin.com/in/cristian-camilo-amezquita-rodriguez-284412374/
