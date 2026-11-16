# Reguły pracy z narzędziami AI w tym repozytorium

Plik dla narzędzi AI w wierszu poleceń (Claude Code, Gemini CLI, Codex CLI) i dla osób współpracujących.

## Kontekst

Repozytorium to fikcyjne case study wdrożenia systemu obiegu dokumentów dla uczelni. Dokumenty są w katalogu docs, proces BPMN w katalogu process.

## Reguły

- Pisz po polsku, prostym językiem, bez żargonu.
- Używaj wyłącznie danych fikcyjnych. Nie wpisuj prawdziwych danych osobowych, haseł ani adresów.
- Każde wymaganie ma identyfikator W-xx. Każdy scenariusz UAT odwołuje się do wymagania.
- Nie wymyślaj funkcji produktu. Gdy brakuje informacji, zapisz pytanie otwarte (P-x) i przyjęte założenie.
- Zmiana wymagania wymaga aktualizacji: docs/01-wymagania.md, docs/02-proces.md wraz z plikiem BPMN, docs/03-konfiguracja.md i docs/04-uat.md.

## Sposób pracy

1. Zbuduj kontekst: przeczytaj README i docs/01-wymagania.md.
2. Podziel zadanie na kroki: wymaganie, proces, konfiguracja, test.
3. Po każdym kroku sprawdź spójność według listy poniżej.
4. Człowiek weryfikuje wynik przed zapisaniem zmiany. Odpowiedzi AI traktuj jako szkic.

## Lista kontrolna spójności

- [ ] Każde wymaganie Must ma element procesu i scenariusz UAT.
- [ ] Progi i terminy są takie same we wszystkich dokumentach (np. 5000 zł, 2 dni robocze).
- [ ] Nazwy statusów w procesie, konfiguracji i UAT są identyczne.
- [ ] Plik BPMN otwiera się w bpmn.io bez błędów.
