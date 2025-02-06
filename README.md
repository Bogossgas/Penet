# -*- coding: utf-8 -*-
"""
Created on Tue Feb  4 16:31:10 2025

Gaspard chanut
Hugo Jeandeau-diop

"""

import math

# Fonction pour afficher le menu des opérations
def afficher_menu(x):
    print(f"Choisissez une opération :")
    print(f"1) {x} + y")
    print(f"2) {x} - y")
    print(f"3) {x} × y")
    print(f"4) {x} ÷ y")
    print(f"5) √{x}")
    print(f"6) {x} div y")
    print(f"7) {x} mod y")
    print(f"8) {x} ^ y")
    print(f"9) inv({x})")
    print("10) Repartir à 0")
    print("11) Quitter")

# Fonction pour obtenir un nombre de l'utilisateur
def obtenir_nombre(message):
    while True:
        try:
            nombre = input(message)
            if '.' in nombre:
                return float(nombre)
            else:
                return int(nombre)
        except ValueError:
            print("Veuillez entrer un nombre valide.")

def choisir_historique(historique):
    print("Historique des résultats :")
    for i, valeur in enumerate(historique):
        print(f"{i + 1}) {valeur}")
    choix = obtenir_nombre("Choisissez un résultat pour y : ")
    return historique[choix - 1]

def calculatrice():
    historique = []
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
            y = obtenir_nombre("Valeur de y : ")
            x = x // y
        elif choix == '7':
            y = obtenir_nombre("Valeur de y : ")
            x = x % y
        elif choix == '8':
            y = obtenir_nombre("Valeur de y : ")
            x = x ** y
        elif choix == '9':
            if x != 0:
                x = 1 / x
            else:
                print("Inverse de zéro impossible.")
        elif choix == '10':
            x = obtenir_nombre("Entrez un nouveau nombre de départ : ")
        elif choix == '11':
            print("Au revoir!")
            break
        else:
            print("Choix invalide.")
        
        historique.append(x)
        print(f"Résultat : {x}")

calculatrice()
















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
            x = x / y
        elif choix == '5':
            x = math.sqrt(x)
        elif choix == '6':
            print("Au revoir!")
            break
        else:
            print("Choix invalide.")
        
        print(f"Résultat : {x}")

calculatrice()



import math

def afficher_menu(x):
    print(f"Choisissez une opération :")
    print(f"1) {x} + y")
    print(f"2) {x} - y")
    print(f"3) {x} × y")
    print(f"4) {x} ÷ y")
    print(f"5) √{x}")
    print(f"6) {x} div y")
    print(f"7) {x} mod y")
    print(f"8) {x} ^ y")
    print(f"9) inv({x})")
    print("10) Recommencer")
    print("11) Quitter")

def obtenir_nombre(message):
    while True:
        nombre = input(message)
        if '.' in nombre:
            return float(nombre)
        else:
            return int(nombre)

def calculatrice():
    historique = []
    x = obtenir_nombre("Entrez un nombre : ")
    
    while True:
        afficher_menu(x)
        choix = input("Choix : ")
        
        if choix in ['1', '2', '3', '4', '6', '7', '8']:
            y = obtenir_nombre("Valeur de y : ")
            if choix == '1':
                x = x + y
            elif choix == '2':
                x = x - y
            elif choix == '3':
                x = x * y
            elif choix == '4':
                x = x / y
            elif choix == '6':
                x = x // y
            elif choix == '7':
                x = x % y
            elif choix == '8':
                x = x ** y
        elif choix == '5':
            x = math.sqrt(x)
        elif choix == '9':
            x = 1 / x
        elif choix == '10':
            x = obtenir_nombre("Entrez un nouveau nombre de départ : ")
            historique.clear()
            continue
        elif choix == '11':
            print("Au revoir!")
            break
        else:
            print("Choix invalide.")
            continue
        
        historique.append(x)
        print(f"Résultat : {x}")
        
        # Afficher l'historique
        print("Historique des résultats :", historique)

calculatrice()

