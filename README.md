# trabajo_final_issi
El ahorcado
import random

def jugar_ahorcado():

#una lista la cual tiene como fin buscar una palbra mediande una funcion que le permite elegir 
# una palabra al asar 
    palabras = ['python', 'programacion', 'inteligencia', 'computadora', 'algoritmo']
    palabra_secreta = random.choice (palabras).lower()
    letras_adivinadas = []
    intentos = 6

    print("¡Bienvenido al Ahorcado!")


    while intentos > 0:
        palabra_mostrada = ""
        faltan_letras = 0


        for letra in palabra_secreta:
            if letra in letras_adivinadas:
                palabra_mostrada += letra + " "
            else:
                palabra_mostrada += "_ "
                faltan_letras += 1

        print(f"\nPalabra: {palabra_mostrada}")
        print(f"Intentos restantes: {intentos}")
        print(f"Letras usadas: {', '.join(letras_adivinadas)}")

        
        if faltan_letras == 0:
            print("¡Felicidades! Ganaste.")
            break

        
        adivinanza = input("Introduce una letra: ").lower()

        
        if len(adivinanza) != 1 or not adivinanza.isalpha():
            print("Por favor, introduce solo una letra válida.")
            continue

        if adivinanza in letras_adivinadas:
            print(f"Ya habías intentado con la '{adivinanza}'. Prueba otra.")
            continue

        letras_adivinadas.append(adivinanza)


        if adivinanza in palabra_secreta:
            print(f"¡Bien! La letra '{adivinanza}' está en la palabra.")
        else:
            intentos -= 1
            print(f"Lo siento, la '{adivinanza}' no está.")

    if intentos == 0:
        print(f"\nte ahorcaste. La palabra era: {palabra_secreta}")


jugar_ahorcado()
