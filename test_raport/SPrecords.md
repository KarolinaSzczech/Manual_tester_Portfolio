 # Raport z testów  strony https://sprecords.pl/ # 

**Do testów użyto:**

_**Desktop:**_

 - OS: Windows 10 PRO
 - Browser: Chrome version 107.0.5304.108 (Oficjalna wersja) (64-bitowa)
 - Browser: Firefox Developer Edition Wersja 108.0b6
 - Browser: Microsoft Edge Wersja 107.0.1418.56 (Oficjalna kompilacja) (wersja 64-bitowa)
 - Browser: Opera Wersja Wersja:94.0.4606.37  (wersja 64-bitowa)

_**Smartphone:**_

Device: POCO X3 NFC
Android wersja MIU 13.0.3
Browser Chrome version 107.0.5304.105

**Czas testów:**
 - Testowanie strony https://sprecords.pl/ 4h
 - Na przygotowanie raportu około 6h

## Przetestowano: ##

### REJESTRACJA: ###

**Wysłanie pustego formularza** - nie działa poprawnie

_**WYKRYTE DEFEKTY:**_

**ID-001 Formularz rejestracji waliduje tylko po jednym polu na raz** 

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Nie wypełniaj żadnego pola 
4. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się tylko przy polu Imię_

5. Wypełnij pole Imię
6. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się tylko przy polu Nazwisko_

7. Wypełnij pola: Imię i Nazwisko
8. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się tylko przy polu E-mail_

10. Wypełnij pola: Imię, Nazwisko i E-mail
11. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się tylko przy polu Hasło_

