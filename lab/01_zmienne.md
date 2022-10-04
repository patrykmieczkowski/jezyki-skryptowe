# Zmienne

## Typy 💻
liczby całkowite, typ *int*
```python
zmienna = 3
print(zmienna)
print(type(zmienna))
```

liczby rzeczywiste, typ *float*
```python
liczba_pi = 3.14
liczba = float(5)
wynik = liczba_pi + liczba
print(wynik)
```

łańcuch znaków, typ *str*
```python
imie = "Adam"
nazwisko = 'Nowak'
imie_i_nazwisko = imie + " " + nazwisko
print(f"{imie} {nazwisko}")
print(len(imie_i_nazwisko))
print(f"Czy jest cyfrą? {imie.isdigit()}")
```

wartość logiczna, typ *bool*
```python
czy_prawda = True
print(czy_prawda)
print("slowo" != "slowo")
```

liczby zespolone, typ *complex*
```python
c = 1 + 3j
```

multiple assignment
```python
drzewo, wiek, czy_najstarsze = "dab", 400, True
print("Drzewo {} ma {} lat, czy jest najstarsze? {}".format(drzewo, wiek, czy_najstarsze))
```

typowanie dynamiczne
```python
x = 1
print(f"x = {x}, typ {type(x)}")
x = "Dwa"
print(f"x = {x}, typ {type(x)}")
x = False
print(f"x = {x}, typ {type(x)}")
```

## Definicje 📝
* konwencja nazewnictwa zmiennych https://www.w3schools.com/python/gloss_python_variable_names.asp

## Pytania rekrutacyjne ❓
1. *Co oznacza to, że python jest językiem typowanym dynamicznie?*  
Typowanie dynamiczne jest to przypisywanie typów do zmiennych dopiero w trakcie działania programu. Typ wynika z wartości jaką dana zmienna przechowuje i może się zmieniać w różnych momentach wykonywania. Zastanowić się nad wadą i zaletą.
2. *Kiedy należy używać *"double quotes"*, a kiedy *'single quotes'*?*  
Zgodnie z dokumentacją PEP8 są one w zasadzie wymienne. Zaleca wybrać jedno podejście i trzymać się go lub dostosować do istniejących zasad w projekcie. Najczęściej używamy " " przy stringach, a ' ' przy kluczach i symbolach.

## Zadania ✏️
1. Wypisz liczbę PI z dokładnością do 10 miejsc po przecinku korzystając z pythonowej stałej
2. Stwórz 3 zmienne o 3 różnych typach za i wypisz je używając tylko jednego wywołania funkcji *print()*
3. Wypisz zmienną "Kleopatra" małymi i wielkimi literami wraz z jej typem używając tylko jednego wywołania funkcji *print()*
4. Dodatkowe ćwiczenia https://www.w3schools.com/python/exercise.asp?filename=exercise_variables1