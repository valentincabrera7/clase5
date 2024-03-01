# Ejercicio n1

numero = int(input("Ingrese un numero: "))

numero = 0
while numero <= 5:
    numero += 1 # se agrega a la variable numero = 0, y llega hasta el 6 porque ya es mayor a 5
    print("Numero es igual a", numero)

# Ejercicio n2

intento = 1
while intento <= 3:
    respuesta = input("Escribe si: ")
    if respuesta == "si":
        print("Saliste del programa en el intento", intento)
        exit()
    intento += 1 # va aca porque si lo pongo abajo del while, me suma otro intento más
                 # debajo del if se asegura que solo se incremente cuando la condicion no se haya cumplido   
else:
    print("Has agotado todos los intentos")


# Ejercicio n3

# calcular la suma de una cantidad de numeros ingresada por el usuario
# para finalizar la ejecucion del programa el usuario debe escribir la palabra exit
# el programa debe validar dicha accion
# finalmente el algoritmo debe mostrar la suma parcial y total obtenida 

suma = 0 
#continuar = True

while True: #while continuar. El bucle continuará ejecutándose indefinidamente hasta que se encuentre una instrucción de interrupción (en este caso, el break).
    entrada = input("Ingrese un numero a contar (exit para salir): ") #aca no va int pq sino convierte el exit y da error
    if entrada == "exit":
        break  #continuar = False           #cambiamos el True por el False si el usuario ingresa exit
    else:                                   #de lo contrario, si no ingresa exit, cambiamos entrada y le agregamos el int
        entrada = int(entrada) # cambia str de la variable a enteros
        suma += entrada # con esta variable empieza a sumar los numeros ingresados
        print(f"Suma parcial: {suma}")
#else:  para que no tire error el codigo ya que el break corta, sacamos el else y el print va en la linea del while
print(f"Suma total: {suma}") #la suma final la hace cuando salga del bucle, por eso va en la misma linea del while (para que tire la suma total)

#se cambia de while continuar(continuar = True) a falso porque while False es inejecutable

# EL CODIGO DE ARRIBA EXPLICADO, QUEDARIA:

suma = 0
while True:
    entrada = input("Ingrese un numero a contar (exit para salir): ")
    if entrada == "exit":
        break # aca nunca me va a tirar la suma total
    else:
        entrada = int(entrada)
        suma += entrada
        print(f"La suma parcial: {suma}")
print(f"La suma total: {suma}") # aca me ejecuta el break porque el print lo alinee al while True
# si el print va en el else, tira la suma parcial y total, por eso va al while, para que tire la suma total solo al ingresar el exit

# Ejercicio n4

indice = 0 # se le agrega 0 porque en la linea 4 con += 1 le vas agregando numeros
lista = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for indice in lista: # el guin bajo es para rellenar el lugar y no confundir con un nombre, ya que no se va a usar
    lista[indice] *= 5
    indice += 1 
print(lista)


# Ejercicio n5 

# enumarate() returna tuplas que contienen 2 elementos: un indice y el valor del objeto iterable 

paises = ["Argentina", "Brasil", "Chile", "Uruguay"] # esto es una lista, pero retorna tupla()
for indice, pais in enumerate(paises, start=1): # si no pongo start=1 empieza a contar desde el 0
    print(indice, pais) # al poner indice, me devuelve la lista sin "", ni ()


# Ejercicio n6

for numero in range(10):
    print(numero) 
# con range cuenta hasta el numero ingresado, excluyendolo, en este caso hasta el 9


# Ejercicio n7

for numero in range(10):
    if numero == 2:
        continue # saltea el 2 porque continua con otro elemento
    elif numero == 8:
        break # cuando llega a 8 sale del bucle 
    else:
        print(f"Se termino de iterar {numero=}")


# Ejercicio n8

estribillo = ("¿Qué voy a hacer?, je ne sais pas\n"
    "¿Qué voy a hacer?, je ne sais plus\n"
    "¿Qué voy a hacer?, je suis perdu\n"
    "¿Qué horas son, mi corazón?\n,") # va con coma porque sino no lo recorre, es decir que muestra todo completo) # el estribillo tiene un solo elemento, que es una tupla

verso_1 = ( "los aviones", "viajar", "la mañana",
    "el viento", "soñar", "la mar") # la tupla tiene varios elementos
    
verso_2 = ("la moto", "correr", "la lluvia", "volver",
    "marihuana", "colombiana", "la montaña", "la noche") # la tupla tiene varios elementos

verso_3 = ("la cena", "la vecina", "su cocina", "camelar",
    "la guitarra", "el reggae") # la tupla tiene varios elementos


verso_4 = ("la canela", "el fuego", "menear",
    "la coruña", "la castaña", "guatemala")


secuencia = (verso_1, estribillo, verso_2, estribillo,
             verso_3, estribillo, verso_4, estribillo) # el estribillo es tupla asi queda igual en la secuencia


letra = ""
for verso in secuencia:
    if len(verso) > 1: # la longitud es mayor a 1 (hablando de todos los versos)
        for frase in verso: # el if quiere decir que si tiene mas de 1 elemento estoy trabajando con los versos
            letra += f"Me gusta {frase}, me gustas tu\n" # a letra que esta vacia le voy agregando me gusta-frase-me gusta
            # todo el if hasta letra no entra al else, entonces se vuelve a secuencia y pasa al estribillo
    else: # de lo contrario, estoy trabajando con el estribillo, que tiene 1 solo elemento
        letra += estribillo[0] # este 0 es para que recurre el unico elemento en la tupla y no la tupla entera
        letra += "\n" # despues del estribillo, un salto de linea sino queda pegado
print(letra)
