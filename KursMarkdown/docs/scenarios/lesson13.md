# Kod binarny, szesnastkowy

## Wymagana wiedza

- Podstawowe operacje na liczbach
- Znajomość potęg liczby 2

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 3) Przedstawia sposób reprezentacji w komputerze: znaków, liczb (system binarny). |

## Wstęp teoretyczny (20 minut)

System liczbowy to zbiór reguł, według którego zapisuje się liczby.
Takie systemy można podzielić na dwa typy - pozycyjny oraz addytywny.

### Systemy addytywne (Dodawanie symboli)

W systemie **addytywnym** wartość liczby to suma jej cyfr. Taki system znamy ze szkoły,
jest nim system rzymski - `I = 1`, `V = 5`, `X = 10`, `L = 50`, `C = 100`, `D = 500`, `M = 1000`.
Liczba `CXXIII` to `100 + 10 + 10 + 1 + 1 + 1 = 123`.

### Systemy pozycyjne (Znaczenie pozycji cyfry)

W systemie pozycyjnym każda pozycja ma swoją **wagę**, która wpływa na
zapisaną na tej pozycji cyfrę.

#### System dziesiętny (Ludzki)

Używamy go codziennie. Składa się z dziesięciu cyfr (od `0` do `9`), a waga każdej pozycji to kolejna potęga liczby `10`.

Przykład liczby 123:
- 1 stoi na miejscu setek ($10^2$)
- 2 stoi na miejscu dziesiątek ($10^1$)
- 3 stoi na miejscu jedności ($10^0$)

W zapisie matematycznym $123 = 10^2 \cdot 1 + 10^1 \cdot 2 + 10^0 \cdot 3$.

#### System dwójkowy (Komputerowy)

Komputery nie rozumieją dziesięciu cyfr. Ich procesory składają się z milionów malutkich przełączników, które mogą być tylko w dwóch stanach: włączony (1) lub wyłączony (0). Dlatego komputery używają systemu dwójkowego, gdzie wagą jest potęga liczby 2.

O systemie binarnym najlepiej myśleć jak o rozkładzie liczby na potęgi dwójki, które trzeba do siebie dodać.

Na przykład liczba `50` to `32 + 16 + 2`, czyli potęg $2^5$, $2^4$ i $2^1$.
W zapisie systemu dwójkowego, liczba w systemie dziesiętnym `50` wygląda tak: `110010`.
`1` oznacza "bierzemy tę potęgę `2` do sumy", a `0` oznacza "nie bierzemy".

### Algorytm zamiany (metoda dzielenia przez 2)

Aby zamienić liczbę dziesiętną na binarną "ręcznie", dzielimy ją przez 2 i zapisujemy reszty z dzielenia. Proces powtarzamy, aż wynik dzielenia wyniesie 0. Wynik czytamy od dołu (od ostatniej zapisanej reszty).

Przykład dla liczby 13:
- `13 // 2 = 6`, reszta **1**
- `6 // 2 = 3`, reszta **0**
- `3 // 2 = 1`, reszta **1**
- `1 // 2 = 0`, reszta **1**
Wynik: `1101`.

## Wspólne eksperymenty (20 minut)

### Krok 1: Zbieranie reszt do listy
Najpierw zapiszmy nasze reszty w liście, tak jak robiliśmy to na kartce.

```python
n = int(input("Podaj liczbę: "))
reszty = []

while n > 0:
    reszta = n % 2
    reszty.append(reszta)
    n = n // 2

reszty.reverse()  # Pamiętasz? Wynik czytamy od dołu/od końca!
print("Lista bitów:", reszty)
```

### Dlaczego nie możemy po prostu dodawać?
Gdybyśmy napisali `wynik = wynik + reszta`, gdzie `wynik` jest liczbą (np. `0`), to dla liczby `13` (reszty: 1, 0, 1, 1) otrzymalibyśmy wynik `3`. 

**Dlaczego?** Bo komputer wykonałby działanie matematyczne: $1 + 0 + 1 + 1 = 3$. My natomiast nie chcemy **sumy** tych liczb, ale ich **zlepienia** w odpowiedniej kolejności.

### Krok 2: Zamiana na jeden tekst (String)
Aby otrzymać czytelny wynik, musimy zamienić listę cyfr na tekst:

```python
tekst = ""
for bit in reszty:
    tekst = tekst + str(bit)
print("Postać binarna:", tekst)
```

!!! tip "Szybszy sposób"
    W Pythonie możemy to zrobić w jednej linijce, dodając resztę bezpośrednio do tekstu:
    `wynik = str(reszta) + wynik`. Zauważ, że dodajemy `str(reszta)` na **początek**, co automatycznie odwraca nam wynik!

## Zadania do rozwiązania (15 minut)

System szesnastkowy to system, w którym podstawą jest liczba **16**. Ponieważ zabrakło nam pojedynczych cyfr, po `9` używamy liter: **A** (10), **B** (11), **C** (12), **D** (13), **E** (14) oraz **F** (15).

**Gdzie go stosujemy?**
*   **Kolory na stronach WWW (HEX)**: Zapis typu `#FF0000` to nic innego jak trzy liczby szesnastkowe określające jasność barwy czerwonej, zielonej i niebieskiej.
*   **Adresy fizyczne urządzeń (MAC)**: Każdy telefon i komputer ma unikalny numer karty sieciowej zapisany właśnie tak: `00:1A:2B:3C:4D:5E`.

1. **Wypisywacz binarny**: Napisz program, który wczyta liczby `a` i `b` i wypisze ich zapis w systemie binarnym.
2. **Suma w systemie binarnym** Napisz program, który wczyta liczby `a` i `b` i wypisze ich sumę w systemie binarnym.
3. **Wypisywacz szesnastkowy** Napisz program, który wczyta liczbę w systemie dziesiętnym i wypisze jej zapis w systemie szesnastkowym.

!!! Wskazówka
    Wykorzystaj kod do zamiany do systemu dwójkowego, ale dziel przez 16.

4. **Szesnastkowe kolory**: Wypisz zapisy szesnastkowe dla liczb od 0 do 255.
5. **Własna potęga**: Napisz program, który sprawdzi, czy podana liczba jest potęgą dwójki (liczby te w systemie binarnym mają tylko jedną jedynkę).