![Screen_1](https://user-images.githubusercontent.com/118970045/212694757-eb7dcc2f-ce01-4d4a-9497-89a3287f8424.png)
![Screen 2](https://user-images.githubusercontent.com/118970045/212694754-4ef4732d-42bb-42e4-8d76-d7f930bf927f.png)
![screen- brak emaila](https://user-images.githubusercontent.com/118970045/212695058-8619899d-b272-46ae-90dc-c41acb628775.png)
![screen - bez hasla](https://user-images.githubusercontent.com/118970045/212694750-5623b4fc-51a4-434d-855d-f1f2a10a937c.png)

**Oczekiwane zachowanie:** _Komunikat "Wypełnij pole" powinien pojawić się przy wszystkich niewypełnionych polach._


### Rejestracja konta z użyciem błędnego adresu e-mail ###
Walidacja działa poprawnie

### Rejestracja konta z użyciem długiego adresu e-mail ###

Walidacja działa poprawnie, pojawia się komunikat "Pole email jest zbyt długie (maks. 128 znaków)."


### Weryfikacja użycia krótkiego hasła ###

Weryfikacja walidacji hasła nie działa poprawnie
_Na stronie brak informacji o wymaganiach hasła. Żeby utworzyć konto wystarczy wpisać 5 znaków, nie muszą spełniać wymagań typu: wielka litera, cyfra, znak specjalny. Hasłem może być pięć jednakowych małych liter np: aaaaa_ 
Weryfikacja użycia krótkiego hasła, krótszego niż 5 znaków,  działa poprawnie 

### Weryfikacja użycia długiego hasła ###
Walidacja nie działa poprawnie

_**WYKRYTE DEFEKTY:**_

**ID-002 Formularz rejestracji nie waliduje za długiego hasła**

_Możliwe jest utworzenie konta z użyciem bardzo długiego hasła ale nie jest możliwe poźniejsze zalogowanie się na konto z użyciem tego hasła._

Priorytet: Wysoki

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Wypełnij poprawnie pola: Imię, Nazwisko, E-mail
4. Użyj bardzo długiego hasła wypełniając pole Hasło. Jako hasło ja użyłam słowa: Wiaderkoooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo
5. Naciśnij Zapisz

_**Rezultat:** Konto zostało utworzone poprawnie, użytkownik zostaje zalogowany na stronie._

Następnie

6. Wyloguj się z konta
7. Zaloguj się na konto przy użyciu wcześniejszych danych z użyciem ustawionego długiego hasła.

_**Rezultat:** Brak możliwości zalogowania się na utworzone konto. Pod polem hasło pojawia się komunikat Niepoprawny format._

![screen - brak możliwości zalogowania się](https://user-images.githubusercontent.com/118970045/212700822-c5640a56-8fe8-4410-860c-ea904b46fc1f.png)

**Oczekiwane zachowanie:** _Komunikat "Nieprawidłowy format" powinien pojawiać się na etapie rejestracji konta, a nie dopiero na etapie logowania._ 

### Rejestracja konta z użyciem poprawnych danych ###

Działa

### Rejestracja konta z wykorzystaniem poprzednio użytego adresu e-mail ###

Walidacja wcześniej użytego adresu e-mail nie zawsze działa poprawnie

_**WYKRYTE DEFEKTY**_

**ID-003 Brak czytelnego komunikatu o użyciu istniejącego w bazie adresu e-mail** 

Priorytet: Średni

Kroki:
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Wypełnij poprawnie pola: Imię, Nazwisko, E-mail
Imię :anna 
Nazwisko: nowak 
E-mail: a@wp.pl 
Hasło: Wiaderko
4. Naciśnij Zapisz

_**Rezultat:**  Czasami pojawia się komunikat pod polem e-mail, że istnieje on w bazie, a czasami nad nagłówkiem strony pojawiają się dwie notyfikacje niezrozumiałe dla użytkownika._

Nie udało mi się ustalić od czego zależy pojawianie się prawidłowego komunikatu, a od czego notyfikacji nad nagłówkiem strony.

![screen 10 - błąd logowania](https://user-images.githubusercontent.com/118970045/212735939-851ef665-621b-427e-8db3-37cd9828b18b.png)

**Oczekiwane zachowanie:** _Za każdym razem powinien pojawiać się komunikat pod polem e-mail o tym, że wskazany e-mail już istnieje w bazie_ 


### LOGOWANIE: ###

### Logowanie poprawnymi danymi ### 
Działa

### Logowanie nieistniejącego użytkownika ### 
Walidacja działa poprawnie

### Logowanie z użyciem adresu e-mail innego użytkownika ### 
Walidacja działa poprawnie

### Logowanie z użyciem nieprawidłowego hasła ###
Walidacja działa poprawnie

Walidacja nie działa poprawnie

### Logowanie pustym formularzem ###
Walidacja nie działa poprawnie

_**WYKRYTE DEFEKTY:**_

**ID-004 Formularz logowania waliduje tylko po jednym polu na raz** 

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta
3. Nie wypełniaj żadnego pola 
4. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się tylko przy polu E-mail_

5. Wypełnij pole E-mail
6. Kliknij Zapisz

_**Rezultat:** Komunikat "Wypełnij pole" pojawia się przy polu Hasło_

![logowanie 1](https://user-images.githubusercontent.com/118970045/212708281-8e58c326-0202-412e-b7bb-b0f78eca194a.png)
![logowanie 2](https://user-images.githubusercontent.com/118970045/212708290-6ca1aa89-107e-45e6-a839-a02b5cfeb3d1.png)

**Oczekiwane zachowanie:** _Komunikat "Wypełnij pole" powinien pojawić od razu się przy wszystkich niewypełnionych polach, a nie pojedynczo._

### ZMIANA DANYCH, ZMIANA HASŁA: ###

### Zmiana hasła na inne poprawne ### 

Zmiana hasła na inne poprawne, spełniające wymagania jak przy rejestracji konta - **działa** 
Jednakże mimo poprawnej zmiany hasła na stronie jest błąd.

_**WYKRYTE DEFEKTY:**_

**ID-005 Po zmianie hasła strona jest "ucięta"**

Priorytet: Niski

Kroki
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta i zaloguj się na konto
3. Wejdź w zakładkę moje dane
4. Uzupełnij pole hasło swoim aktualnym hasłem
5. Uzupełnij pole nowe hasło poprawnym hasłem

_**Rezultat:** Hasło zostało poprawnie zmienione, widoczny jest komunikat o treści "Informacje poprawnie zaktualizowane" jednakże strona jest "ucięta", nie da się jej scrollować_

![Screen 13 - srona ucięta do połowy po zaktualizowaniu hasła](https://user-images.githubusercontent.com/118970045/212753466-36a1c124-b975-4bfb-bf31-565c6fbfc046.png)

### Zmiana hasła na niepoprawne hasło ###

Zmiana hasła na niepoprawne (na bardzo długie hasło)  - **brak walidacji weryfikacji nieprawidłowego hasła**

_**WYKRYTE DEFEKTY:**_

**ID-006 Po zmianie hasła na bardzo długie nie jest możliwe zalogowanie się do konta**

Priorytet: Wysoki

Kroki
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta i zaloguj się na konto
3. Wejdź w zakładkę moje dane
4. Uzupełnij pole hasło swoim aktualnym hasłem
5. Uzupełnij pole nowe hasło bardzo długim hasłem, ja użyłam hasła Wiaderkoooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo

_**Rezultat:** Hasło zostało poprawnie zmienione_

Następnie:

6. Wyloguj się z konta
7. Zaloguj się ponownie przy użyciu swojego bardzo długiego hasła

_**Rezultat:** Brak możliwości zalogowania się do konta. Pod polem hasło wyskakuje komunikat Niepoprawny format_

![screen - brak możliwości zalogowania się](https://user-images.githubusercontent.com/118970045/212742177-3fb7cc4a-682d-4592-8299-0f4e6cf8ed84.png)

**Oczekiwane zachowanie:** _Przy próbie zmiany hasła do konta na bardzo długie powinna działać weryfikacji walidacji hasła uniemożliwiająca użycie nieprawidłowego hasła._

W celu odzyskania dostępu do konta należy skorzystać z funkcji "Nie pamiętasz hasła?". 

Formularz odzyskiwania hasła działa prawidłowo. Dopuszczalna jest możliwość zmiany hasła na poprawne hasło pierwotne. 


**ID-007 Brak możliwości zmiany danych użytkownika**

Priorytet: Wysoki

Kroki
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta i zaloguj się na konto
3. Wejdź w zakładkę moje dane

_**Rezultat:** Brak możliwości zmiany danych. Raz po zalogowaniu się na konto i otwarciu zakładki można zmienić dane (w tym hasło), natomiast innym razem po zalogowaniu się na konto nie ma możliwości zmiany danych. Strony nie da się scrollować, a nad nagłówkiem pojawiają się dwie notyfikacje._

![screen - bład moje dane](https://user-images.githubusercontent.com/118970045/212740918-9eb70dfa-0f8e-46a1-b828-e684c616c94d.png)

### INNE DEFEKTY ###

**ID-008 Problem z wyglądem czcionki „na” polskich znakach**

Priorytet: Niski

Kroki:
1. Wejdź na stronę https://sprecords.pl/
2. Zaloguj się
3. Wejdź na Moje konto

_**Rezultat:** Zastosowana czcionka w Witaj Karolina Szczęch najprawdopodobniej nie obsługuje polskich znaków i/lub zastosowane są różne czcionki._ 

![2023-01-11 11 54 55 SP records -  polskie znaki](https://user-images.githubusercontent.com/118970045/212748060-ae097638-8772-400b-b18a-7af21721c63e.png)


Następnie

4. Przejdź ścieżkę Moje konto >Historia i szczegóły zamówień
5. Kliknij na szczegóły swojego zamówienia
6. Na dole strony pojawi się okienko DODAJ WIADOMOŚĆ


_**Rezultat:** Czcionka zastosowana dla tekstu: „DODAJ WIADOMOŚĆ”  najprawdopodobniej nie obsługuje polskich znaków i/lub zastosowane są różne czcionki._

![SP Records - ść](https://user-images.githubusercontent.com/118970045/212748170-6a6d17a1-24c2-4f83-ae42-cbddb92b56ca.png)


**ID-009 Niepoprawne wyniki filtrowania płyt winylowych artysty Pidżama Porno**

_Problem występuje jedynie po wyfiltrowaniu (LP) płyt winylowych. W przypadku wyświetlenia wszystkich produktów (gadżetów, koszulek, płyt winylowych, kaset itp.) w zwróconych wynikach nie ma produktów innych artystów._

Priorytet: niski

Kroki:
1. Wejdź na stronę https://sprecords.pl/
2. Wyszukaj artystę Pidżama Porno
3. Wyfiltruj płyty winylowe tego artysty (LP)

_**Rezultat:** Wśród płyt winylowych artysty Pidżama Porno widnieją płyty winylowe artysty El DUPA_

![Full Page SP Records -bug](https://user-images.githubusercontent.com/118970045/212754014-9b596186-eb1a-4898-a104-add97607ce29.png)

**Oczekiwane zachowanie:** _W wyfiltrowanych wynikach powinny być jedynie płyty winylowe artysty Pidżama Porno._


**ID-010 Niepoprawne wyniki filtrowania gadżetów artysty Pidżama Porno**

_Problem występuje jedynie po wyfiltrowaniu gadżetów. W przypadku wyświetlenia wszystkich produktów (gadżetów, koszulek, płyt winylowych, kaset itp.) w zwróconych wynikach nie ma produktów innych artystów._ 

Priorytet: Niski

Kroki:
1. Wejdź na stronę https://sprecords.pl/
2. Wyszukaj artystę Pidżama Porno
3. Wyfiltruj gadżety tego artysty 

_**Rezultat:** Wśród gadżetów artysty Pidżama Porno widnieją gadżety artysty Kazik na Żywo (KNŻ)._

![PP - Gażety](https://user-images.githubusercontent.com/118970045/212754545-a4d1557f-5389-4159-99dc-94aacfa2c1ff.png)

**Oczekiwane zachowanie:** _W wyfiltrowanych wynikach powinny być jedynie gadżety artysty Pidżama Porno._

**ID-011 Niepoprawne wyniki filtrowania gadżetów artysty Kazik Na Żywo (KNŻ)**

_Problem występuje jedynie po wyfiltrowaniu gadżetów. W przypadku wyświetlenia wszystkich produktów (gadżetów, koszulek, płyt winylowych, kaset itp.) w zwróconych wynikach u artysty KNŻ figurują wszystkie jego gadżety._

Priorytet: Niski

Kroki:
1. Wejdź na stronę  https://sprecords.pl/
2. Wyszukaj artystę KNŻ
3. Wyfiltruj gadżety tego artysty 
 
_**Rezultat:** Brak jakichkolwiek gadżetów u artysty KNŻ._

 Następnie 
 
4. Wyszukaj artystę Pidżama Porno
5. Wyfiltruj gadżety artysty

_**Rezultat:** Gadżety KNŹ są wśród gadżetów artysty Pidżama Porno._

![KNŻ - brak gadżetów](https://user-images.githubusercontent.com/118970045/212755497-ba450d15-e5ff-4b8b-a06a-5ffde103109d.png)
![PP - Gażety](https://user-images.githubusercontent.com/118970045/212755500-aaa36bbe-1723-4728-883b-cc6aff9f4c22.png)


**Oczekiwane zachowanie:** _Wśród gadżetów artysty Pidżama Porno nie powinno być gadżetów artysty KNŻ._

**ID-012 Niejednakowe stylowanie elementów z nagłówka**

![2023-01-11 11 51 15 _ cała strona SP](https://user-images.githubusercontent.com/118970045/212756916-e39dedd7-85ec-464d-8319-2bbb2f42e528.png)

Położenie białych elementów na czarnym polu jest ewidentnie niesymetryczne. 
Elementy i tekst PRODUKTY po stronie lewej są większe niż elementy i tekst ARTYŚCI po stronie prawej.
Wskazane elementy i tekst powinny być jednakowo ostylowane.

**ID-013 Nieprawidłowe stylowanie elementów z nagłówka**

W przypadku powiększenia widoku strony do wielkości 125% tekst PRODKUTY wychoodzi poza czarne pole i nachodzi na pole ARTYŚCI

![screeen 125procent powiększenia](https://user-images.githubusercontent.com/118970045/212757974-44d5a131-a75b-497b-8d30-fd7d41b7e75e.png)



## Propozycje użyteczności ##

Myślę, że dobrą opcją byłaby możliwość utworzenia i późniejszego logowania się do konta przy użyciu konta gmail czy konta facebook.







