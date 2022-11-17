# Wyrażenia regularne
Wyrażenia regularne (nazywane **regex** od angielskiej nazwy **regular expression**) to narzędzia, które służą do dopasowywania wzorców, czyli rozpoznawania zgodności z zadanym schematem.  Za ich pomocą można określić z czego ma się dokładnie składać np. adres e-mail.
Python posiada dedykowany moduł ```re``` do ich obsługi

## Funkcja search
Funkcja ```re.search(pattern, string)``` zwraca zgodny z wzorcem łańcuch znakowy, a jest nim obiekt *re.Match* lub *None*.
Najprostsze wyrażenie regularne to po prostu tekst, np. ```spinacz```, który zwróci match'a na każdy tekst zawierający ciąg znaków *spinacz*. Aby wydobyć z obiektu *Match* napis posługujemy się metodą ```group()```
```python
import re
text = "Tekst na wejściu"
x = re.search("spinacz", text) 
print(f"output x: {x}")

if x:
    wartosc = x.group()
    print(f"wartosc: {wartosc}")
```

## Funkcja findall
Aby znaleźć wszystkie wystąpienia wzorca możemy użyć ```findall()```. Jeśli wzorzec zostanie znaleziony, zostanie zwrócona lista z dopasowanymi, niezachodzącymi na siebie, ciągami znaków. Jeśli nie, zostanie zwrócona pusta lista.

```python
wynik = re.findall(r'spi', text)
if len(wynik) > 0:
    print(f'znaleziono {wynik}')
else:
    print(f'{wynik} nie znaleziono')
```

## Kwantyfikatory
Dotyczą elementu, który znajduje się po jego lewej stronie  
```a*spinacz``` * zero lub więcej  
```a+spinacz``` + jedno lub więcej  
```a?spinacz``` ? zero lub jedno  
```a{n}spinacz``` {n} dokładna ilość wystąpień
```a{min, max}``` zakres liczby znaków

## Zakresy i grupy przechwytujące
Zakres definiujemy w nawiasach kwadratowych, na dwa sposoby: można wymienić wszystkie możliwe znaki lub wprowadzić przedział  
```[qwerty]``` jedna z liter: q, w, e, r, t lub y  
```[a-zA-Z]``` jedna z liter małych lub dużych od a do Z  
```[a-d2-4]``` jedna z litera od a do d lub cyfra od 2 do 4  

Grupy służą nam do tworzenia bardziej skomplikowanych struktur (np. mamy wyrażenie regularne które dopasowuje wielokrotnie powtarzany fragment). Do oznaczania grup używamy zwykłych nawiasów.
```a(bcd)*``` litera a oraz ciąg bcd zero lub więcej razy
```a(b(cd)?)+``` litera a, a następnie jedno lub więcej powtórzeń b lub bcd

## Znaki specjalne
```^``` znak grotu oznacza, że tekst musi być na początku lini  
```.*?``` dopasowanie niezachłanne to dopasowanie jak najmniejszej liczby znaków  
```.``` kropka dopasowuje dowolny znak  
Aby kropka była traktowana jako kropka należy poprzedzić ją backslashem: ```\``` To właśnie on mówi o tym, że kolejny znak należy traktować na specjalnych warunkach.  
Znak ```r``` przed ' wyłącza zwykłe formatujące działanie \ przez co nie musimy używać dwukrotnego backslasha. Dołączanie r przed każdym wyrażeniem jest powszechnie rekomendowane jako dobra praktyka programistyczna.

## Flagi
| Flaga         | Opis
| ------------- | ------------------------- |
| re.IGNORECASE | ignoruje wielkość znaków |
| re.MULTILINE  | wyszukanie w wielu liniach |
| re.DOTALL     | dopasowuje dowolny znak, nawet jeżeli jest to znak nowej linii |

# Materiały
* https://docs.python.org/3/library/re.html
* https://kobietydokodu.pl/4-wyrazenia-regularne/
* https://miroslawmamczur.pl/wyrazenia-regularne-czym-sa-i-jak-pisac-wlasne-regexy/
* https://regex101.com/

# Zadania
1. Napisz regułę pozwalającą na dopasowanie adresu e-mail
2. Napisz regułę pozwalającą na dopasowanie numeru telefonu
3. Sprawdź format numeru domu - poprawny to **numer\numer** (np. 50/2A, 100/3, 4/1), a błędny AB/2, ads/ew
4. Napisz program, który będzie zwracał informację czy hasło jest silne czy słabe w zależności od wpisanego hasła poprzez *input()*