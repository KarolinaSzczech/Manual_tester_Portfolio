# Raport z testów na stronie https://noclegi.pl

Przedmiotem testów jest formularz do wyszukiwania noclegów na stronie https://noclegi.pl

**Do testów użyto:**

_**Desktop:**_

 OS: Windows 10 PRO
 - Przeglądarka: Chrome Wersja 107.0.5304.108 (64-bitowa)
 - Przeglądarka: Firefox Wersja 109.0 (64 bity)
 - Przeglądarka: Firefox Developer Edition Wersja 108.0b6 (64 bity)
 - Przeglądarka: Microsoft Edge Wersja 107.0.1418.56 (Oficjalna kompilacja) (wersja 64-bitowa)
 - Przeglądarka: Opera Wersja 94.0.4606.37 (wersja 64-bitowa)

**Czas testów:**
 - Testowanie strony https://noclegi.pl  - 4h
 - Na przygotowanie raportu około - 6h


### Weryfikacja ustawień docelowego miejsca podróży ### 

| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 | Wysłanie formularza z pustym docelowym miejscem podróży.|	Pojawia się komunikat walidacyjny lub nie jest możliwe wysłanie formularza.| Walidacja działa. Nie jest możliwe wysłanie pustego formularza. Po kliknięciu przycisku „Szukaj”  pod polem wyboru miejsca podróży rozwija się lista pięciu popularnych miejscowości: Zakopane, Kraków, Gdańsk, Wrocław, Sopot.|
|2 | Wysłanie formularza z wybranym docelowym miejscem podróży.| Wyszukiwarka przedstawia wyniki wybranego przez nas miejsca.| Wyszukiwarka działa poprawnie.|
|3 | Weryfikacja użycia polskich znaków np.: przez wpisanie miejscowości „Kolobrzeg” zamiast Kołobrzeg, lub „Poznan” zamiast Poznań.| Wyszukiwarka podpowiada prawidłową nazwę miejsca docelowego. | Wyszukiwarka działa poprawnie.|
|4 | Użycie klawisza Enter dla potwierdzenia wyboru.| Kursor przechodzi do kolejnego pola lub wysyła formularz.| Działa poprawnie.|

## Weryfikacja funkcjonowania działania kalendarza do zarezerwowania pobytu ##
 
| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 |Wybór daty przybycia wcześniejszej niż dzisiejsza.|Wybór niemożliwy, brak akceptacji daty. |Walidacja działa. Nie jest możliwe wybranie daty przybycia wcześniejszej niż dzisiejsza.|
|2 |Wybór daty dzisiejszej jako daty przybycia.|Wybór możliwy do zaakceptowania. |Dzała prawidłowo. Możliwy wybór daty dzisiejszej jako daty przybycia.|
|3 |Wybór tej samej daty dla daty przyjazdu i wyjazdu.|Wybór niemożliwy do wyboru/ do zaakceptowania.|Wynik prawidłowy. W przypadków próby ustawienia jednakowej daty wyjazdu i przyjazdu aplikacja ustawia datę wyjazdu na dzień następny po dacie przyjazdu.|
|4 |Wybór daty wyjazdu wcześniejszej niż data przyjazdu.|Wybór niemożliwy do zaakceptowania.|Działa prawidłowo. Nie jest możliwe wybranie daty wyjazdu wcześniejszej niż data przyjazdu. Jednakże w takim przypadku aplikacja przesuwa termin rezerwacji w ten sposób, że wybrana data wyjazdu staje się datą przyjazdu. Ustawiając datę przyjazdu na 26 stycznia i chcąc ustawić datę wyjazdu na 25 stycznia aplikacja przesuwa rezerwację w ten sposób, że ustawia 24 stycznia dniem przyjazdu, a 25 dniem wyjazdu.|
|5 |Wybór daty bieżącej jako daty przyjazdu i daty z nieodległej przyszłości jako daty wyjazdu (do 31 dni).|Wybór możliwy do zaakceptowania. |Działa prawidłowo. |
|6 |Wybór długiego pobytu przekraczającego 31 dni. |Wybór niemożliwy do zaakceptowania.|Walidacja działa. Nie jest możliwe zarezerwowania pobytu na czas dłuższy niż 31 noclegów.|
|7 |Wybór daty przyjazdu z bliskiej przyszłości. |Wybór możliwy do zaakceptowania |Wynik prawidłowy. Maksymalny termin możliwy do wyboru jako dzień przybycia to rok od daty dzisiejszej.|
|8 |Wybór dat z dalekiej przyszłości (rok lub więcej od dziś). |Nie można zarezerwować pobytu z rocznym i większym wyprzedzeniem. | Działa poprawnie. Najodleglejsza opcja to ustalenie daty powrotu dokładnie na rok do przodu od daty dzisiejszej. |


### Weryfikacja wieku dzieci ###

Zweryfikowano, że wartości wpisywane za pomocą klawiatury pozwalają na wpisywanie wieku jako liczby niecałkowitej z wartością po przecinku lub kropce.

