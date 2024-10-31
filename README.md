import random

# Pedir al usuario la cantidad de filas
n = int(input("Type the number of rows (positive integers): "))
while n <= 0:
    n = int(input("Type the number of rows (positive integers): "))

s = ''

# Generar la parte superior izquierda del árbol (lado izquierdo del triángulo)
for row in range(n - 1):
    # Añadir espacios iniciales para centrar la mitad del árbol
    for space in range(n - row - 1):
        s += ' '

    # Añadir los símbolos '@' o ' ' de forma aleatoria y al final el '*'
    for j in range(row):
        r = random.randint(0, row)
        if r == 0:
            s += '@'
        else:
            s += ' '
    s += '*'

    # Generar la parte superior derecha del árbol (reflejo de la izquierda)
    for j in range(row - 1, -1, -1):
        r = random.randint(0, row)
        if r == 0:
            s += '@'
        else:
            s += ' '

    s += '\n'

# Generar el tronco del árbol con el ancho completo
for i in range(n * 2 - 1):
    s += '*'
s += ' \n'

# Generar la base del árbol centrada usando 'X'
for rows in range(int(n / 3)):
    s += ' ' * (n - int(n / 5))
    for asterisks in range(int(n / 5) * 2 - 1):
        s += 'X'
    s += '\n'

# Mostrar el árbol completo
print("My full tree is: ")
print(s)
print(s)
