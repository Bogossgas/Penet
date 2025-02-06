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
    print("12) Choisir un ancien résultat pour y")

def obtenir_nombre(message, historique):
    while True:
        nombre = input(message)
        if nombre == 'h' and historique:
            print("Historique des résultats :", historique)
            try:
                index = int(input("Entrez l'index du résultat souhaité : "))
                return historique[index]
            except (IndexError, ValueError):
                print("Index invalide. Veuillez réessayer.")
        elif '.' in nombre:
            return float(nombre)
        else:
            return int(nombre)

def calculatrice():
    historique = []
    x = obtenir_nombre("Entrez un nombre : ", historique)
    
    while True:
        afficher_menu(x)
        choix = input("Choix : ")
        
        if choix in ['1', '2', '3', '4', '6', '7', '8']:
            y = obtenir_nombre("Valeur de y (ou 'h' pour historique) : ", historique)
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
            x = obtenir_nombre("Entrez un nouveau nombre de départ : ", historique)
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

___________________________________________________________________________________
import math  # Importation du module math pour les opérations mathématiques avancées

def afficher_menu(x):
    # Affiche le menu des opérations disponibles avec la valeur actuelle de x
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
    # Demande à l'utilisateur de saisir un nombre et le convertit en int ou float selon la présence d'un point
    while True:
        nombre = input(message)
        if '.' in nombre:
            return float(nombre)
        else:
            return int(nombre)

def calculatrice():
    # Fonction principale de la calculatrice
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
        elif choix == '7':  # Modulo (reste de la division entière)
            y = obtenir_nombre("Valeur de y : ")
            x = x % y
        elif choix == '8':  # Puissance
            y = obtenir_nombre("Valeur de y : ")
            x = x ** y
        elif choix == '9':  # Inverse (1/x)
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
        print(f"Résultat : {x}")  # Afficher le résultat de l'opération

calculatrice()  # Lancement de la calculatrice
