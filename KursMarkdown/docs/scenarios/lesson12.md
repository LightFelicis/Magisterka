# Własności liczbowe – podzielność, suma cyfr, iloczyn cyfr

## Wymagana wiedza

- Pętle `while` oraz `for`
- Operatory `%` (modulo) oraz `//` (dzielenie całkowite)

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 1) Formułuje problem w postaci specyfikacji i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów. | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne, pętle. |

## Wstęp teoretyczny (15 minut)

Aby wyciągnąć ostatnią cyfrę liczby, używamy operacji `n % 10`. 
Aby "pozbyć się" ostatniej cyfry, używamy operacji dzielenia całkowitego `n // 10`.

Przykład dla liczby 123:
- `123 % 10 = 3`
- `123 // 10 = 12`

## Wspólne eksperymenty (15 minut)

Przeanalizujmy algorytm sumujący cyfry liczby:

```python
n = int(input("Podaj liczbę: "))
suma = 0
while n > 0:
    cyfra = n % 10
    suma = suma + cyfra
    n = n // 10
print("Suma cyfr wynosi:", suma)
```

Algorytm "obcina" kolejne cyfry, dodając je do wyniku.

Przeanalizujmy algorym dla `n = 123`:

W pierwszym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `3`.
Suma zostanie zwiększona o `3`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `12`.

W kolejnym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `2`.
Suma zostanie zwiększona o `2`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `1`.

W kolejnym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `1`.
Suma zostanie zwiększona o `1`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `0`.

Po zakończeniu pętli w zmiennej `suma` znajduje się wartość `6`.

## Zadania do rozwiązania (60 minut)

1. **Iloczyn cyfr**: Zmodyfikuj powyższy program tak, aby obliczał iloczyn cyfr podanej liczby.

!!! Wskazówka
    Pamiętaj, że dla iloczynu zmienna początkowa powinna wynosić 1, a nie 0!

2. **Liczba cyfr**: Napisz program, który policzy, ile cyfr ma podana liczba.

!!! Wskazówka
    Przy każdym obrocie pętli zwiększaj zmienną pomocniczą `ile_cyfr` o 1.

3. **Podzielność**: Napisz program, który wczyta liczbę i sprawdzi, czy jest ona podzielna przez sumę swoich cyfr.

!!! Wskazówka
    Najpierw oblicz sumę cyfr, a później za pomocą polecenia `%` sprawdź, czy liczba jest podzielna przez `suma`.
    Uwaga, wartość `n` będzie równa `0` na koniec pętli! Zapisz sobie jej początkową wartość w zmiennej.

4. **Suma parzystych cyfr**: Napisz program, który obliczy sumę tylko tych cyfr liczby, które są parzyste.