Wartość ustawiana za pomocą przycisku w górę i w dół wyświetlają się jako liczby całkowite.
- Zwiększanie i zmniejszanie wieku dzieci za pomocą przycisków góra dół - działa poprawnie

Przycisk „Dzieci są w tym samym wieku” - działa poprawnie. Wiek waliduje na takich samych zasadach  jak w przypadku ustawiania wieku dla każdego dziecka z osobna. 



| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 |Wysłanie pustego formularza|Walidacja działa. Wyświetla się informacja o wymaganej wartości.|Działa| 
|2 |Ustawienie wieku za pomocą klawiatury jako liczby całkowitej. |Wartość możliwa do ustawienia. |Działa|
|3 |Wprowadzenie wieku jako liczby niecałkowitej.|Wartość niemożliwa do ustawienia. Dla systemu rezerwacji pobytu wystarczającym jest ustawienie wieku dziecka jako liczby całkowitej.| Ustawiane wieku za pomocą przycisku w górę i w dół jako liczy niecałkowitej nie jest możliwe. Wprowadznie liczby niecałkowitej za pomocą klawiatury jest możliwe. 
|4 |Wprowadzenie wartości mniejszej niż 0 | Wartość niemożliwa do ustawienia.| Działa.|
|5 |Wprowadzenie wartości 18. |Nie jest możliwe ustawienie dla dziecka wieku 18 lat.| Działa.|
|6 |Wprowadzenie w pole wiek liter lub znaków specjalnych. | Brak możliwości wprowadzenia. | Działa.|

### Analiza wprowadzenia wartości brzegowych ###

| No. |	Przypadek testowy | Wiek | Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|---|--------|---------|
|1|Niepoprawna wartość brzegowa |-1 |Wartość niepoprawna. Walidacja działa |Walidacja działa. Wiek nie zostaje zaakceptowany.|
|2|Poprawna wartość brzegowa | 0|Wartość poprawna. Przyjęcie wieku. | Wiek zostaje zaakceptowany.|
|3|Poprawna wartość brzegowa |0,5|Wartość poprawna. Przyjęcie wieku. | Wiek zostaje zakceptowany. Po zwinięciu i ponownym rozwinięciu pola z wiekiem dzieci wartość 0,5 zostaje zamieniona na 0.|
|4|Poprawna wartość brzegowa |1|Wartość poprawna. Przyjęcie wieku. | Wiek zostaje zakceptowany.|
|5|Poprawna wartość brzegowa |17.9|Wartość poprawna. Przyjęcie wieku |Wiek zostaje zakceptowany. Po zwinięciu i ponownym rozwinięciu pola z wiekiem dzieci wartość 17,9 zostaje zamieniona na 17. |
|6|Poprawna wartość brzegowa |17.99 |Wartość poprawna. Przyjęcie wieku |Po zwinięciu i ponownym rozwinięciu pola z wiekiem dzieci wartość 17,99 zostaje zamieniona na 17. |
|7|Niepoprawna wartość brzegowa |18 |Wartość niepoprawna. Walidacja działa |Walidacja działa. Wiek nie zostaje zaakceptowany. |
|8|Niepoprawna wartość brzegowa |18.1 |Wartość niepoprawna. Walidacja działa |Walidacja działa. Wiek nie zostaje zaakceptowany. |
|9|Nieoprawna wartość brzegowa |19 |Wartość niepoprawna. Walidacja działa |Walidacja działa. Wiek nie zostaje zaakceptowany. |

![Screen_2 - wiek dzieci](https://user-images.githubusercontent.com/118970045/214585190-730f37ce-fcdf-4d0f-95c8-86080533db7d.png)


### Konfiguracja ilości pokoi, ilości osób dorosłych i dzieci  ###

 - Konfiguracja ilości pokoi, ilości osób dorosłych i dzieci odbywa się przez wybór z listy odpowiedniej pozycji lub z użyciem klawiatury - **działa poprawnie**.
 - W przypadku wybrania z opcji "więcej miż 30 osób dorosłych" otrzymujemy komunikat z prośbą o kontakt z działem obsługi klienta. 


 ### Wykryte defekty ###
 
 ### ID-001 literówka w słowie oragnizowania ###
 
 
Priorytet: Niski

Kroki:

1. Wejdź na stronę https://noclegi.pl
2. Z paska z konfiguracją ilości pokoi, ilości osób dorosłych i dzieci rozwiń listę osób dorosłych
3. Z listy osób dorosłych wybierz opcję więcej niż 30

**Rezultat:** _Pojawia się komunikat o z próśbą o kontakt z działem obsługi klienta. W słowie "orgnizowania" brakuje litery a po literze g._

![Screen 1 - literówka w słowie orgaznizowania](https://user-images.githubusercontent.com/118970045/214586622-1f5de658-198c-4b69-a7fb-e378fed19e22.png)

 
 
