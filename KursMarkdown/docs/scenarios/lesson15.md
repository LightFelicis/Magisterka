# Wyszukiwanie w zbiorze – Liniowo znajdujemy minimum, maksimum

## Wymagana wiedza

- Listy (`list`)
- Pętla `for` przechodząca po elementach

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 1) Opisuje dane i wyniki. |
| II. Programowanie i rozwiązywanie problemów. | 1) Stosuje zmienne i tablice. |

## Wstęp teoretyczny (15 minut)

Aby znaleźć najmniejszą liczbę w worku (liście), zakładamy, że pierwsza z brzegu jest najmniejsza, a potem porównujemy ją z każdą kolejną. Jeśli znajdziemy mniejszą – ona staje się naszym nowym "rekordzistą".

## Wspólne eksperymenty (15 minut)

```python
liczby = [7, 3, 9, 1, 5]
najmniejsza = liczby[0]

for x in liczby:
    if x < najmniejsza:
        najmniejsza = x

print("Najmniejsza liczba to:", najmniejsza)
```

## Zadania do rozwiązania (60 minut)

1. **Maksimum**: Napisz program znajdujący największy element w liście.
2. **Pozycja**: Zmodyfikuj program tak, aby oprócz samej wartości wypisał też indeks (miejsce), na którym znajduje się najmniejsza liczba.
3. **Rozpiętość**: Oblicz różnicę między największą a najmniejszą liczbą w zbiorze (tzw. rozstęp).
4. **Średnia bez skrajności**: Oblicz średnią ocen ucznia, ale odrzuć najniższą i najwyższą ocenę (tak jak w skokach narciarskich).

W Pythonie istnieją gotowe funkcje `min(lista)` oraz `max(lista)`, ale warto wiedzieć, jak działają "pod spodem".