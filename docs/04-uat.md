# Etap 4. Testy akceptacyjne (UAT)

Scenariusze testowe przygotowane do wykonania przez użytkowników klienta w środowisku testowym. Kolumna Wynik jest do uzupełnienia podczas testów.

## Zasady

- Środowisko: testowe, z kontami testowymi dla każdej roli (np. pracownik.test, przelozony.test, finanse.test, prorektor.test).
- Kryterium zakończenia: wszystkie scenariusze o priorytecie Wysoki zaliczone i brak otwartych błędów o priorytecie Wysoki.
- Błędy zgłaszamy w rejestrze poniżej. Zespół produktowy dostaje opis, kroki odtworzenia i zrzut ekranu.

## Scenariusze

| ID | Wymaganie | Priorytet | Kroki | Oczekiwany wynik | Wynik |
|---|---|---|---|---|---|
| UAT-01 | W-01 | Wysoki | 1. Zaloguj się jako pracownik.<br>2. Wypełnij wszystkie pola poprawnymi danymi.<br>3. Kliknij Złóż wniosek. | Wniosek ma status Do akceptacji przełożonego i ma numer. | Do wykonania |
| UAT-02 | W-02 | Wysoki | Ustaw datę powrotu wcześniejszą niż datę wyjazdu i spróbuj złożyć wniosek. | Komunikat o błędzie przy polu. Wniosek nie zostaje złożony. | Do wykonania |
| UAT-03 | W-02 | Wysoki | Wpisz koszt 0 i spróbuj złożyć wniosek. | Komunikat o błędzie przy polu Koszt. | Do wykonania |
| UAT-04 | W-01 | Średni | Wybierz źródło Grant badawczy i zostaw pusty Numer projektu. | System wymaga numeru projektu. | Do wykonania |
| UAT-05 | W-03 | Wysoki | Zaloguj się jako przełożony i zaakceptuj wniosek. | Status zmienia się na Do akceptacji finansowej. | Do wykonania |
| UAT-06 | W-03 | Wysoki | Zwróć wniosek bez komentarza, a potem z komentarzem. | Bez komentarza system blokuje akcję. Z komentarzem wniosek ma status Do poprawy. | Do wykonania |
| UAT-07 | W-04 | Wysoki | Jako finanse odrzuć wniosek z komentarzem. | Status Odrzucony. Wnioskodawca dostaje e-mail. | Do wykonania |
| UAT-08 | W-05 | Wysoki | Złóż wniosek z kosztem 5000,00 zł i przeprowadź go przez akceptacje. | Wniosek omija prorektora i otrzymuje status Zatwierdzony. | Do wykonania |
| UAT-09 | W-05 | Wysoki | Złóż wniosek z kosztem 5000,01 zł i przeprowadź go przez akceptacje. | Po finansach wniosek trafia do prorektora. | Do wykonania |
| UAT-10 | W-06 | Średni | Przejdź wniosek przez wszystkie statusy. | Każda zmiana statusu generuje e-mail zgodny z tabelą powiadomień. | Do wykonania |
| UAT-11 | W-07 | Wysoki | Zaloguj się kontem uczelnianym przez SSO. | Logowanie bez dodatkowego hasła. Rola zgodna z grupą w katalogu. | Do wykonania |
| UAT-12 | W-08 | Wysoki | Zaloguj się jako pracownik A i otwórz listę wniosków. | Widoczne tylko wnioski pracownika A. Bezpośrednie wejście w adres wniosku pracownika B zwraca brak dostępu. | Do wykonania |
| UAT-13 | P-1 | Wysoki | Jako przełożony złóż własny wniosek. | Wniosek trafia do przełożonego wyższego szczebla, a nie do składającego. | Do wykonania |
| UAT-14 | W-09 | Średni | Doprowadź wniosek do statusu Zatwierdzony. | Polecenie wyjazdu w PDF ma poprawne dane z wniosku. | Do wykonania |
| UAT-15 | W-12 | Średni | Włącz zastępstwo przez przełożonego i złóż wniosek. | Zadanie trafia do zastępcy. Po zakończeniu zastępstwa wraca do przełożonego. | Do wykonania |

## Rejestr błędów (wzór)

| ID błędu | Scenariusz | Opis | Priorytet | Status | Odpowiedzialny |
|---|---|---|---|---|---|
| BUG-001 | UAT-09 | (przykład) Wniosek 5000,01 zł omija prorektora | Wysoki | Do analizy | Zespół produktowy |
