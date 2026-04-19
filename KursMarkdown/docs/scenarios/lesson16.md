# Porządkowanie zbioru – sortowanie przez wybieranie

## Wymagana wiedza

- Listy
- Wyszukiwanie minimum (z poprzedniej lekcji)
- Zamiana wartości między zmiennymi

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 2) Stosuje algorytmy sortowania. |

## Wstęp teoretyczny (15 minut)

Sortowanie przez wybieranie (Selection Sort) to intuicyjny algorytm, który dzieli naszą listę na dwie części: **już posortowaną** (na początku) oraz **jeszcze nieposortowaną**.

### Jak to działa krok po kroku?
1.  **Szukanie**: Przeszukujemy nieposortowaną część listy, aby znaleźć w niej najmniejszy element.
2.  **Zamiana**: Gdy znajdziemy najmniejszą liczbę, zamieniamy ją miejscami z pierwszym elementem części nieposortowanej.
3.  **Postęp**: Teraz nasza "posortowana część" powiększyła się o jeden element. Przesuwamy się o jedną pozycję w prawo i powtarzamy cały proces dla reszty liczb.
4.  **Koniec**: Robimy tak długo, aż zostanie nam tylko jeden (ostatni) element – on siłą rzeczy musi być już największy i na właściwym miejscu.

### Przykład z życia: Sortowanie kart
Wyobraź sobie, że trzymasz w ręku wachlarz nieuporządkowanych kart (np. od 2 do Asa). Chcesz je ułożyć od najmniejszej do największej:
1.  Przeglądasz wszystkie karty w ręku i szukasz tej najniższej (np. Dwójki).
2.  Wyciągasz ją i przekładasz na sam początek (lewa strona).
3.  Teraz szukasz najniższej karty wśród tych, które pozostały po prawej stronie od Dwójki.
4.  Znajdujesz np. Trójkę i kładziesz ją zaraz za Dwójką.
5.  Powtarzasz to, aż w prawej ręce nie zostanie Ci żadna karta.

**Dlaczego "przez wybieranie"?** Bo w każdym kroku algorytm "wybiera" konkretną wartość – tę najmniejszą z dostępnych – i kładzie ją na właściwe miejsce.

## Wizualizacja (unplugged)
Uczniowie dostają karty z liczbami. Muszą ustawić się w szeregu i posortować zgodnie z algorytmem.
1. Nauczyciel wskazuje pierwszą osobę w szeregu jako "miejsce docelowe".
2. Klasa szuka osoby z najniższym numerem w pozostałej części szeregu.
3. Wybrana osoba zamienia się miejscami z osobą na "miejscu docelowym".

## Wspólne eksperymenty (20 minut)

Przeanalizujmy kod implementujący sortowanie przez wybieranie. Zwróć uwagę na dwie pętle – zewnętrzna wskazuje miejsce, na które szukamy najmniejszego elementu, a wewnętrzna przeszukuje pozostałą, nieposortowaną część listy.

```python
lista = [64, 25, 12, 22, 11]

for i in range(len(lista)):
    # Zakładamy, że pierwszy element nieposortowanej części jest najmniejszy
    min_idx = i
    for j in range(i + 1, len(lista)):
        if lista[j] < lista[min_idx]:
            min_idx = j
            
    # Zamiana miejscami: najmniejszy znaleziony trafia na i-tą pozycję
    lista[i], lista[min_idx] = lista[min_idx], lista[i]

print("Posortowana lista:", lista)
```

## Zadania do rozwiązania (45 minut)

1. **Sortowanie malejące**: Zmodyfikuj powyższy kod tak, aby liczby były układane od największej do najmniejszej (odwrócenie kierunku sortowania).
2. **Mediana**: Napisz program, który wczyta od użytkownika 5 liczb, posortuje je, a następnie wypisze element środkowy (medianę).

!!! Wskazówka
    Skorzystaj z polecenia `len()` by odczytać długość tablicy i obliczyć środkowy indeks.

3. **Sortowanie nazwisk**: Stwórz listę kilku imion i spróbuj je posortować alfabetycznie. Czy Python radzi sobie z porównywaniem słów (operator `<`) tak samo łatwo jak z liczbami?
4. **Sortowanie par**: Masz listę wyników biegaczy: `wyniki = [[12.5, "Jan"], [11.2, "Ola"], [13.1, "Piotr"]]`. Posortuj ją według czasu (pierwszy element w każdej parze). Zauważ, że Python przy zamianie `lista[i], lista[min_idx]` przenosi całe "paczki" danych (liczbę wraz z imieniem).
