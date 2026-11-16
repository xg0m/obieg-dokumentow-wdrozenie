# Etap 6. Status projektu, ryzyka i przekazanie do utrzymania

Dane są fikcyjne.

## Harmonogram

| Kamień milowy | Termin | Status |
|---|---|---|
| Warsztat z klientem | 10.03.2026 | Zakończony |
| Akceptacja koncepcji wdrożenia | 24.03.2026 | Zakończony |
| Konfiguracja środowiska testowego | 28.04.2026 | Zakończony |
| Migracja danych startowych | 05.05.2026 | W trakcie |
| Testy akceptacyjne (UAT) | 12.05 - 23.05.2026 | Planowany |
| Szkolenia użytkowników | 26.05 - 30.05.2026 | Planowany |
| Uruchomienie produkcyjne | 01.06.2026 | Planowane |
| Asysta powdrożeniowa | 01.06 - 30.06.2026 | Planowana |
| Przekazanie do utrzymania | 03.07.2026 | Planowane |

## Przykładowy raport statusu dla kierownika projektu (tydzień 8)

| Obszar | Ocena | Komentarz |
|---|---|---|
| Zakres | Zielony | Bez zmian względem zaakceptowanej koncepcji |
| Harmonogram | Żółty | Eksport z systemu kadrowego dostarczony 3 dni po terminie. Migracja przesunięta do 05.05. |
| Jakość danych | Żółty | 6% rekordów z błędami (duplikaty, błędne numery PESEL). Raport przekazany klientowi do poprawy. |
| Ryzyka | Żółty | Dwa otwarte ryzyka (R-1, R-2). |
| Potrzebne decyzje | - | Wskazanie osób do UAT (do 08.05) |

## Rejestr ryzyk

| ID | Ryzyko | Prawdopodobieństwo | Wpływ | Działanie | Właściciel |
|---|---|---|---|---|---|
| R-1 | Opóźnione dostarczenie eksportu z systemu kadrowego | Średnie | Wysoki | Uzgodnić termin na piktogramie harmonogramu, przygotować zestaw danych testowych | Kierownik projektu |
| R-2 | Niska jakość danych źródłowych | Wysokie | Średni | Walidacja przed importem i raport błędów dla klienta | Konsultant wdrożeniowy |
| R-3 | Brak dostępności użytkowników w czasie UAT | Średnie | Wysoki | Zarezerwować terminy z wyprzedzeniem, wskazać zastępców | Właściciel procesu |
| R-4 | Zmiany wymagań po akceptacji koncepcji | Średnie | Średni | Zmiany tylko przez formalny wniosek zmiany z oceną wpływu | Kierownik projektu |
| R-5 | Problemy z konfiguracją SSO po stronie klienta | Średnie | Wysoki | Wczesny test logowania na środowisku testowym | IT klienta |

## Lista kontrolna przekazania do utrzymania

- [ ] Dokumentacja konfiguracji jest aktualna (role, słowniki, formularz, obieg).
- [ ] Instrukcje użytkownika i nagrania szkoleń są przekazane.
- [ ] Wszystkie błędy o priorytecie Wysoki są zamknięte.
- [ ] Lista otwartych błędów o niższym priorytecie jest przekazana z planem napraw.
- [ ] Dane dostępowe administratora są przekazane bezpiecznym kanałem.
- [ ] Zespół utrzymania przeszedł szkolenie administracyjne.
- [ ] Protokół odbioru jest podpisany przez klienta.
