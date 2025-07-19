# reto-10
1.Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
  
    def leer_matriz(filas, columnas, nombre):
        print(f"\nIngrese los elementos de la {nombre}:")
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = float(input(f"{nombre}[{i}][{j}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz
    
    def mostrar_matriz(matriz):
        for fila in matriz:
            print(fila)
    
    def operar_matrices(m1, m2, operacion):
        resultado = []
        for i in range(len(m1)):
            fila_resultado = []
            for j in range(len(m1[0])):
                if operacion == 'suma':
                    fila_resultado.append(m1[i][j] + m2[i][j])
                elif operacion == 'resta':
                    fila_resultado.append(m1[i][j] - m2[i][j])
            resultado.append(fila_resultado)
        return resultado
    print("Operación con matrices (suma o resta)")
    filas = int(input("Número de filas: "))
    columnas = int(input("Número de columnas: "))

    matriz1 = leer_matriz(filas, columnas, "Matriz 1")
    matriz2 = leer_matriz(filas, columnas, "Matriz 2")

    op = input("¿Desea realizar una suma o una resta? (escriba 'suma' o 'resta'): ").lower()

    if op in ['suma', 'resta']:
        resultado = operar_matrices(matriz1, matriz2, op)
        print("\nResultado de la operación:")
        mostrar_matriz(resultado)
    else:
        print("Operación no válida. Solo se acepta 'suma' o 'resta'.")

# 2 . Desarrolle un programa que permita realizar el producto de matrices.

    def leer_matriz(filas, columnas, nombre):
        print(f"\nIngrese los elementos de la {nombre}:")
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = float(input(f"{nombre}[{i}][{j}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz
    
    def mostrar_matriz(matriz):
        for fila in matriz:
            print(fila)
    
    def multiplicar_matrices(m1, m2):
        filas_a = len(m1)
        columnas_a = len(m1[0])
        columnas_b = len(m2[0])
    
        resultado = []
        for i in range(filas_a):
            fila_resultado = []
            for j in range(columnas_b):
                suma = 0
                for k in range(columnas_a):
                    suma += m1[i][k] * m2[k][j]
                fila_resultado.append(suma)
            resultado.append(fila_resultado)
        return resultado
    
    
    print("Multiplicación de matrices")
    
    filas_a = int(input("Filas de la matriz A: "))
    columnas_a = int(input("Columnas de la matriz A (debe coincidir con filas de la matriz B): "))
    
    filas_b = int(input("Filas de la matriz B: "))
    columnas_b = int(input("Columnas de la matriz B: "))
    
    if columnas_a != filas_b:
        print(" No se pueden multiplicar: las columnas de A deben coincidir con las filas de B.")
    else:
        matriz_a = leer_matriz(filas_a, columnas_a, "Matriz A")
        matriz_b = leer_matriz(filas_b, columnas_b, "Matriz B")
    
        resultado = multiplicar_matrices(matriz_a, matriz_b)
    
        print("\nResultado de la multiplicación:")
        mostrar_matriz(resultado)

# 3. Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada.

    def leer_matriz(filas, columnas):
        print("\nIngrese los elementos de la matriz:")
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = float(input(f"Elemento [{i}][{j}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz
    
    def mostrar_matriz(matriz):
        for fila in matriz:
            print(fila)
    
    def transponer_matriz(matriz):
        filas = len(matriz)
        columnas = len(matriz[0])
        transpuesta = []
        for j in range(columnas):
            nueva_fila = []
            for i in range(filas):
                nueva_fila.append(matriz[i][j])
            transpuesta.append(nueva_fila)
        return transpuesta
    
    print(" MATRIZ TRANSPUESTA")
    
    filas = int(input("Ingrese el número de filas: "))
    columnas = int(input("Ingrese el número de columnas: "))
    
    matriz_original = leer_matriz(filas, columnas)
    
    print("\nMatriz Original:")
    mostrar_matriz(matriz_original)
    
    matriz_transpuesta = transponer_matriz(matriz_original)
    
    print("\n Matriz Transpuesta:")
    mostrar_matriz(matriz_transpuesta)

# 4. Desarrollar un programa que sume los elementos de una columna dada de una matriz

       def leer_matriz(filas, columnas):
        print("\nIngrese los elementos de la matriz:")
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = float(input(f"Elemento [{i}][{j}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz
    
        def mostrar_matriz(matriz):
            for fila in matriz:
                print(fila)
          
        def sumar_columna(matriz, col):
            suma = 0
            for fila in matriz:
                suma += fila[col]
            return suma
        

        print(" SUMAR ELEMENTOS DE UNA COLUMNA")
        
        filas = int(input("Número de filas: "))
        columnas = int(input("Número de columnas: "))
          
        matriz = leer_matriz(filas, columnas)
        
        print("\n Matriz ingresada:")
        mostrar_matriz(matriz)
        
        columna = int(input(f"\n¿Qué columna deseas sumar? (0 a {columnas-1}): "))
        
        if columna < 0 or columna >= columnas:
            print(" Columna inválida.")
        else:
            resultado = sumar_columna(matriz, columna)
            print(f"\n La suma de los elementos en la columna {columna} es: {resultado}")

# 5. Desarrollar un programa que sume los elementos de una fila dada de una matriz.
  
      def leer_matriz(filas, columnas):
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = float(input(f"Ingrese el valor en la posición [{i}][{j}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz
    
    def mostrar_matriz(matriz):
        for fila in matriz:
            print(fila)
    
    def sumar_fila(matriz, fila_index):
        if not matriz or fila_index < 0 or fila_index >= len(matriz):
            print("Error: Índice de fila fuera de rango.")
            return None

        suma = sum(matriz[fila_index])
        return suma

    if __name__ == "__main__":
        print("Suma de los elementos de una fila de una matriz")

        filas = int(input("Ingrese el número de filas: "))
      columnas = int(input("Ingrese el número de columnas: "))
  
        print("\nIngrese los valores de la matriz:")
        matriz = leer_matriz(filas, columnas)

        print("\nMatriz ingresada:")
        mostrar_matriz(matriz)
    
        fila_index = int(input(f"\nIngrese el índice de la fila a sumar (0 a {filas - 1}): "))
        resultado = sumar_fila(matriz, fila_index)
    
        if resultado is not None:
            print(f"La suma de los elementos de la fila {fila_index} es: {resultado}")
    
