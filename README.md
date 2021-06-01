# Dado_gane_2.0
1k13_G28
#random dado
import random

#cantidad de jugadores
print("Juego de dos o tres")

#puntajes
Ptj1 = int(0)
Ptj2 = int(0)

#Valores de los dados
vd1 = 0
vd2 = 0
vd3 = 0

#pedir nombres de los jugadores:
print("Ingresar los nombres de los participantes")
nom1 = str(input("Nombre jugador 1:"))
nom2 = str(input("Nombre jugador 2:"))
print(("-" * 75))

#round 1
print("Round 1")
print("Turno del Jugador ", nom1, ":")

#arrojar los dados Jugador 1
print("Desea tirar los dados?")
td = str(input("Tirar dado(s/n):"))  # pedir tirar dado
if td == "s" or td == "S":
    # pedir rando de dado del 1 al 6
    vd1 = random.randrange(1, 7)  # dado 1
    vd2 = random.randrange(1, 7)  # dado 2
    vd3 = random.randrange(1, 7)  # dado 3
    print("Dados:", vd1, vd2, vd3)
else:
    exit("Fin del juego. Debe tirar los dados si o si.")

if vd1 == vd2 == vd3:  # puntaje 6
    Ptj1 = 6
    print("Suma 6 puntos")
elif vd1 != vd2 and vd1 != vd3 and vd2 != vd3:  # puntaje 0
    Ptj1 = 0
    print("Suma 0 puntos")
else:  # disputa de puntaje entre tres y seis
    print()
    print("Obtuvo 2 dados iguales, puede tirar el diferente nuevamente")
    tdn = (input("Tirar de nuevo(s/n):"))
    if tdn == "s" or tdn =="S":
        if vd1 == vd2:
            vd3 = random.randrange(1, 7)
            print("Dado 3:", vd3)
        elif vd1 == vd3:
            vd2 = random.randrange(1, 7)
            print("Dado 2:", vd2)
        elif vd2 == vd3:
            vd1 = random.randrange(1, 7)
            print("Dado 1:", vd1)

        if vd1 == vd2 == vd3:
            Ptj1 = 6
            print("¡¡SUERTE!!")
            print("Suma 6 puntos")
        else:
            Ptj1 = 3
            print("¡¡MALA SUERTE!!")
            print("Suma 3 puntos")
    else:
        print("Ok. Su puntaje es 3..")

print(("-" * 75))
print("Round 1")
print("Turno del Jugador ", nom2, ":")

# arrojar los dados Jugador 2
print("Desea tirar los dados?")
td = str(input("Tirar dados(s/n):"))  # pedir tirar dado
if td == "s" or td == "S":
    # pedir rando de dado del 1 al 6
    vd1 = random.randrange(1, 7)  # dado 1
    vd2 = random.randrange(1, 7)  # dado 2
    vd3 = random.randrange(1, 7)  # dado 3
    print("Dados:", vd1, vd2, vd3)
else:
    exit("Fin del juego. Debe tirar los dados si o si.")

if vd1 == vd2 == vd3:  # puntaje 6
    Ptj2 = 6
    print("Suma 6 puntos")
elif vd1 != vd2 and vd1 != vd3 and vd2 != vd3:  # puntaje 0
    Ptj2 = 0
    print("Suma 0 puntos")
else:  # disputa de puntaje entre tres y seis
    print()
    print("Obtuvo 2 dados iguales, puede tirar el diferente nuevamente")
    tdn = (input("Tirar de nuevo(s/n):"))
    if tdn == "s" or tdn =="S":
        if vd1 == vd2:
            vd3 = random.randrange(1, 7)
            print("Dado 3:", vd3)
        elif vd1 == vd3:
            vd2 = random.randrange(1, 7)
            print("Dado 2:", vd2)
        elif vd2 == vd3:
            vd1 = random.randrange(1, 7)
            print("Dado 1:", vd1)

        if vd1 == vd2 == vd3:
            Ptj2 = 6
            print("¡¡SUERTE!!")
            print("Suma 6 puntos")
        else:
            Ptj2 = 3
            print("¡¡MALA SUERTE!!")
            print("Suma 3 puntos")
    else:
        print("Ok. Suma 3 puntos..")

#puntaje al finalizar la ronda 1
print("-" * 75)
print("Desea ver el puntaje de la Ronda 1")
td = str(input("Si/No(s/n):"))  # pedir mostrar puntaje
if td == "s" or td == "S":
    print()
    print("Puntajes de la primera Ronda")
    print("Jugador ", nom1, Ptj1, "puntos")
    print("Jugador ", nom2, Ptj2, "puntos")

#round 2
print(("-" * 75))
print("Round 2")
print("Jugador ", nom1, ":")

