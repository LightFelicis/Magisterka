# Czym jest sztuczna inteligencja? Implementujemy uproszczone "drzewo decyzyjne"

## Wymagana wiedza

- Instrukcje warunkowe `if-elif-else`

## Wstęp teoretyczny (20 minut)

Sztuczna inteligencja (AI) to dziedzina informatyki zajmująca się tworzeniem programów, które potrafią wykonywać zadania wymagające "ludzkiej" inteligencji.
Jednym z najprostszych modeli AI jest **drzewo decyzyjne** – seria pytań, które prowadzą do wyniku (decyzji).

**Przykłady z życia wzięte:**
*   **Bankowość**: Decyzja o przyznaniu pożyczki (Pytania o zarobki, wiek, historię spłat).
*   **Medycyna**: Wstępna diagnoza choroby (np. czy pacjent ma gorączkę? czy ma wysypkę? -> jeśli tak, to może być ospa).

## Wspólne eksperymenty (15 minut)

Stwórzmy system klasyfikujący zwierzęta:

```python
print("Odpowiedz na pytania (tak/nie):")
czy_ma_piora = input("Czy ma pióra? ")

if czy_ma_piora == "tak":
    czy_lata = input("Czy lata? ")
    if czy_lata == "tak":
        print("To prawdopodobnie wróbel!")
    else:
        print("To prawdopodobnie struś!")
else:
    print("To prawdopodobnie ssak lub gad.")
```

## Zadania do rozwiązania (10 minut)

1. **Akinator**: Rozbuduj drzewo decyzyjne tak, aby potrafiło rozpoznać co najmniej 5 różnych zwierząt lub postaci z gier.
2. **Diagnoza komputera**: Napisz program, który pyta o objawy (np. "czy ekran działa?", "czy słychać wiatrak?") i sugeruje rozwiązanie problemu z komputerem.

