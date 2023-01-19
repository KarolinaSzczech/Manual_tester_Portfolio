# Raport z testów logowania do strony https://ceneo.pl z użyciem przypadków testowych wysokiego i niskiego poziomu #

## Raport z testów logowania do strony https://ceneo.pl z użyciem przypadków testowych wysokiego poziomu ##

**Do testów użyto:**

**Desktop:**

OS: Windows 10 PRO
 - Browser: Chrome version 107.0.5304.108 (Oficjalna wersja) (64-bitowa)
 - Browser: Firefox Wersja 109.0 (64 bity)
 - Browser: Firefox Developer Edition Wersja 108.0b6 (64 bity)
 - Browser: Microsoft Edge Wersja 107.0.1418.56 (Oficjalna kompilacja) (wersja 64-bitowa)
 - Browser: Opera Wersja Wersja:94.0.4606.37 (wersja 64-bitowa)


| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 |  Logowanie istniejącego użytkownika poprawnymi danymi |	Użytkownik jest zalogowany do aplikacji | Działa|
|2 |  Próba zalogowania się istniejącego użytkownika z użyciem błędnego hasła | Użytkownik powinien zobaczyć komunikat np. „Nieprawidłowe dane uwierzytelniające” | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|3 |	Próba zalogowania się z użyciem losowego loginu i hasła (nie istniejącego w bazie) | Użytkownik powinien zobaczyć komunikat np.: „Nieprawidłowe dane uwierzytelniające” | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|4 |	Próba zalogowania się pustym formularzem | Powinna zostać wyświetlona informacja o wymaganej wartości lub Przycisk powinien być wyłączony tak długo, jak pola są puste | Walidacja działa|
|5 |	Weryfikacja pola logowania przy użyciu wielkich liter jako login i ważnego hasło | Użytkownik jest zalogowany do aplikacji Uwaga: Tylko jeśli tak ma to działać | Użytkownik poprawnie zalogowany|
|6 |	Weryfikacja pola logowania: w przypadku poczty e-mail weryfikacja polega tylko adresu @domain.com i ważnego hasła | Powinna zostać wyświetlona informacja "niepoprawna wartość" Uwaga: Jeżeli system używa adresu e-mail jako loginu, dobrze byłoby wyświetlić login@domena.com wraz z komunikatem "Nieprawidłowa wartość" | Walidacja działa. Pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|7 |	Zalogowany użytkownik wprowadza adres URL logowania | Użytkownik zostaje przekierowany na stronę główną| **Wykryto defekt - ID 001** |
|8 |	Wpisanie hasła na stronie logowania |	Hasło powinno być zamaskowane *** | Działa | 
|9 |	Używanie klawisza Tab do poruszania się po formularzu logowania |  Użytkownik może używać klawiatury do logowania się do aplikacji |	Działa|
|10 |	Używanie klawisza Enter do potwierdzenia formularza logowania | Użytkownik jest zalogowany do aplikacji	| Działa|
|11	| Zaznaczenie pola wyboru Zapamiętaj hasło i zalogowanie się przy użyciu poprawnych danych uwierzytelniających | Użytkownik powinien być zalogowany po ponownym wejściu na stronę, po ponownym uruchomieniu przeglądarki | Działa|
|12	| Trzykrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Blokada logowania na kilka minut i/lub e-mail do użytkownika o podejrzanej próbie logowania| **Wykryto defekt - ID 002** |
|13 | Pięciokrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Blokada logowania na kilka minut i/lub e-mail do użytkownika o podejrzanej próbie logowania|**Wykryto defekt - ID 003** |

### ID 001 Brak przekierowania na stronę główną po wpisaniu adresu URL logowania ###

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://ceneo.pl
2. Przejdż na stronę logowania 
3. Skopiuj adres URL strony logowania
4. Zaloguj się poprawnymi danymi 
5. Wklej adres URL strony logowania i wciśnij ENTER

**_Rezultat_**: Użytkownik zostaje przekierowany na stronę logowania

![1](https://user-images.githubusercontent.com/118970045/213262691-a77dc0bd-a075-437f-bb24-b4bbd1f13c6f.png)


### ID 002 Brak blokady dalszego logowania po trzykrotnej próbie zalogowania się z użyciem nieprawidłowego hasła ###

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://ceneo.pl
2. Przejdż na stronę logowania 
3. Trzykrotnie zaloguj się do konta z użyciem nieprawidłowego hasła

**_Rezultat_**: Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła.

![2](https://user-images.githubusercontent.com/118970045/213248247-0dde9824-7598-4809-b83d-a3c55b6d8ee3.png)


### ID 003 Brak blokady dalszego logowania po pięciokrotnwj próbie zalogowania się z użyciem nieprawidłowego hasła ###

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://ceneo.pl
2. Przejdż na stronę logowania 
3. Pięciokrotnie zaloguj się do konta z użyciem nieprawidłowego hasła

**_Rezultat_**: Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła. Pojawia się również reCAPTCHA z opcją zaznaczenia nie jestem robotem

![3](https://user-images.githubusercontent.com/118970045/213262979-efd5f772-5813-4ada-942a-f8073a75e71c.png)


**UWAGI:**

W przeglądarce Chrome i Edge wystraczy zaznaczyć pole **Nie jestem robotem** żeby móc dalej próbować zalogować się na stronę. Nie pojawia się czerwony komunikat **Potwierdź, że nie jesteś robotem**.

![5](https://user-images.githubusercontent.com/118970045/213263115-0f1baadb-e3d8-456f-b812-522fd0d3702d.png)


W przeglądarce OPERA, Firefox oraz Firefox Developer Edition  pojawia się czerwony komunikat **Potwierdź, że nie jesteś robotem**. Ponadto oprócz pola **Nie jestem robotem**  trzeba jeszcze przejść weryfikację obrazkową żeby móc dalej próbować zalogować się na stronę

![6](https://user-images.githubusercontent.com/118970045/213261337-4cdea001-e06e-40f0-af09-05921f3fef3e.png)

![4](https://user-images.githubusercontent.com/118970045/213261231-cb91e8bf-a473-418b-bfb6-cc0ee19c3c03.png)


## Raport z testów logowania do strony https://ceneo.pl z użyciem przypadków testowych niskiego poziomu ##

### Logowanie do strony za pomocą konta Facebook ###

**CEL:** Weryfikacja możliwości zalogowania do aplikacji za pomocą konta połączonego z kontem na portalu Facebook.

| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 |   |	 | |
|2 |   |  | |
|3 |	 |  | |
|4 |	 |  | |
