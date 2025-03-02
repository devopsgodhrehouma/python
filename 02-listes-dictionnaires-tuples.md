# **Différences entre Listes, Dictionnaires et Tuples en Python** 📌

## **1️⃣ Introduction**
En Python, les **listes**, les **dictionnaires** et les **tuples** sont des structures de données fondamentales. Chacune d'elles a des caractéristiques et des usages spécifiques.

---

## **2️⃣ Liste (`list`)**
Une **liste** est une collection ordonnée et modifiable d'éléments.

### **Caractéristiques :**
- **Ordonnée** : Les éléments gardent leur position.
- **Mutable** : On peut modifier, ajouter ou supprimer des éléments.
- **Peut contenir différents types** : On peut stocker des nombres, chaînes, objets, etc.
- **Utilise des crochets `[]`**.

### **Exemples :**
```python
# Création d'une liste
fruits = ["pomme", "banane", "cerise"]

# Accès aux éléments
print(fruits[0])  # Affiche "pomme"

# Modification d'un élément
fruits[1] = "mangue"

# Ajout d'un élément
fruits.append("orange")

# Suppression d'un élément
fruits.remove("cerise")

print(fruits)  # Output: ['pomme', 'mangue', 'orange']
```

### **Quand utiliser une liste ?**
✅ Lorsque vous avez une collection **modifiable** et **ordonnée** d'éléments.

---

## **3️⃣ Tuple (`tuple`)**
Un **tuple** est une collection **ordonnée et immuable** d'éléments.

### **Caractéristiques :**
- **Ordonné** : Comme les listes, les tuples conservent l'ordre des éléments.
- **Immuable** : Une fois créé, on ne peut **pas** modifier un tuple.
- **Utilise des parenthèses `()`**.
- **Moins gourmand en mémoire** que les listes.

### **Exemples :**
```python
# Création d'un tuple
jours = ("lundi", "mardi", "mercredi")

# Accès aux éléments
print(jours[1])  # Affiche "mardi"

# Tentative de modification (génère une erreur)
# jours[1] = "dimanche"  # TypeError: 'tuple' object does not support item assignment
```

### **Quand utiliser un tuple ?**
✅ Lorsque vous avez une collection **ordonnée mais qui ne doit pas être modifiée** (ex : jours de la semaine, coordonnées GPS…).

---

## **4️⃣ Dictionnaire (`dict`)**
Un **dictionnaire** est une collection **non ordonnée** de paires **clé-valeur**.

### **Caractéristiques :**
- **Clés uniques** : Chaque clé est associée à une seule valeur.
- **Les valeurs sont modifiables**.
- **Utilise des accolades `{}`**.
- **Rapide pour les recherches** par clé.

### **Exemples :**
```python
# Création d'un dictionnaire
eleve = {
    "nom": "Alice",
    "âge": 20,
    "note": 15
}

# Accès aux valeurs
print(eleve["nom"])  # Affiche "Alice"

# Modification d'une valeur
eleve["âge"] = 21

# Ajout d'une nouvelle clé-valeur
eleve["matière"] = "Mathématiques"

# Suppression d'un élément
del eleve["note"]

print(eleve)  
# Output: {'nom': 'Alice', 'âge': 21, 'matière': 'Mathématiques'}
```

### **Quand utiliser un dictionnaire ?**
✅ Lorsque vous avez des **données associées** (comme une base de données : `nom → âge`).

---

## **5️⃣ Comparaison : Liste vs Tuple vs Dictionnaire**

| **Caractéristique** | **Liste (`list`)** | **Tuple (`tuple`)** | **Dictionnaire (`dict`)** |
|---------------------|--------------------|----------------------|---------------------------|
| **Ordre**          | Oui                | Oui                  | Non (depuis Python 3.6, les dicts gardent l’ordre) |
| **Modification**   | Oui (mutable)      | Non (immuable)       | Oui (valeurs modifiables, clés uniques) |
| **Accès**          | Index (`list[0]`)  | Index (`tuple[0]`)   | Clé (`dict["clé"]`) |
| **Duplication d'éléments** | Oui | Oui | Non (clés uniques) |
| **Performance**    | Moyen              | Rapide (moins gourmand) | Rapide pour les recherches |
| **Utilisation principale** | Stocker une liste d’éléments modifiables | Stocker des données constantes | Associer des valeurs à des clés |

---

## **6️⃣ Exemples Concrets**
### **📌 Exemple 1 : Gestion d'une classe d'élèves**
- **Liste** : Stocke les noms des élèves.
- **Tuple** : Contient les matières enseignées (car elles ne changent pas).
- **Dictionnaire** : Associe chaque élève à sa note.

```python
# Liste des élèves
eleves = ["Alice", "Bob", "Charlie"]

# Tuple des matières (ne change pas)
matieres = ("Maths", "Physique", "Histoire")

# Dictionnaire des notes
notes = {
    "Alice": 15,
    "Bob": 18,
    "Charlie": 12
}

print(notes["Bob"])  # Output: 18
```

---

### **📌 Exemple 2 : Système de gestion de produits**
- **Liste** : Stocke plusieurs produits.
- **Tuple** : Utilisé pour définir un produit (nom, prix).
- **Dictionnaire** : Associe un produit à son stock.

```python
# Liste des produits
produits = ["PC", "Téléphone", "Casque"]

# Tuple (nom, prix)
produit_info = ("PC", 1000)

# Dictionnaire stock produit → quantité
stock = {
    "PC": 10,
    "Téléphone": 25,
    "Casque": 50
}

print(stock["PC"])  # Output: 10
```

---

## **7️⃣ Conclusion**
- **Utilisez une liste** si vous avez une collection **modifiable** et **ordonnée**.
- **Utilisez un tuple** si vous avez une collection **fixe** et **ordonnée**.
- **Utilisez un dictionnaire** si vous avez des **associations clé-valeur**.

📌 **Exemple résumé :**
```python
# Liste
animaux = ["chat", "chien", "lapin"]

# Tuple
coordonnees = (48.8566, 2.3522)  # Latitude, Longitude

# Dictionnaire
capitales = {"France": "Paris", "Italie": "Rome"}
```

