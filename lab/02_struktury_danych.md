# Struktury danych

# Typy
lista mutowalna, typ *list*
```python
lista = [1, 2, 3, 4, 5, 1, 1]
print(lista)
print(lista[1])
lista[5] = 77
del lista[6]
lista.append("string")
print(lista)
```

krotka niemutowalna, typ *tuple*
```python
krotka = ("jeden", "dwa", "trzy")
print(krotka)
nowa_struktura = krotka + (1, 2)
print(nowa_struktura)
```

slownik, typ *dict*
```python
ksiazka = {
    'Nowak': 100,
    'Kowalski': 200,
    'Wisniewski': 300,
    'Wozniak':400
}
print(f"Książka zawiera {ksiazka}")
ksiazka['Kowalski'] = 500
print(f"nr Nowak {ksiazka['Nowak']} oraz nr Kowalski {ksiazka['Kowalski']}")
```

set nie zawiera duplikatów, typ *set*
```python
wartosci = {1, 2, 3, 1, 2, 3, 1, "dwa", "dwa"}
print(f"w moim secie są {wartosci}")
wartosci = {True, True, True, False, False, True}
print(f"w moim secie są {wartosci}")
```

## Definicje 📝
| lists               | tuples              | sets          | dictionaries      |
|---------------------|---------------------|---------------|-------------------|
| ordered             | ordered             | unordered     | unordered         |
| mutable             | immutable           | mutable       | mutable           |
| duplicates  allowed | duplicates  allowed | no duplicates | no duplicate keys |
| [ value ]           | ( value )           | { value }     | { key : value }   |
* więcej na temat struktur danych https://docs.python.org/pl/3/tutorial/datastructures.html
* porównanie https://www.educative.io/answers/list-vs-tuple-vs-set-vs-dictionary-in-python

## Pytania rekrutacyjne ❓
1. *Czym się różni lista od tuple?*
Tuple są immutable przez co nie możemy modyfikować ani usuwać raz utworzonych danych, a listy są mutable czyli możemy edytować, usuwać i dodawać nowe elementy

## Zadania ✏️
1. Stwórz listę w której będą wyniki dużego lotka, znajdź na jakim indeksie znajduje się wybrana dowolna liczba z losowania
2. Stwórz słownik *schroniska* w którym będziesz przechowywał informację o ilości schronisk w danym mieście dla miast (kluczy) Kraków, Warszawa i Poznań
    * podnieś liczbę schronisk w Krakowie i Poznaniu o 1, a w Warszawie o 2
    * dodaj nowe miasto Rzeszów z liczbą 3 schronisk
    * korzystając z funkcji *input* poproś użytkownika o miasto (klucz) dla którego wyświetlona zostanie informacja o liczbie schronisk
3. Stwórz słownik w którym kluczami będą trzy ostatnie daty w formacie 'YYYY-MM-DD', a wartościami wyniki dużego lotka w formie krotki