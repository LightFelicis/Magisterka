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

## Zadania do rozwiązania na platformie Szkopuł

### Haxor

![haxor](./lesson10-materials/haxor.png)

Od dawna wiadomo, że hakerzy posługują się własnym językiem, różnymi skrótami i innymi formami zaciemniania, żeby zacierać ścieżki po sobie. O najlepszych z nich zwykle mawia się „h4x0rzy”.

Niektórzy hakerzy czasami zamieniają niektóre litery na cyfry, żeby ich tekst wyglądał bardziej profesjonalnie. Każde wystąpienie jednej z liter podanych poniżej w tabeli zamieniane jest na odpowiadającą jej cyfrę. Pozostałe znaki pozostają niezmienione.

| Litera | Cyfra |
| :---: | :---: |
| **a** | **4** |
| **e** | **3** |
| **i** | **1** |
| **o** | **0** |
| **s** | **5** |

Napisz program, który wczyta napis, przekształci go do hakerskiego slangu zgodnie z powyższą tabelą i wypisze wynik na standardowe wyjście.

Do wczytania danych wykorzystaj polecenie `tekst = input()`.

#### Wejście

W pierwszym (jedynym) wierszu wejścia znajduje się niepusty ciąg małych liter alfabetu angielskiego – napis, który należy przekształcić. Długość napisu nie przekracza $1\ 000\ 000$ znaków.

#### Wyjście

W pierwszym (jedynym) wierszu wyjścia powinien się znaleźć napis z wejścia przedstawiony w hakerskim slangu.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| haxor | h4x0r |
| rigcz | r1gcz |
| aeios | 43105 |

??? Wskazówka
    Wykorzystaj instrukcję `if` i sprawdź kody ASCII kolejnych liter słowa. Jeśli kodem jest kod litery `a`,
    wypisz `4`, podobnie z pozostałymi literami `e`, `i` itd.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/-sW59iNCsLGhh8xyFPEmtn7F/site/?key=statement){ .md-button .md-button--primary }