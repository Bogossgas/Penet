import math

def afficher_menu(x):
    print(f"Choisissez une opération :")
    print(f"1) {x} + y")
    print(f"2) {x} - y")
    print(f"3) {x} × y")
    print(f"4) {x} ÷ y")
    print(f"5) √{x}")
    print("6) Quitter")

def obtenir_nombre(message):
    while True:
        try:
            nombre = input(message)
            if '.' in nombre:
                return float(nombre)
            else:
                return int(nombre)

def calculatrice():
    x = obtenir_nombre("Entrez un nombre : ")
    
    while True:
        afficher_menu(x)
        choix = input("Choix : ")
        
        if choix == '1':
            y = obtenir_nombre("Valeur de y : ")
            x = x + y
        elif choix == '2':
            y = obtenir_nombre("Valeur de y : ")
            x = x - y
        elif choix == '3':
            y = obtenir_nombre("Valeur de y : ")
            x = x * y
        elif choix == '4':
            y = obtenir_nombre("Valeur de y : ")
            if y != 0:
                x = x / y
            else:
                print("Division par zéro impossible.")
        elif choix == '5':
            if x >= 0:
                x = math.sqrt(x)
            else:
                print("Racine carrée d'un nombre négatif impossible.")
        elif choix == '6':
            print("Au revoir!")
            break
        else:
            print("Choix invalide.")
        
        print(f"Résultat : {x}")

calculatrice()

