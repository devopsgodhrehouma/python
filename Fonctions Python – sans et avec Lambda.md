# 🚩 **Titre du cours : Fonctions Python – sans et avec Lambda**

**Description** :  
Ce cours pédagogique est conçu pour les débutants. Vous apprendrez à créer des fonctions classiques claires et réutilisables, puis découvrirez ce qu'est une fonction lambda, en quoi elle est utile, et comment l’utiliser simplement.

**Slug** : `fonctions-python-sans-et-avec-lambda`

**Emoji** : 🐍🚀

---

# 📚 Table des matières :

1. [Partie 1 : Les fonctions classiques (sans lambda)](#partie-1-les-fonctions-classiques-sans-lambda)
   - Qu’est-ce qu’une fonction ?
   - Créer une fonction simple
   - Paramètres et arguments
   - Valeur de retour
   - Plusieurs exemples pédagogiques

2. [Partie 2 : Les fonctions lambda](#partie-2-les-fonctions-lambda)
   - Qu’est-ce qu’une fonction lambda ?
   - Syntaxe claire et simple
   - Exemple concret : Comparer une fonction classique et une fonction lambda
   - Quand utiliser les fonctions lambda ?
   - Erreurs fréquentes à éviter

---

# Partie 1 : Les fonctions classiques (sans lambda)

1. **Les fonctions Python classiques (sans lambdas)** 🐍
2. **Les fonctions lambda en Python** 🚀


## 🟢 Qu’est-ce qu’une fonction ?

Une fonction est un morceau de code réutilisable qui exécute une tâche précise. On crée une fonction une fois et on peut l’utiliser autant de fois qu'on le souhaite.

## 🟢 Créer une fonction simple

Pour créer une fonction en Python, on utilise le mot-clé `def`.

**Code 1 : Fonction simple**
```python
def saluer():
    print("Bonjour tout le monde !")

# Appel de la fonction
saluer()
```

**Résultat :**
```
Bonjour tout le monde !
```

**Explication :**
- `def` définit une fonction.
- `saluer` est le nom choisi.
- Le bloc indenté contient le code à exécuter.

⬆️ [Retour à la Table des Matières](#📚-table-des-matières-)

---

## 🟢 Paramètres et arguments

On peut passer des informations à une fonction à l’aide de paramètres.

**Code 2 : Fonction avec paramètres**
```python
def saluer(nom):
    print(f"Bonjour {nom} !")

# Appels
saluer("Alice")
saluer("Bob")
```

**Résultat :**
```
Bonjour Alice !
Bonjour Bob !
```

**Explication :**
- `nom` est le paramètre de la fonction.
- `"Alice"` et `"Bob"` sont des arguments (valeurs concrètes).

⬆️ [Retour à la Table des Matières](#📚-table-des-matières-)

---

## 🟢 Valeur de retour

Une fonction peut retourner une valeur avec `return`.

**Code 3 : Fonction avec valeur de retour**
```python
def addition(a, b):
    return a + b

resultat = addition(3, 5)
print(resultat)
```

**Résultat :**
```
8
```

**Explication :**
- La fonction additionne `a` et `b` puis renvoie le résultat.

⬆️ [Retour à la Table des Matières](#📚-table-des-matières-)

---

## 🟢 Plusieurs exemples pédagogiques

**Exemple 1 : Vérifier si un nombre est pair**
```python
def est_pair(nombre):
    return nombre % 2 == 0

print(est_pair(10))  # True
print(est_pair(7))   # False
```

**Exemple 2 : Afficher une liste d’éléments**
```python
def afficher_liste(liste):
    for element in liste:
        print("-", element)

courses = ["pomme", "pain", "fromage"]
afficher_liste(courses)
```

**Résultat :**
```
- pomme
- pain
- fromage
```

Ces exemples simples montrent comment les fonctions rendent le code clair et réutilisable.

⬆️ [Retour à la Table des Matières](#📚-table-des-matières-)

---

# Partie 2 : Les fonctions lambda

## 🚩 Qu’est-ce qu’une fonction lambda ?

Une fonction lambda est une petite fonction **anonyme**, écrite sur une seule ligne.

Elle est pratique pour des opérations simples et rapides.

---

## 🚩 Syntaxe claire et simple

Syntaxe d'une fonction lambda :
```python
lambda arguments : expression
```

Exemple ultra simple :
```python
ajouter_un = lambda x: x + 1

print(ajouter_un(4))  # Résultat : 5
```

Explication :
- `lambda` : mot-clé pour créer une fonction lambda
- `x` : argument de la fonction
- `x + 1` : expression retournée

---

## 🚩 Exemple concret : Comparer fonction classique et lambda

Voyons clairement la différence entre les deux approches.

**Code 4 : Fonction classique**
```python
def multiplier_par_deux(x):
    return x * 2

print(multiplier_par_deux(5))  # 10
```

**Code 5 : Fonction lambda**
```python
multiplier_par_deux = lambda x: x * 2

print(multiplier_par_deux(5))  # 10
```

Explication :
- Les deux codes produisent exactement le même résultat.
- La fonction lambda est plus courte, idéale pour des fonctions simples.

---

## 🚩 Quand utiliser les fonctions lambda ?

**Utilisez une fonction lambda lorsque :**
- Vous avez besoin d’une fonction très simple et courte.
- Vous voulez l’utiliser immédiatement sans avoir besoin de la réutiliser ailleurs.

**Exemple courant avec `sorted()` :**
```python
noms = ["Alice", "Bob", "Claire", "Dan"]

# Trier par longueur de nom
noms_tries = sorted(noms, key=lambda nom: len(nom))

print(noms_tries)  # ['Bob', 'Dan', 'Alice', 'Claire']
```

---

## 🚩 Erreurs fréquentes à éviter

**Erreur 1 : Utiliser lambda pour des fonctions complexes.**

Ne faites pas ça :
```python
# Difficile à lire
mauvaise_idee = lambda x: (x**2 + 3*x - 5)/((x-1)**2)

# Bonne pratique : utiliser une fonction normale
def calcul_complexe(x):
    return (x**2 + 3*x - 5)/((x-1)**2)
```

**Erreur 2 : Essayer d’inclure plusieurs instructions :**

Lambda est limité à une seule expression simple :

❌ Erreur :
```python
lambda x: print(x), x + 1  # incorrect
```

✅ Correct :
```python
def afficher_et_incrementer(x):
    print(x)
    return x + 1
```

---

# ✅ Résumé visuel ultra-simple :

| Point               | Fonction classique | Fonction lambda |
|---------------------|--------------------|-----------------|
| Réutilisable ?      | ✅ Oui             | ⚠️ Rarement     |
| Lisibilité ?        | ✅ Très bonne      | ⚠️ Limitée      |
| Utilité principale  | Tous les cas       | Fonctions courtes |

---

## 🎯 Conclusion pédagogique simple :

- Utilisez des fonctions classiques (`def`) pour des tâches complexes, réutilisables, et lisibles.
- Utilisez des fonctions lambda pour des petites tâches très courtes et ponctuelles.

Maintenant, vous savez exactement quand utiliser chaque type de fonction ! 🎉

⬆️ [Retour à la Table des Matières](#📚-table-des-matières-)

