# Lekcja 14 – Systemy liczbowe: dwójkowy i szesnastkowy

**Czas realizacji:** 90 minut (2 godziny lekcyjne). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Podstawowe operacje na liczbach.

- Znajomość potęg liczby 2.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 3) przedstawia sposoby reprezentowania w komputerze wartości logicznych, liczb naturalnych (system binarny), znaków (kody ASCII) i tekstów. |

## Wstęp teoretyczny (20 minut)

System liczbowy to zbiór reguł, według których zapisuje się liczby.
Takie systemy można podzielić na pozycyjne i niepozycyjne.

### Systemy niepozycyjne (dodawanie i odejmowanie symboli)

W systemach **niepozycyjnych** wartość symbolu nie zależy od wagi pozycji. Przykładem jest system rzymski – `I = 1`, `V = 5`, `X = 10`, `L = 50`, `C = 100`, `D = 500`, `M = 1000`.
Liczba `CXXIII` to `100 + 10 + 10 + 1 + 1 + 1 = 123`. System rzymski korzysta także z odejmowania, np. `IV = 5 - 1 = 4`.

### Systemy pozycyjne (znaczenie pozycji cyfry)

W systemie pozycyjnym każda pozycja ma swoją **wagę**, która wpływa na
zapisaną na tej pozycji cyfrę.

#### System dziesiętny

Używamy go codziennie. Składa się z dziesięciu cyfr (od `0` do `9`), a waga każdej pozycji to kolejna potęga liczby `10`.

Przykład liczby 123:

- 1 stoi na miejscu setek ($10^2$);

- 2 stoi na miejscu dziesiątek ($10^1$);

- 3 stoi na miejscu jedności ($10^0$).

W zapisie matematycznym $123 = 10^2 \cdot 1 + 10^1 \cdot 2 + 10^0 \cdot 3$.

#### System dwójkowy

W układach cyfrowych dane reprezentuje się za pomocą dwóch stanów logicznych, umownie oznaczanych jako 0 i 1. W systemie dwójkowym wagą pozycji jest potęga liczby 2.

O systemie binarnym najlepiej myśleć jak o rozkładzie liczby na potęgi dwójki, które trzeba do siebie dodać.

Na przykład liczba `50` to `32 + 16 + 2`, czyli suma potęg $2^5$, $2^4$ i $2^1$.
Liczba `50` zapisana w systemie dziesiętnym ma w systemie dwójkowym postać `110010`.
`1` oznacza „bierzemy tę potęgę `2` do sumy”, a `0` oznacza „nie bierzemy”.

### Algorytm zamiany (metoda dzielenia przez 2)

Aby zamienić liczbę dziesiętną na binarną „ręcznie”, dzielimy ją przez 2 i zapisujemy reszty z dzielenia. Proces powtarzamy, aż wynik dzielenia wyniesie 0. Wynik czytamy od dołu (od ostatniej zapisanej reszty).

Przykład dla liczby 13:

- `13 // 2 = 6`, reszta **1**

- `6 // 2 = 3`, reszta **0**

- `3 // 2 = 1`, reszta **1**

- `1 // 2 = 0`, reszta **1**
Wynik: `1101`.

## Wspólne eksperymenty (20 minut)

### Krok 1: Zbieranie reszt do listy
Najpierw zapiszmy nasze reszty do listy, tak jak robiliśmy to na kartce. Przyjmujemy nieujemne liczby całkowite. Dla zera zapisujemy pojedynczy bit `0`.

```python
n = int(input("Podaj liczbę: "))
reszty = []
if n == 0:
    reszty.append(0)

while n > 0:
    reszta = n % 2
    reszty.append(reszta)
    n = n // 2

reszty.reverse()  # Pamiętasz? Wynik czytamy od dołu/od końca!
print("Lista bitów:", reszty)
```

### Dlaczego nie możemy po prostu dodawać?
Gdybyśmy napisali `wynik = wynik + reszta`, gdzie `wynik` jest liczbą (np. `0`), to dla liczby `13` (reszty: 1, 0, 1, 1) otrzymalibyśmy wynik `3`.

**Dlaczego?** Bo komputer wykonałby działanie matematyczne: $1 + 0 + 1 + 1 = 3$. My natomiast nie chcemy **sumy** tych liczb, ale ich **połączenia w napis** w odpowiedniej kolejności.

### Krok 2: Zamiana na napis (str)
Aby otrzymać czytelny wynik, musimy zamienić listę cyfr na napis:

```python
tekst = ""
for bit in reszty:
    tekst = tekst + str(bit)
print("Postać binarna:", tekst)
```

!!! tip "Krótszy kod"
    Zamiast listy możemy w każdej iteracji pętli dodawać resztę bezpośrednio do napisu (przed pętlą ustaw `wynik = ""`):
    `wynik = str(reszta) + wynik`. Zauważ, że dodajemy `str(reszta)` na **początek**, co daje cyfry we właściwej kolejności. Dla zera ustaw osobno `wynik = "0"`.

System szesnastkowy to system, w którym podstawą jest liczba **16**. Ponieważ zabrakło nam pojedynczych cyfr, po `9` używamy liter: **A** (10), **B** (11), **C** (12), **D** (13), **E** (14) oraz **F** (15).

**Gdzie go stosujemy?**

*   **Kolory na stronach WWW (HEX)**: Zapis typu `#FF0000` to nic innego jak trzy liczby szesnastkowe określające jasność barwy czerwonej, zielonej i niebieskiej.

*   **Adresy fizyczne urządzeń (MAC)**: Adresy MAC interfejsów sieciowych często przedstawia się w zapisie szesnastkowym, np. `00:1A:2B:3C:4D:5E`.

### Wyzwanie

Wybierzcie dowolną trzycyfrową liczbę i zapiszcie ją w systemie szesnastkowym. Następnie przekażcie zapis sąsiadowi z ławki i spróbujcie nawzajem odczytać swoje liczby. Kto jako pierwszy poprawnie przeliczy liczbę z powrotem na system dziesiętny? Zmiana systemu liczbowego nie jest szyfrowaniem.

## Zadania do rozwiązania (50 minut)

1. **Wypisywacz binarny**: Napisz program, który wczyta nieujemne liczby całkowite `a` i `b` i wypisze ich zapis w systemie binarnym.
2. **Suma w systemie dwójkowym**: Napisz program, który wczyta nieujemne liczby całkowite `a` i `b` i wypisze ich sumę w systemie binarnym.
3. **Zapis szesnastkowy**: Napisz program, który wczyta nieujemną liczbę całkowitą w systemie dziesiętnym i wypisze jej zapis w systemie szesnastkowym.

!!! tip "Wskazówka"
    Wykorzystaj kod zamieniający zapis liczby na system dwójkowy, ale dziel przez 16. Reszty 10–15 zamieniaj na litery A–F, np. za pomocą `cyfry = "0123456789ABCDEF"` i `cyfry[reszta]`.

4. **Szesnastkowe kolory**: Wypisz zapisy szesnastkowe dla liczb od 0 do 255.
5. **Potęga dwójki**: Napisz program, który sprawdzi, czy podana liczba jest potęgą dwójki (liczby te w systemie binarnym mają tylko jedną jedynkę).
