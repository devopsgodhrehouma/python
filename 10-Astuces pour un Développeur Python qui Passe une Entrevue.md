# **Astuces pour un Développeur Python qui Passe une Entrevue**  

Les entrevues techniques en Python peuvent être un terrain miné. Si tu veux éviter que le recruteur fronce les sourcils et se demande si tu codes en PHP le soir en cachette, voici une liste d'astuces pour faire bonne impression.  

---

## **Exemple 1 – Ne sois pas un développeur qui écrit trop de code**  

**Mauvais : Trop verbeux**  
```python
nombres = [10, 20, 30, 40, 50]
```

**Correct : Utilisation de `range()`**  
```python
nombres = list(range(10, 51, 10))
```

**Meilleur : Pythonic et compact**  
```python
nombres = [x * 10 for x in range(1, 6)]
```

Le premier est correct mais manuel, le second est mieux, et le troisième montre que tu sais manipuler les itérations avec `list comprehension`.  

---

## **Exemple 2 – Savoir utiliser les compréhensions de listes**  

**Mauvais : Boucle `for` inutilement longue**  
```python
carrés = []
for x in nombres:
    carrés.append(x ** 2)
```

**Correct : Élimination des `append()` inutiles**  
```python
carrés = [x ** 2 for x in nombres]
```

Si tu écris une boucle `for` juste pour construire une liste, tu perds des points. Les compréhensions de listes sont **faites pour ça**.  

---

## **Exemple 3 – Arrête d’écrire des fonctions trop longues**  

**Mauvais : Fonction verbeuse et inefficace**  
```python
def filtrer_pairs(liste):
    resultat = []
    for x in liste:
        if x % 2 == 0:
            resultat.append(x)
    return resultat
```

**Correct : Utilisation d’une compréhension de liste**  
```python
def filtrer_pairs(liste):
    return [x for x in liste if x % 2 == 0]
```

**Meilleur : Utilisation de `lambda` (si la fonction est simple)**  
```python
filtrer_pairs = lambda liste: [x for x in liste if x % 2 == 0]
```

Ne surcharge pas tes définitions de fonctions si un `lambda` ou une compréhension de liste fait le travail en une ligne.  

---

## **Exemple 4 – Utiliser `zip()` au lieu de bricoler avec des index**  

**Mauvais : Utilisation manuelle des index**  
```python
noms = ["Alice", "Bob", "Charlie"]
notes = [85, 92, 78]

for i in range(len(noms)):
    print(noms[i], notes[i])
```

**Correct : Utilisation de `zip()`**  
```python
for nom, note in zip(noms, notes):
    print(nom, note)
```

Si tu utilises `range(len(...))` pour parcourir plusieurs listes, le recruteur risque de te demander pourquoi tu n’utilises pas `zip()`.  

---

## **Exemple 5 – Utiliser `enumerate()` au lieu de bricoler un compteur**  

**Mauvais : Création manuelle d’un index**  
```python
i = 0
for nom in noms:
    print(i, nom)
    i += 1
```

**Correct : Utilisation de `enumerate()`**  
```python
for i, nom in enumerate(noms):
    print(i, nom)
```

Si tu gères ton propre compteur, tu donnes l’impression de ne pas connaître les outils de base du langage.  

---

## **Exemple 6 – Utiliser les f-strings au lieu de `.format()`**  

**Mauvais : Concaténation de chaînes archaïque**  
```python
nom = "Alice"
print("Bonjour, " + nom + " !")
```

**Correct : Utilisation de `.format()`**  
```python
print("Bonjour, {} !".format(nom))
```

**Meilleur : Utilisation des f-strings (Python 3.6+)**  
```python
print(f"Bonjour, {nom} !")
```

Si tu concatènes des chaînes avec `+`, le recruteur pourrait penser que tu codes en Python 2.  

---

## **Exemple 7 – Éviter les pièges des valeurs par défaut mutables**  

**Mauvais : Utilisation de listes mutables comme valeur par défaut**  
```python
def ajouter_element(liste=[]):
    liste.append(42)
    return liste

print(ajouter_element())  # [42]
print(ajouter_element())  # [42, 42] 😱
```

**Correct : Utilisation de `None` comme valeur par défaut**  
```python
def ajouter_element(liste=None):
    if liste is None:
        liste = []
    liste.append(42)
    return liste
```

Si tu ne fais pas attention aux valeurs par défaut mutables, ton code pourrait se comporter bizarrement et le recruteur pourrait te piéger avec une question sur la mutabilité.  

---

## **Exemple 8 – Ne pas abuser des `try-except`**  

**Mauvais : Capturer toutes les exceptions sans raison**  
```python
try:
    x = 1 / 0
except:
    print("Erreur !")
```

**Correct : Spécifier l’exception**  
```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Division par zéro détectée !")
```

Capturer **toutes** les exceptions sans distinction est un **mauvais signal**. Un bon développeur Python sait gérer **précisément** les erreurs attendues.  

---

## **Exemple 9 – Utiliser les `set()` pour éliminer les doublons**  

**Mauvais : Utilisation d’une boucle pour filtrer les doublons**  
```python
nombres = [1, 2, 2, 3, 4, 4, 5]
uniques = []
for x in nombres:
    if x not in uniques:
        uniques.append(x)
```

**Correct : Utilisation de `set()`**  
```python
nombres = [1, 2, 2, 3, 4, 4, 5]
uniques = list(set(nombres))
```

Si tu parcours une liste pour supprimer les doublons, le recruteur pourrait **te regarder avec suspicion**.  

---

## **Exemple 10 – Utiliser un `defaultdict` au lieu de bricoler des dictionnaires**  

**Mauvais : Vérification manuelle des clés d’un dictionnaire**  
```python
notes = {}
eleves = ["Alice", "Bob", "Alice", "Charlie"]

for eleve in eleves:
    if eleve not in notes:
        notes[eleve] = 0
    notes[eleve] += 1
```

**Correct : Utilisation de `defaultdict`**  
```python
from collections import defaultdict

notes = defaultdict(int)
for eleve in eleves:
    notes[eleve] += 1
```

Si tu ne connais pas `defaultdict`, tu risques d’écrire plus de code que nécessaire.  

---

### **Conclusion**  

Si tu veux réussir une entrevue Python, retiens ces **principes clés** :  

- **Moins de code = mieux (dans la limite du lisible)**  
- **Utilise les outils natifs de Python (`zip()`, `enumerate()`, `set()`, `defaultdict()`)**  
- **Ne tombe pas dans les pièges classiques (mutabilité, gestion des erreurs, optimisations idiomatiques)**  

Si tu maîtrises ces astuces, tu ne devrais pas seulement **passer** ton entrevue, mais aussi **impressionner** ton recruteur.
