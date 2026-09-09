BLACKJACK KALKULATOR - WERSJA DESKTOPOWA (Electron + GitHub Actions)
======================================================================

MASZ DOSTĘP TYLKO DO WINDOWSA NA CO DZIEŃ? Ten projekt jest ustawiony tak,
żeby GitHub zbudował za Ciebie zarówno plik .exe (Windows) jak i .dmg (Mac)
w chmurze - nie potrzebujesz fizycznie Maca do zbudowania appki na Maca.

CZĘŚĆ A: TEST LOKALNY NA WINDOWSIE (opcjonalne, ale polecane najpierw)
------------------------------------------------------------------------
1. Zainstaluj Node.js (LTS) z https://nodejs.org
2. W folderze projektu, w terminalu: npm install
3. Uruchom: npm start   -> powinno się otworzyć okno appki
4. Jeśli chcesz sam plik .exe z tego komputera: npm run dist
   (znajdziesz go w folderze dist/)

CZĘŚĆ B: BUDOWANIE OBU WERSJI (Windows + Mac) PRZEZ GITHUB
------------------------------------------------------------------------
1. Załóż darmowe konto na https://github.com (jeśli jeszcze nie masz).

2. Zainstaluj GitHub Desktop (https://desktop.github.com) - to prosta
   aplikacja z klikaniem zamiast wpisywania komend gita w terminalu.

3. W GitHub Desktop: File -> New repository. Wskaż jako lokalizację
   ten folder (blackjack-electron-app). Nazwij repozytorium, np.
   "blackjack-kalkulator". Może być prywatne albo publiczne - oba
   działają z GitHub Actions za darmo (prywatne mają limit minut
   budowania w miesiącu, ale ten projekt jest mały i się zmieści).

4. Kliknij "Publish repository" - to wgrywa projekt na GitHub.

5. Wejdź na stronę repozytorium w przeglądarce -> zakładka "Actions"
   na górze. Powinien się tam pojawić uruchomiony workflow o nazwie
   "Build Blackjack Kalkulator" (startuje automatycznie po wgraniu).
   Jeśli nie widzisz go od razu, kliknij "Build Blackjack Kalkulator"
   po lewej, potem "Run workflow" po prawej.

6. Budowanie trwa kilka minut (osobno dla Windows i dla Mac). Jak się
   skończy (zielony haczyk), wejdź w ten konkretny "run" - na dole
   strony będzie sekcja "Artifacts" z dwoma plikami do pobrania:
   - blackjack-kalkulator-windows-latest (zawiera plik .exe)
   - blackjack-kalkulator-macos-latest (zawiera plik .dmg)

7. Pobierasz, rozpakowujesz, wysyłasz komu chcesz - jeden plik dla
   użytkowników Windows, drugi dla użytkowników Maca.

KIEDY BUDOWAĆ PONOWNIE:
Za każdym razem, jak zmienisz coś w kodzie (np. ja Ci coś poprawię w
index.html), wystarczy w GitHub Desktop zrobić "Commit" + "Push" -
GitHub sam odpali budowanie od nowa.

WAŻNE UWAGI:
- Niepodpisany .exe na Windowsie wywoła ostrzeżenie SmartScreen
  ("Windows chronił Twój komputer") - trzeba kliknąć "Więcej informacji"
  -> "Uruchom mimo to". To normalne dla appek bez płatnego certyfikatu.
- Niepodpisana appka na Macu wywoła podobne ostrzeżenie Gatekeepera -
  obejście: prawy klik na appkę -> "Otwórz". Pełne pozbycie się tego
  ostrzeżenia wymaga płatnego konta Apple Developer (99$/rok) - nie
  jest tego warte dla appki na własny użytek/dla znajomych.
- index.html nadal ładuje React/Babel z internetu (unpkg.com) przy
  starcie appki. Jeśli chcesz 100% offline, daj znać - zamienię to na
  lokalne kopie bibliotek wbudowane w projekt.
