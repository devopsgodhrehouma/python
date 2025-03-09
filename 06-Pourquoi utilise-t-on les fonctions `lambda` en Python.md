### 🚀 **Pourquoi utilise-t-on les fonctions `lambda` en Python ?**
Les **fonctions lambda** ne remplacent pas les fonctions classiques (`def`). Elles sont utiles dans **des cas spécifiques** où elles simplifient le code et évitent des définitions inutiles.

---

## ✅ **1. Éviter de définir une fonction qui ne sert qu'une seule fois**
Imaginez que vous avez besoin d’une fonction **juste une fois**. Créer une fonction avec `def` est parfois inutile.

🔴 **Avec une fonction classique (`def`) :**
```python
def ajouter_un(x):
    return x + 1

print(ajouter_un(5))  # Résultat : 6
```

🟢 **Avec `lambda` (plus direct) :**
```python
print((lambda x: x + 1)(5))  # Résultat : 6
```

✅ **Avantage :**
- Pas besoin de donner un nom à la fonction.
- Le code est plus compact.

---

## ✅ **2. Passer une fonction en argument à une autre fonction**
C’est l'usage **le plus courant** des `lambda`. Python permet d'envoyer une fonction comme paramètre d'une autre fonction.

---

### 📌 **Exemple : Trier une liste selon un critère**
🔴 **Avec une fonction classique :**
```python
def longueur(nom):
    return len(nom)

noms = ["Alice", "Bob", "Claire", "Dan"]
noms_tries = sorted(noms, key=longueur)

print(noms_tries)  # Résultat : ['Bob', 'Dan', 'Alice', 'Claire']
```

🟢 **Avec `lambda` (élimine la fonction `longueur()`) :**
```python
noms = ["Alice", "Bob", "Claire", "Dan"]
noms_tries = sorted(noms, key=lambda nom: len(nom))

print(noms_tries)  # Résultat : ['Bob', 'Dan', 'Alice', 'Claire']
```

✅ **Avantage :**
- Pas besoin de définir `longueur()`, qui ne servait qu’une seule fois.
- `lambda` évite une fonction inutile et allège le code.

---

## ✅ **3. Écrire des transformations simples avec `map()`, `filter()`, et `reduce()`**
Les fonctions `lambda` sont parfaites pour modifier des listes ou filtrer des valeurs.

### 🛠 **Exemple avec `map()`: Appliquer une opération à chaque élément**
🔴 **Avec `def` :**
```python
def doubler(x):
    return x * 2

nombres = [1, 2, 3, 4]
doubles = list(map(doubler, nombres))

print(doubles)  # Résultat : [2, 4, 6, 8]
```

🟢 **Avec `lambda` (plus court) :**
```python
nombres = [1, 2, 3, 4]
doubles = list(map(lambda x: x * 2, nombres))

print(doubles)  # Résultat : [2, 4, 6, 8]
```

✅ **Avantage :**
- `lambda` évite de créer une fonction juste pour une seule ligne.

---

### 🔍 **Exemple avec `filter()`: Garder certains éléments**
🔴 **Avec `def` :**
```python
def est_pair(x):
    return x % 2 == 0

nombres = [1, 2, 3, 4, 5, 6]
pairs = list(filter(est_pair, nombres))

print(pairs)  # Résultat : [2, 4, 6]
```

🟢 **Avec `lambda` :**
```python
nombres = [1, 2, 3, 4, 5, 6]
pairs = list(filter(lambda x: x % 2 == 0, nombres))

print(pairs)  # Résultat : [2, 4, 6]
```

✅ **Avantage :**
- `lambda` simplifie le code et le rend plus direct.

---

### 🔄 **Exemple avec `reduce()`: Réduire une liste en une seule valeur**
🔴 **Avec `def` :**
```python
from functools import reduce

def addition(x, y):
    return x + y

nombres = [1, 2, 3, 4, 5]
somme = reduce(addition, nombres)

print(somme)  # Résultat : 15
```

🟢 **Avec `lambda` :**
```python
from functools import reduce

nombres = [1, 2, 3, 4, 5]
somme = reduce(lambda x, y: x + y, nombres)

print(somme)  # Résultat : 15
```

✅ **Avantage :**
- `lambda` permet d’éliminer une fonction `addition()` inutile.

---

## ❌ **Quand NE PAS utiliser `lambda`**
### ⚠️ **1. Quand la fonction devient compliquée**
```python
# Mauvaise pratique : difficile à lire
calcul = lambda x: (x**2 + 3*x - 5)/((x-1)**2) if x != 1 else "Erreur"
```
✅ **Mieux avec `def` :**
```python
def calcul(x):
    if x == 1:
        return "Erreur"
    return (x**2 + 3*x - 5)/((x-1)**2)
```

---

### ⚠️ **2. Quand la lisibilité est réduite**
```python
# Mauvaise idée avec lambda
print((lambda x: x[::-1].upper())("hello"))
```
✅ **Mieux avec `def` :**
```python
def inverser_et_majuscules(texte):
    return texte[::-1].upper()

print(inverser_et_majuscules("hello"))  # Résultat : "OLLEH"
```

---

## 🎯 **Résumé : Pourquoi utiliser `lambda` ?**
| Cas | Fonction `def` | Fonction `lambda` |
|---|---|---|
| Fonction réutilisable | ✅ Oui | ❌ Non |
| Fonction courte (1 ligne) | ⚠️ Possible, mais long | ✅ Idéal |
| Fonction utilisée comme paramètre (`sorted()`, `map()`, etc.) | ❌ Pas optimal | ✅ Parfait |
| Fonction complexe | ✅ Oui | ❌ Non |

---

## 🚀 **Conclusion : Lambda est un outil, pas une obligation !**
- ✅ Utilisez `lambda` pour des **fonctions simples et rapides**.
- ❌ Évitez `lambda` si la fonction est **trop longue ou complexe**.
- 🎯 **L’objectif est toujours la lisibilité et la simplicité !**
