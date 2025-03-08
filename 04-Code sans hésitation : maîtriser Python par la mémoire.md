# Introduction

### **Cette fois, c'est particulier**  

D'habitude, l'important est de comprendre. Cette fois, il faut mémoriser.  

Lors de l'évaluation, je choisirai un exercice au hasard. Sans documentation, sans notes, vous devrez l'écrire parfaitement et l'expliquer.  

Pourquoi ?  
- Parce qu'en examen ou en entretien, vous serez seuls face à votre écran.  
- Parce que mémoriser crée des réflexes immédiats.  
- Parce qu'un bon développeur ne doit pas hésiter sur les bases.  

Apprenez par cœur, répétez, testez-vous. Cela doit devenir automatique.



## **1️⃣ Exercice 1 : Manipulation d'une liste de nombres**
📌 **Objectif** : Apprendre à manipuler une liste (ajout, suppression, modification, calcul).

### **Enoncé :**
1. Crée une liste appelée `nombres` contenant les valeurs `[10, 20, 30, 40, 50]`.
2. Ajoute le nombre `60` à la fin de la liste.
3. Remplace le deuxième élément (`20`) par `25`.
4. Supprime le dernier élément de la liste sans utiliser `del`.
5. Écris une fonction `somme_liste(liste)` qui prend une liste de nombres et retourne la somme des éléments.
6. Définir une autre liste `notes` contenant les valeurs `[50, 60]` et calculer la somme des notes en utilisant la fonction `somme_liste` que vous avez développé.
7. Définir une autre liste de votre choix et calculez sa somme en utilisant la fonction `somme_liste`.

### **Correction attendue :**
```python
# Étape 1 : Création de la liste
nombres = [10, 20, 30, 40, 50]

# Étape 2 : Ajouter 60
nombres.append(60)

# Étape 3 : Modifier le deuxième élément
nombres[1] = 25

# Étape 4 : Supprimer le dernier élément
nombres.pop()

# Étape 5 : Fonction pour calculer la somme
def somme_liste(liste):
    return sum(liste)

# Test de la fonction
print(somme_liste(nombres))  # Output : 10 + 25 + 30 + 40 = 105
```
---

## **2️⃣ Exercice 2 : Création et manipulation d'un dictionnaire**
📌 **Objectif** : Comprendre l'utilisation des dictionnaires et des clés/valeurs.

### **Enoncé :**
1. Crée un dictionnaire appelé `eleve` avec les clés suivantes :
   - `"nom"` : `"Alice"`
   - `"âge"` : `20`
   - `"note"` : `15`
2. Ajoute une nouvelle clé `"matière"` avec la valeur `"Maths"`.
3. Modifie l'âge de l'élève pour `21`.
4. Supprime la clé `"note"` du dictionnaire.
5. Écris une fonction `afficher_info(eleve)` qui affiche les clés et valeurs du dictionnaire sous la forme `"clé : valeur"`.

### **Correction attendue :**
```python
# Étape 1 : Création du dictionnaire
eleve = {"nom": "Alice", "âge": 20, "note": 15}

# Étape 2 : Ajout de la clé "matière"
eleve["matière"] = "Maths"

# Étape 3 : Modification de l'âge
eleve["âge"] = 21

# Étape 4 : Suppression de la clé "note"
del eleve["note"]

# Étape 5 : Fonction pour afficher les informations
def afficher_info(eleve):
    for cle, valeur in eleve.items():
        print(f"{cle} : {valeur}")

# Test de la fonction
afficher_info(eleve)
```
---

## **3️⃣ Exercice 3 : Compréhension de listes**
📌 **Objectif** : Utiliser les **compréhensions de listes** pour manipuler les données de manière concise.

### **Enoncé :**
1. Crée une liste `nombres` contenant les nombres de `1` à `10`.
2. Utilise une **compréhension de liste** pour créer une liste `carrés` contenant le carré de chaque nombre.
3. Crée une **compréhension de liste** qui ne garde que les nombres pairs de la liste `nombres`.
4. Écris une fonction `filtrer_sup_5(liste)` qui retourne une nouvelle liste contenant uniquement les nombres supérieurs à `5`.

### **Correction attendue :**
```python
# Étape 1 : Liste des nombres de 1 à 10
nombres = list(range(1, 11))

# Étape 2 : Liste des carrés
carrés = [x ** 2 for x in nombres]

# Étape 3 : Liste des nombres pairs
pairs = [x for x in nombres if x % 2 == 0]

# Étape 4 : Fonction de filtrage
def filtrer_sup_5(liste):
    return [x for x in liste if x > 5]

# Tests
print(carrés)  # Output: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
print(pairs)   # Output: [2, 4, 6, 8, 10]
print(filtrer_sup_5(nombres))  # Output: [6, 7, 8, 9, 10]
```
---

## **4️⃣ Exercice 4 : Manipulation des tuples**
📌 **Objectif** : Comprendre la **non-mutabilité** des tuples et leur utilité.

### **Enoncé :**
1. Crée un tuple `jours` contenant les jours de la semaine.
2. Affiche le **troisième jour** du tuple.
3. Tente de modifier un élément du tuple et note l’erreur obtenue.
4. Convertis le tuple en **liste**, ajoute `"Dimanche"`, puis reconvertis-le en tuple.
5. Écris une fonction `plus_long_mot(mots)` qui prend un tuple de mots et retourne le mot le plus long.

### **Correction attendue :**
```python
# Étape 1 : Création du tuple
jours = ("Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi")

# Étape 2 : Affichage du troisième jour
print(jours[2])  # Output: "Mercredi"

# Étape 3 : Tentative de modification (génère une erreur)
# jours[2] = "Dimanche"  # TypeError: 'tuple' object does not support item assignment

# Étape 4 : Conversion en liste et modification
jours_liste = list(jours)
jours_liste.append("Dimanche")
jours = tuple(jours_liste)

# Étape 5 : Fonction pour trouver le mot le plus long
def plus_long_mot(mots):
    return max(mots, key=len)

# Test
mots = ("Python", "Programmation", "Code", "Développement")
print(plus_long_mot(mots))  # Output: "Développement"
```
---

## **5️⃣ Exercice 5 : Boucles et conditions**
📌 **Objectif** : Travailler avec les **boucles et conditions**.

### **Enoncé :**
1. Écris une boucle `while` qui affiche les nombres de `1` à `10`.
2. Modifie cette boucle pour n'afficher que les nombres **pairs**.
3. Écris une boucle `for` qui affiche chaque lettre du mot `"PYTHON"`, une par ligne.
4. Utilise `range()` pour afficher les nombres de `5` à `50` avec un pas de `5`.
5. Implémente un programme qui demande un mot de passe jusqu'à ce que l'utilisateur entre `"Python123"`.

### **Correction attendue :**
```python
# Étape 1 : Boucle while de 1 à 10
i = 1
while i <= 10:
    print(i)
    i += 1

# Étape 2 : Affichage des nombres pairs
i = 2
while i <= 10:
    print(i)
    i += 2

# Étape 3 : Boucle for pour afficher les lettres de "PYTHON"
for lettre in "PYTHON":
    print(lettre)

# Étape 4 : Utilisation de range() avec un pas de 5
for i in range(5, 51, 5):
    print(i)

# Étape 5 : Vérification du mot de passe
mot_de_passe = ""
while mot_de_passe != "Python123":
    mot_de_passe = input("Entrez le mot de passe : ")

print("Accès autorisé !")
```
---
