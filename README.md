#🎧 3D Audio Explorer

3D Audio Explorer to interaktywne narzędzie webowe do eksploracji dźwięku przestrzennego w czasie rzeczywistym. Aplikacja wykorzystuje zaawansowane algorytmy Web Audio API (HRTF), aby symulować sposób, w jaki ludzkie ucho odbiera dźwięki z różnych kierunków i odległości.

![Technologia-HTML5/JS-blue)

##🚀 Główne Funkcje

Spatial Audio (Dźwięk Przestrzenny): Pełna symulacja 3D z uwzględnieniem pozycji ($X, Y, Z$) oraz orientacji słuchacza.

Dwa Tryby Pracy:

###✏️ Tryb Edycji: Dowolnie rozmieszczaj źródła dźwięku na mapie za pomocą myszki.

###🎮 Tryb Eksploracji: Wciel się w rolę słuchacza i poruszaj się po stworzonym świecie, doświadczając imersyjnych przejść dźwiękowych.

Dynamiczna Minimapa: Podgląd całego obszaru w czasie rzeczywistym z wskaźnikiem pozycji i kierunku patrzenia.

Drag & Drop: Błyskawiczne dodawanie własnych plików audio (.mp3, .wav, .ogg) bezpośrednio do przeglądarki.

Wizualizacja Zasięgu: Graficzne przedstawienie propagacji dźwięku dla aktywnych źródeł.

##🛠 Zastosowania

Aplikacja idealnie sprawdzi się jako:

Prototypowanie audio w grach: Szybkie sprawdzanie, jak różne odgłosy otoczenia współgrają ze sobą w przestrzeni.

Wsparcie sesji RPG: Tworzenie dynamicznych teł dźwiękowych (np. karczma, las), gdzie pozycja graczy wpływa na to, co słyszą.

Narzędzie relaksacyjne/ASMR: Komponowanie własnych pejzaży dźwiękowych (soundscapes) do pracy lub medytacji.

Edukacja: Demonstracja zjawisk akustycznych, takich jak spadek głośności wraz z dystansem czy panorama stereo.

##⌨️ Sterowanie

Klawisz / Akcja

Funkcja

W, A, S, D

Poruszanie się słuchaczem

Q, E

Obracanie głowy (zmiana panoramy)

Kliknięcie na mapie

Automatyczne przejście do wskazanego punktu

Przeciąganie (Explore)

Swobodne rozglądanie się

Przeciąganie (Edit)

Zmiana pozycji źródła dźwięku

Spacja

Play / Pauza wybranego źródła

##🏗 Technologia

Aplikacja została zbudowana przy użyciu czystych technologii webowych, co gwarantuje szybkość działania i brak konieczności instalowania dodatkowych bibliotek:

Web Audio API: Obsługa pannerów 3D i listenera.

HTML5 Canvas: Wydajne renderowanie środowiska graficznego 2D.

Vanilla JavaScript: Logika aplikacji i zarządzanie stanem bez zbędnego narzutu.

##📦 Instalacja i Uruchomienie

Sklonuj repozytorium:

git clone [https://github.com/twój-username/audio-explorer.git](https://github.com/twój-username/audio-explorer.git)


Otwórz plik index.html w dowolnej nowoczesnej przeglądarce (Chrome, Firefox, Edge).

Ważne: Przeglądarki blokują autoodtwarzanie dźwięku. Kliknij gdziekolwiek na stronie po jej załadowaniu, aby aktywować silnik audio.

Stworzone z pasji do dźwięku i interaktywnych mediów.
