# Etap 3. Konfiguracja systemu

Opis docelowej konfiguracji wykonywanej bez programowania: role, słowniki, formularz, obieg akceptacji, powiadomienia i szablon dokumentu. Dane są fikcyjne.

## Role i uprawnienia

| Rola | Kto | Widoczne wnioski | Dozwolone akcje |
|---|---|---|---|
| Wnioskodawca | Każdy pracownik | Własne | Tworzenie, edycja szkicu, składanie, wycofanie przed akceptacją |
| Przełożony | Kierownicy jednostek | Własne i zespołu | Akceptacja, odrzucenie, zwrot do poprawy |
| Finanse | Dział finansów | Wnioski po akceptacji przełożonego | Akceptacja finansowa, odrzucenie, raport |
| Prorektor | Dwie osoby | Wnioski powyżej 5000 zł | Akceptacja, odrzucenie |
| Kadry | Dział kadr | Wszystkie (odczyt) | Zarządzanie słownikami, archiwum |
| Administrator | IT klienta | Brak wglądu w treść | Konfiguracja, konta, logi |

Zasada najmniejszych uprawnień: każda rola ma tylko dostęp potrzebny do swoich kroków obiegu.

## Słowniki

| Słownik | Wartości | Właściciel |
|---|---|---|
| Cel wyjazdu | Konferencja, Szkolenie, Badania terenowe, Spotkanie projektowe, Inny | Kadry |
| Źródło finansowania | Budżet jednostki, Grant badawczy, Projekt UE, Inne | Finanse |
| Środek transportu | Samolot, Pociąg, Autobus, Samochód służbowy, Samochód prywatny | Kadry |

## Formularz wniosku delegacyjnego

| Pole | Typ | Wymagane | Walidacja lub reguła |
|---|---|---|---|
| Cel wyjazdu | Lista ze słownika | Tak | Brak |
| Opis celu | Tekst wielowierszowy | Tak | Minimum 20 znaków |
| Miejsce | Tekst | Tak | Brak |
| Data wyjazdu | Data | Tak | Nie wcześniejsza niż dzisiaj |
| Data powrotu | Data | Tak | Nie wcześniejsza niż data wyjazdu |
| Środek transportu | Lista ze słownika | Tak | Brak |
| Koszt szacowany (zł) | Liczba, 2 miejsca po przecinku | Tak | Większy od 0 i nie większy niż 100000 |
| Źródło finansowania | Lista ze słownika | Tak | Brak |
| Numer projektu | Tekst | Warunkowo | Wymagany, gdy źródło to Grant badawczy lub Projekt UE |
| Załączniki | Pliki | Nie | PDF, maksymalnie 10 MB każdy |
| Komentarz decyzji | Tekst | Warunkowo | Wymagany przy statusach Do poprawy i Odrzucony |

## Obieg akceptacji

| Krok | Kto decyduje | Warunek wejścia | Możliwe decyzje | Termin |
|---|---|---|---|---|
| 1 | Bezpośredni przełożony | Wniosek złożony | Akceptuj, Zwróć, Odrzuć | 2 dni robocze |
| 2 | Finanse | Krok 1 zaakceptowany | Akceptuj, Odrzuć | 2 dni robocze |
| 3 | Prorektor | Krok 2 zaakceptowany i koszt powyżej 5000 zł | Akceptuj, Odrzuć | 3 dni robocze |

Zastępstwo: jeśli decydent ma włączone zastępstwo, zadanie trafia do wskazanego zastępcy na czas jego trwania.

## Powiadomienia e-mail

| Zdarzenie | Odbiorca | Temat wiadomości |
|---|---|---|
| Wniosek złożony | Przełożony | Nowy wniosek delegacyjny do akceptacji |
| Zwrot do poprawy | Wnioskodawca | Wniosek wymaga poprawy |
| Odrzucenie | Wnioskodawca | Wniosek został odrzucony |
| Zatwierdzenie | Wnioskodawca i Kadry | Wniosek zatwierdzony, polecenie wyjazdu w załączeniu |
| 2 dni bez decyzji | Decydent | Przypomnienie o wniosku czekającym na decyzję |
| 4 dni bez decyzji | Kierownik działu decydenta | Wniosek czeka na decyzję ponad 4 dni |

## Szablon polecenia wyjazdu służbowego

Szablon w PDF wypełniany polami z wniosku: {{imię_nazwisko}}, {{jednostka}}, {{miejsce}}, {{data_wyjazdu}}, {{data_powrotu}}, {{środek_transportu}}, {{koszt_szacowany}}, {{numer_wniosku}}, {{data_zatwierdzenia}}.

## Logowanie SSO

- Protokół: OpenID Connect lub SAML 2.0, do uzgodnienia z IT klienta.
- Login użytkownika: adres e-mail z konta uczelnianego.
- Role w systemie wynikają z grup w katalogu użytkowników: GRP_Pracownicy, GRP_Kierownicy, GRP_Finanse, GRP_Prorektorzy, GRP_Kadry, GRP_Admin.
- Konto lokalne administratora zostaje jako awaryjne, z silnym hasłem i włączonym logowaniem zdarzeń.

## Dane startowe

Pracownicy i struktura organizacyjna pochodzą z eksportu CSV z systemu kadrowego. Przed importem dane przechodzą walidację opisaną w projekcie [migration-validator](https://github.com/xg0m/migration-validator). Raport z walidacji jest przekazywany klientowi do poprawy źródła.
