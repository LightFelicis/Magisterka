# Algorytm Euklidesa – zastosowanie

## Wymagana wiedza

- Pętla `while`
- Pojęcie największego wspólnego dzielnika (NWD)

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 1) Wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów. | 1) Stosuje instrukcje iteracyjne. |

## Wstęp teoretyczny (15 minut)

Algorytm Euklidesa to jeden z najstarszych znanych algorytmów (opisany już ok. 300 lat p.n.e.!). Służy do znajdowania **Największego Wspólnego Dzielnika (NWD)** dwóch liczb całkowitych. 

Zamiast wypisywać wszystkie dzielniki obu liczb i szukać największego, Euklides zauważył pewną własność:

### Dlaczego odejmowanie działa? (Dowód intuicyjny)

Załóżmy, że mamy dwie liczby: $a$ oraz $b$ ($a > b$). Jeśli jakaś liczba $d$ jest wspólnym dzielnikiem $a$ i $b$, to musi ona również dzielić ich różnicę, czyli $(a - b)$.

**Dlaczego?**
1. Skoro $d$ dzieli $a$, to możemy zapisać: $a = n \cdot d$.
2. Skoro $d$ dzieli $b$, to możemy zapisać: $b = m \cdot d$.
3. Wtedy ich różnica: $a - b = (n \cdot d) - (m \cdot d) = d \cdot (n - m)$.

Jak widzisz, różnica $(a - b)$ również jest wielokrotnością liczby $d$. Oznacza to, że szukając NWD, możemy zastąpić większą liczbę różnicą tych liczb, a wynik się nie zmieni. Powtarzając to, aż liczby będą równe, otrzymamy właśnie ich największy wspólny dzielnik.

### Przykład "na kartce": NWD(28, 12)
1. Mamy pary (28, 12). $28 > 12$, więc odejmujemy: $28 - 12 = 16$.
2. Mamy parę (16, 12). $16 > 12$, więc odejmujemy: $16 - 12 = 4$.
3. Mamy parę (4, 12). $12 > 4$, więc odejmujemy: $12 - 4 = 8$.
4. Mamy parę (4, 8). $8 > 4$, więc odejmujemy: $8 - 4 = 4$.
5. Mamy parę (4, 4). Liczby są równe! **NWD to 4**.

### Wizualizacja (Geometria)
Wyobraź sobie prostokąt o bokach $a$ i $b$. Szukanie NWD to tak naprawdę próba znalezienia największego kwadratu, którym można idealnie "wykafelkować" ten prostokąt bez zostawiania wolnych miejsc.

## Wspólne eksperymenty (10 minut)

Przeanalizujmy kod implementujący tę logiczną ścieżkę:

```python
a = int(input("a: "))
b = int(input("b: "))
while a != b:
    if a > b:
        a = a - b
    else:
        b = b - a
print("NWD to:", a)
```

## Zadania do rozwiązania (15 minut)

1. **NWW**: Wykorzystaj wzór `NWW(a,b) = (a*b) / NWD(a,b)` aby napisać kalkulator najmniejszej wspólnej wielokrotności.
2. **Skracanie ułamków**: Napisz program, który wczyta licznik i mianownik, a następnie wypisze je po skróceniu ich przez NWD.
3. **Wersja z modulo**: Spróbuj zaimplementować szybszą wersję algorytmu Euklidesa używając operatora `%`.

!!! note
    W bibliotece `math` istnieje gotowa funkcja `gcd(a, b)`, która robi to samo!