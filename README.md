import math

def afficher_menu(x):
    # Affiche le menu des opérations 
    print(f"\nChoisissez une opération :")
    print(f"1) {x} + y")
    print(f"2) {x} - y")
    print(f"3) {x} × y")
    print(f"4) {x} ÷ y")
    print(f"5) √{x}")
    print(f"6) {x} div y (division entière)")
    print(f"7) {x} mod y (modulo)")
    print(f"8) {x} ^ y (puissance)")
    print(f"9) inv({x}) (inverse)")
    print("10) Repartir à 0 (nouveau nombre)")
    print("11) Afficher l'historique")
    print("12) Quitter")

def obtenir_nombre(message):
    # Demande à l'utilisateur de saisir un nombre
    while True:
        nombre = input(message)
        if '.' in nombre:
            return float(nombre)
        else:
            return int(nombre)

def calculatrice():
    x = obtenir_nombre("Entrez un nombre : ")  # Demande le premier nombre
    historique = [x]  # Initialise l'historique avec le premier nombre

    while True:
        afficher_menu(x)  # Afficher le menu avec la valeur actuelle de x
        choix = input("Choix : ")

        if choix == '1':  # Addition
            y = obtenir_nombre("Valeur de y : ")
            x = x + y
        elif choix == '2':  # Soustraction
            y = obtenir_nombre("Valeur de y : ")
            x = x - y
        elif choix == '3':  # Multiplication
            y = obtenir_nombre("Valeur de y : ")
            x = x * y
        elif choix == '4':  # Division
            y = obtenir_nombre("Valeur de y : ")
            x = x / y
        elif choix == '5':  # Racine carrée
            x = math.sqrt(x)
        elif choix == '6':  # Division entière
            y = obtenir_nombre("Valeur de y : ")
            x = x // y
        elif choix == '7':  # Modulo 
            y = obtenir_nombre("Valeur de y : ")
            x = x % y
        elif choix == '8':  # Puissance
            y = obtenir_nombre("Valeur de y : ")
            x = x ** y
        elif choix == '9':  # Inverse
            x = 1 / x
        elif choix == '10':  # Réinitialisation de la calculatrice
            x = obtenir_nombre("Entrez un nouveau nombre : ")
            historique.append(f"Réinitialisation → {x}")
        elif choix == '11':  # Affichager de l'historique
            print("Historique des résultats :")
            for val in historique:
                print(val)
        elif choix == '12':  # Quitter le programme
            print("Au revoir!")
            break
        else:
            print("Choix invalide.")
            continue
        
        historique.append(x)  # Ajouter le résultat à l'historique
        print(f"Résultat : {x}")  # Afficher le résultat

calculatrice() 
