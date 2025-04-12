# ab23007uno

Una librería de Python para resolver problemas matemáticos y numéricos, especializada en métodos iterativos y directos para la resolución de sistemas de ecuaciones lineales y búsqueda de raíces.

## Instalación

```bash
pip install ab23007uno
```

## Características

La librería implementa los siguientes métodos numéricos:

### Sistemas de Ecuaciones Lineales

- **Eliminación Gaussiana**: Método directo para resolver sistemas de ecuaciones lineales.
- **Eliminación Gauss-Jordan**: Versión extendida del método de eliminación gaussiana.
- **Factorización LU**: Descomposición de una matriz en el producto de matrices triangulares.
- **Regla de Cramer**: Resolución mediante determinantes.
- **Método de Jacobi**: Solución iterativa para sistemas de ecuaciones.
- **Método de Gauss-Seidel**: Método iterativo con convergencia mejorada respecto a Jacobi.

### Búsqueda de Raíces

- **Método de la Bisección**: Algoritmo simple para encontrar raíces de funciones continuas.

## Uso

A continuación se muestran ejemplos básicos de uso para cada método:

### Resolución de Sistemas Lineales

```python
import numpy as np
from ab23007uno import gauss_elimination, cramer, lu_decomposition

# Definir sistema: 2x + y - z = 8, -3x - y + 2z = -11, -2x + y + 2z = -3
A = np.array([
    [2, 1, -1],
    [-3, -1, 2],
    [-2, 1, 2]
])
b = np.array([8, -11, -3])

# Resolver usando eliminación gaussiana
x_gauss = gauss_elimination(A, b)
print("Solución por eliminación gaussiana:", x_gauss)

# Resolver usando Cramer
x_cramer = cramer(A, b)
print("Solución por regla de Cramer:", x_cramer)

# Resolver usando factorización LU
x_lu = resolver_LU(A, b)
print("Solución por factorización LU:", x_lu)
```

### Métodos Iterativos

```python
from ab23007uno import jacobi, gauss_seidel

# Usar los métodos iterativos con valores por defecto
x_jacobi, iterations_jacobi = jacobi(A, b)
print(f"Solución por método de Jacobi ({iterations_jacobi} iteraciones):", x_jacobi)

# Ejemplo con parámetros personalizados
x_seidel, iterations_seidel = gauss_seidel(A, b, tol=1e-8, verbose=True)
print(f"Solución por método de Gauss-Seidel ({iterations_seidel} iteraciones):", x_seidel)
```

### Búsqueda de Raíces

```python
import math
from ab23007uno import bisection

# Definir función f(x) = x^3 - x - 2
def f(x):
    return x**3 - x - 2

# Ejemplo con función que usa math
def g(x):
    return math.sin(x) - 0.5

# Resolver usando método de bisección con los valores por defecto
root1, iterations1 = bisection(f, 1, 2)
# También puedes personalizar los parámetros si es necesario
root2, iterations2 = bisection(g, 0, math.pi/2, tol=1e-8, verbose=True)

print(f"Raíz aproximada de f: {root1} (encontrada en {iterations1} iteraciones)")
print(f"Raíz aproximada de g: {root2} (encontrada en {iterations2} iteraciones)")
```

## Requisitos

- NumPy >= 1.19.0
- Python >= 3.6


