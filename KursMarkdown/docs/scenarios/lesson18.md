# Moduł scikit-learn i sprytniejsze drzewa decyzyjne

## Wymagana wiedza

- Podstawy funkcji i list
- Instalacja bibliotek (`pip install scikit-learn`)

## Wstęp teoretyczny (15 minut)

Zamiast ręcznie pisać instrukcje `if`, możemy pozwolić komputerowi "nauczyć się" zasad na podstawie przykładów. Do tego służy biblioteka **scikit-learn**.

## Przykład kodu (20 minut)

Nauczymy komputer rozpoznawać, czy owoc to jabłko czy pomarańcza na podstawie wagi i tekstury:

```python
from sklearn import tree

# Dane: [waga w gramach, tekstura (0-gładka, 1-szorstka)]
features = [[140, 0], [130, 0], [150, 1], [170, 1]]
# Wyniki: 0 dla jabłka, 1 dla pomarańczy
labels = [0, 0, 1, 1]

clf = tree.DecisionTreeClassifier()
clf = clf.fit(features, labels)

wynik = clf.predict([[160, 1]])
if wynik == 0:
    print("To jabłko!")
else:
    print("To pomarańcza!")
```

## Zadania do rozwiązania (10 minut)

1. **Więcej danych**: Dodaj 4 własne przykłady do listy `features` i `labels`. Czy model stał się "mądrzejszy"?
2. **Nowa cecha**: Dodaj trzecią cechę (np. kolor: 0-czerwony, 1-pomarańczowy) i sprawdź, jak wpływa na wynik.

!!! note
    To, co zrobiliśmy, nazywa się **uczeniem nadzorowanym** (supervised learning).