# random dado, solicitar elegir paridad al jugador 1
print("Desea apostar al par o al impar?(par = 1, impar = 2)")
poi1 = int(input("Par/Impar(1/2):"))
print("Desea tirar los dados")
td = str(input("Tirar dado(s/n):"))  # pedir tirar dado

if td == "s" or td == "S":
    # pedir rando de dado del 1 al 6
    vd1 = random.randrange(1, 7)  # dado 1
    vd2 = random.randrange(1, 7)  # dado 2
    vd3 = random.randrange(1, 7)  # dado 3
    print("Dados:", vd1, vd2, vd3)
else:
    exit("Fin del juego. Debe tirar los dados si o si.")

sd1 = (vd3 + vd2 + vd1) % 2

if sd1 == 0:
    pois1 = 1
else:
    pois1 = 2

# mayor
if vd1 >= vd2 and vd1 >= vd3:
    may = vd1
elif vd2 >= vd1 and vd2 >= vd3:
    may = vd2
else:
    may = vd3

# menor
if vd1 <= vd2 and vd1 <= vd3:
    men = vd1
elif vd2 <= vd1 and vd2 <= vd3:
    men = vd2
else:
    men = vd3

# desarrollo de puntajes
# verificamos si la paridad elegida coincide con la paridad de la sumatoria
if poi1 == pois1:
    Ptj1 = Ptj1 + may
    print("La suma es de la paridad elegida =)")
    print("Sumaste ", may, "puntos")

    # si cada dado es de la paridad elegida duplica puntaje
    if (vd1 % 2) == 1 and (vd2 % 2) == 1 and (vd3 % 2) == 1:
        Ptj1 = Ptj1 * 2
        print("¡¡BRAVO!! Todos los dados son IMPARES duplicaste tu puntaje")
    if (vd1 % 2) == 0 and (vd2 % 2) == 0 and (vd3 % 2) == 0:
        Ptj1 = Ptj1 * 2
        print("¡¡BRAVO!! Todos los dados son PARES duplicaste tu puntaje")

else:
    Ptj1 = Ptj1 - men
    print("La suma no es de la paridad elegida =(")
    print("Restaste ", men, "puntos")

print(("-" * 75))
print("Round 2")
print("Jugador ", nom2, ":")

# random dado, solicitar elegir paridad al jugador 2
print("Desea apostar al par o al impar?(par = 1, impar = 2)")
poi2 = int(input("Par/Impar(1/2):"))
print("Desea tirar los dados")
td = str(input("Tirar dados(s/n):"))  # pedir tirar dado

if td == "s" or td =="S":
    # pedir rando de dado del 1 al 6
    vd1 = random.randrange(1, 7)  # dado 1
    vd2 = random.randrange(1, 7)  # dado 2
    vd3 = random.randrange(1, 7)  # dado 3
    print("Dados:", vd1, vd2, vd3)
else:
    exit("Fin del juego. Debe tirar los dados si o si.")

sd2 = (vd3 + vd2 + vd1) % 2

if sd2 == 0:
    pois2 = 1
else:
    pois2 = 2

# mayor
if vd1 >= vd2 and vd1 >= vd3:
    may = vd1
elif vd2 >= vd1 and vd2 >= vd3:
    may = vd2
else:
    may = vd3

# menor
if vd1 <= vd2 and vd1 <= vd3:
    men = vd1
elif vd2 <= vd1 and vd2 <= vd3:
    men = vd2
else:
    men = vd3

# desarrollo de puntajes
# verificamos si la paridad elegida coincide con la paridad de la sumatoria
if poi2 == pois2:
    Ptj2 = Ptj2 + may
    print("La suma es de la paridad elegida =)")
    print("Sumaste ", may, "puntos")

     # si cada dado es de la paridad elegida duplica puntaje
    if (vd1 % 2) == 1 and (vd2 % 2) == 1 and (vd3 % 2) == 1:
        Ptj2 = Ptj2 * 2
        print("¡¡BRAVO!! Todos los dados son IMPARES duplicaste tu puntaje")
    if (vd1 % 2) == 0 and (vd2 % 2) == 0 and (vd3 % 2) == 0:
        Ptj2 = Ptj2 * 2
        print("¡¡BRAVO!! Todos los dados son PARES duplicaste tu puntaje")

else:
    Ptj2 = Ptj2 - men
    print("La suma no es de la paridad elegida =(")
    print("Restaste ", men, "puntos")

#tabla de puntajes
print(("-" * 75))
print("Tabla de puntajes:")
print(nom1, ":", Ptj1)
print(nom2, ":", Ptj2)

# elegir ganador
print(("-" * 75))

if Ptj1 > Ptj2:
    print("El juego termino, el ganador es:")
    print(nom1, "Win!")
elif Ptj2 == Ptj1:
    print("El juego termino, el resultado fue:")
    print("Empate!")
else:
    print("El juego termino, el ganador es:")
    print(nom2, "Win!")
