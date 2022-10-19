# Instrukcje

# Typy
instrukcja warunkowa *if*
```python
wiek = 23
if wiek >= 18:
    print("pełnoletnia")
else:
    print("niepełnoletnia")

x = int(input())
if x > 10:
    print("x większy niż 10")
elif x == 3:
    print("x jest równy 3")
elif x == 7:
    print("x jest równy 7")
else:
    print(f"inna wartosc, x = {x}")
```

pętla *while*
```python
i = 0
while i < 5:
    i += 1
    print(f"wypisana liczba to {i}")
```

pętla *for*
```python
for y in range(4):
    print(f"for i = {y}")

for imie in ["Adrian", "Bartosz", "Celina", "Dagmara"]:
    print(f"Imie to {imie}")
    if imie == "Bartosz":
        print(f"Dodatkowy warunek został spełniony dla Bartosza")
```

wyjście z pętli *break*
```python
while True:
    x = input()
    if x == "finish":
        break
```

kontynuacja pętli *continue*
```python
while True:
    x = input()
    if x == "skip":
        continue
    print(f"input {x}")
```

| operator | odpowiednik w Pythonie |
|-|-|
| && | and |
| \|\| | or |
| ! | not |

## Definicje 📝
* z jednym argumentem funkcja *range()* generuje listę liczb całkowitych od zera do wartości argumentu (bez niej samej), z dwoma argumentami pierwszy uznawany jest za dolną granicę, z trzema trzeci argument jest krokiem

## Zadania ✏️
1. Napisz program stwierdzający czy liczba podana przez użytkownika jest parzysta czy nieparzysta
2. Za pomocą pętli z każdą iteracją odcinaj pierwszy znak słowa "nabuchodonozor" aż wypisany zostanie pusty string
3. Wypisz za pomocą pętli wszystkie liczby do 1000 podzielne przez 5. Przekształć program tak aby górną granicę oraz dzielnik podawał użytkownik.
4. Sprawdź za pomocą pętli *for* i instrukcji *if* czy wszystkie elementy **lista1 = [1, 2, 3]** znajdują się w **lista2 = [1, 4, 2, 5, 3, 6]**