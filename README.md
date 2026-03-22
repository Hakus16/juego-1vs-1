# juego-1vs-1
Introducción
En este proyecto se desarrolló un juego de combate básico en Python para aplicar conceptos
fundamentales de programación como variables, condicionales, ciclos y funciones.
Objetivo
Simular un combate por turnos donde el usuario pueda tomar decisiones (atacar, curarse o
usar una habilidad especial) y observar sus efectos en el desarrollo del juego.
Descripción del Juego
El héroe y el enemigo inician con 100 puntos de vida. El jugador dispone de 3 pociones que
recuperan 20 puntos de vida. En cada turno el jugador elige una acción y el enemigo
responde automáticamente.
Explicación del Código
1. Importación de librería
Se utiliza la librería random para generar valores aleatorios:
import random
2. Función generar_daño
Genera un número aleatorio entre un mínimo y un máximo:
def generar_daño(minimo, maximo):
 return random.randint(minimo, maximo)
3. Función mostrar_estado
Muestra la vida del héroe, pociones y enemigo:
def mostrar_estado(nombre_h, hp_h, pociones, nombre_e, hp_e):
 print("\n--- ESTADO ---")
 print(nombre_h, "HP:", hp_h)
 print("Pociones:", pociones)
 print(nombre_e, "HP:", hp_e)
4. Variables iniciales
Se definen los valores iniciales del juego:
nombre_heroe = "Héroe"
hp_heroe = 100
pociones = 3
nombre_enemigo = "Enemigo"
hp_enemigo = 100
5. Ciclo principal
Controla la ejecución del juego:
while hp_heroe > 0 and hp_enemigo > 0:
6. Opciones del jugador
El usuario elige una acción:
print("1. Atacar")
print("2. Curarse")
print("3. Especial")
opcion = input("Elige: ")
7. Condición de pociones
Si no hay pociones y se intenta curar, se pierde:
elif opcion == "2":
 if pociones > 0:
 hp_heroe += 20
 pociones -= 1
 else:
 perdiste = True
 break
8. Reinicio del juego
Permite volver a jugar:
while True:
 jugar()
 if input("¿Repetir? (s/n): ") != "s":
 break
