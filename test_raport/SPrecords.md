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
 - Na przygotowanie raportu około 3h

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

Walidacja działa poprawnie, pojawia się kumunikat "Pole email jest zbyt długie (maks. 128 znaków)."


### Weryfikacja użycia krótkiego hasła ### 

Weryfikacja walidacji hasła nie działa poprawnie
_Na stronie brak informacji o wymaganiach hasła. Żeby utworzyć konto wystarczy wpisać 5 znaków, nie muszą spełniać wymagań typu: wielka litera, cyfra, znak specjalny. Hasłem może być pięć jednakowch małych liter np: aaaaa_ 
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
3. Wypełnij poprawnie pola: Imię, Nazisko, E-mail
4. Użyj bardzo długiego hasła wypełniając pole Hasło. Jako hasło ja użyłam słowa: Wiaderkoooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo
5. Naciśnij Zapisz

_**Rezultat:** Konto zostało utworzone poprawnie, użytkownik zostaje zalogowany na stronie._

Następnie

6. Wyloguj się z konta
7. Zaloguj się na konto przy użyciu wcześniejszych danych z użyciem ustawionego długiego hasła.

_**Rezultat:** Brak możliwości zalogowania się na utwrzone konto. Pod polem hasło pojawia się komunikat Niepoprawny format._

![screen - brak możliwości zalogowania się](https://user-images.githubusercontent.com/118970045/212700822-c5640a56-8fe8-4410-860c-ea904b46fc1f.png)

**Oczekiwane zachowanie:** _Komunikat "Nieprawidłowy format" powinien pojawiać się na etapie rejestracji konta, a nie dopiero na etapie logowania._ 

### Rejestracja konta z użyciem poprawnych danych ### 
Działa

### Rejestracja konta z wykorzytaniem poprzednio użytego adresu e-mail ### 
Walidacja wcześniej użytego adresu e-mial nie zawsze działa poprawnie

_**WYKRYTE DEFEKTY**_

**ID-003 Brak czytelnego komunikatu o użyciu istniejącego w bazie adresu e-mail** 

Priorytet: Średni

Kroki:
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Wypełnij poprawnie pola: Imię, Nazisko, E-mail
Imię :anna 
Nazwisko: nowak 
E-mail: a@wp.pl 
Hasło: Wiaderko
4. Naciśnij Zapisz

_**Rezultat:**  Czasami pojwia się komunikat pod polem e-mail, że istnieje on w bazie, a czasami nad nagłówkiem strony pojawiają się dwie notyfikacje niezorzumiałe dla użytkownika._

Nie udało mi się ustalić od czego zależy pojawianie się prawidłowgo komunikatu, a od czego notyfikacji nad nagłówkiem strony.

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

**Oczekiwane zachowanie:** _Komunikat "Wypełnij pole" powinien pojawić od razu się przy wszystkich niewypełnionych polach, a nie pojedyńczo._

### ZMIANA DANYCH, ZMIANA HASŁA: ###

### Zmiana hasła na inne ### 

 - Zmiana hasła na inne poprawne, spełniające wymagania jak przy rejestracji konta - **działa prawidłowo**

 - Zmiana hasła na niepoprwane (na bardzo długie hasło)  - **brak walidacji weryfikacji nieprawidłowego hasła**


_**WYKRYTE DEFEKTY:**_

**ID-005 Po zmianie hasła na bardzo długie nie jest możliwe zalogowanie się do konta**

Priorytet: Wysoki

Kroki
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta i zaloguj się na konto
3. Wejdź w zakładkę moje dane
4. Uzupełnij pole hasło swoim aktualnym hasłem
5. Uzuepłnik pole nowe hasło bradzo długim hasłem, ja użyłam hasła Wiaderkoooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo

_**Rezultat:** Hasło zostało poprawnie zmienione_

Następnie:

6. Wyloguj się z konta
7. Zaloguj się ponownie przy użyciu swojego bardzo długiego hasła

_**Rezultat:** Brak możliwości zalogowania się do konta. Pod polem hasło wyskakuje komunikat Nieporawny format_

![screen - brak możliwości zalogowania się](https://user-images.githubusercontent.com/118970045/212742177-3fb7cc4a-682d-4592-8299-0f4e6cf8ed84.png)

**Oczekiwane zachowanie:** _Przy próbie zmiany hasła do konta na bardzo długie powinna działać weryfikacji walidacji hasła uniemożliwaijąca użycie nieprawidłowego hasła._

W celu odzyskania dostępu do konta należy skorzystać z funkcji "Nie pamietasz hasła?". 

Formularz odzyskiwania hasła działa prawidłowo. Dopuszczalna jest możliwość zmiany hasła na poprawne hasło pierwotne. 



**ID-006 Brak możliwości zmiany danych użytkownika**

Priorytet: Wysoki

Kroki
1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta i zaloguj się na konto
3. Wejdź w zakładkę moje dane

_**Rezultat:** Brak możliwości zmiany danych. Raz po zalogowaniu się na konto i otwarciu zakładki można zmienić dane (w tym hasło), natomiast innym razem po zalogowaniu się na konto nie ma możliwości zmiany danych. Strony nie da się scrollować, a nad nagłówkiem pojawiają się dwie notyfikacje._

![screen - bład moje dane](https://user-images.githubusercontent.com/118970045/212740918-9eb70dfa-0f8e-46a1-b828-e684c616c94d.png)

### INNE DEFEKTY ###

**ID-007 Problem z wyglądem czcionki „na” polskich znakach**

Priorytet: Niski

Kroki:
1. Wejdź na stronę sprecords.pl
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





Propozycje użyteczności

możliwość logowania kontem gmail lub facebooka










