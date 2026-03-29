# Kody ASCII – zmiana liter w liczbę

## Wymagana wiedza

- Podstawy języka Python (lekcje 1-9)
- Intuicyjne rozumienie algorytmu jako listy kroków
- Podstawy myślenia analitycznego i krytyczne podejście do informacji
- Podstawowe metody szyfrowania

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. |
| V. Przestrzeganie prawa i zasad bezpieczeństwa. Uczeń: | |
| | 1) Opisuje kwestie etyczne związane z wykorzystaniem komputerów i sieci komputerowych, takie jak: **bezpieczeństwo**, cyfrowa tożsamość, **prywatność**, **równy dostęp do informacji i dzielenie się informacją**; | 

## Wspólne eksperymenty w języku Python (15 minut)

Aby zrozumieć, jak komputer „widzi” litery, musimy poznać kody ASCII. 
Każda litera ma przypisaną liczbę. 

W Pythonie funkcja `ord('A')` powie nam, jaki numer ma litera A.
Funkcja `chr(65)` zamieni numer z powrotem na literę.

Litery wielkie (od `A` do `Z`) są ponumerowane zaczynając od `65`, i kolejne litery alfabetu mają kolejne wartości.
Litera `A` ma numer `65`, litera `B` ma numer `66` i tak dalej.

```Python
litera = "A"
kod = ord(litera)
nowy_kod = kod + 3
nowa_litera = chr(nowy_kod)
print(nowa_litera) # Wypisze "D"
```

Zagadka: Jak przesunąć literę `Z` o `1` do przodu, czyli zamienić w `A`?

## Zadania do rozwiązania na komputerze (30 minut)

### Zadanie 1: Rozgrzewka z ASCII

Napisz program, który wczyta jedną wielką literę alfabetu i wypisze jej kod ASCII.

### Zadanie 2: ASCII kodowanie

Napisz program, który wczyta słowo i wypisał wszystkie jego litery jako kody ASCII.

Na przykład, dla `ABC`, program powinien wypisać `65 66 67`.

### Zadanie 3: Mały Cezar

Napisz program, który wczyta jedną wielką literę alfabetu i wypisze literę przesuniętą o 1 miejsce (szyfr Cezara z kluczem 1).

### Zadanie 4: Szyfrator słów

Zmodyfikuj program tak, aby wczytał słowo i wypisał je w postaci zaszyfrowanej, przesunięte o 1 miejsce. Potraktuj słowo jako zbiór znaków i do każdego zastosuj przesunięcie.
