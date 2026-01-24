Spatial Audio Explorer
Interaktywne środowisko przeglądarkowe do symulacji i badania akustyki przestrzennej. Narzędzie wykorzystuje standard Web Audio API oraz modelowanie HRTF (Head-Related Transfer Function) do precyzyjnej lokacji źródeł dźwięku w przestrzeni dwuwymiarowej z odwzorowaniem sferycznym.
Kluczowe funkcjonalności
Renderowanie przestrzenne: Pełna implementacja węzłów PannerNode oraz AudioListener, umożliwiająca analizę zmian natężenia i barwy dźwięku w zależności od pozycji () oraz rotacji słuchacza.
Architektura dwutrybowa:
Tryb Projektowy (Edit): Precyzyjne rozmieszczanie źródeł sygnału w przestrzeni laboratoryjnej.
Tryb Eksploracji (Explore): Interaktywna weryfikacja sceny dźwiękowej z perspektywy użytkownika końcowego.
Monitorowanie parametrów: Podgląd współrzędnych geograficznych oraz kąta orientacji w czasie rzeczywistym (HUD).
Analiza dystansu: Wizualizacja tłumienia sygnału zgodnie z modelem fizycznym inverse distance.
Zastosowanie
Projekt służy jako platforma do:
Prototypowania systemów audio w środowiskach wirtualnych.
Badań nad percepcją dźwięku przestrzennego.
Tworzenia dynamicznych opraw akustycznych dla gier i symulacji RPG.
Edukacji w zakresie inżynierii dźwięku i akustyki cyfrowej.
Specyfikacja sterowania
| Interakcja | Funkcja |
| W, A, S, D | Translacja pozycji słuchacza w osiach X/Y |
| Q, E | Manipulacja rotacją (azymut słuchacza) |
| LPM (Mapa) | Definiowanie wektora ruchu do celu |
| Przeciąganie (Explore) | Zmiana orientacji wektora patrzenia |
| Przeciąganie (Edit) | Relokacja wybranych źródeł sygnału |
| Spacja | Kontrola stanu odtwarzania (Play/Pause) |
Architektura techniczna
Aplikacja jest w pełni autonomiczna i nie wymaga zewnętrznych zależności (Zero-dependency):
Web Audio API: Silnik przetwarzania sygnałów i renderowania 3D.
HTML5 Canvas: System wizualizacji wektorowej środowiska.
Vanilla JavaScript (ES6+): Zarządzanie stanem i obsługa zdarzeń.
Uruchomienie projektu
Sklonuj repozytorium:
git clone [https://github.com/spatial-audio-lab/audio-explorer.git](https://github.com/spatial-audio-lab/audio-explorer.git)



Otwórz plik index.html w środowisku zgodnym z Web Audio API (Chrome 60+, Firefox 55+, Edge 79+).
Uwaga: Ze względów bezpieczeństwa (Autoplay Policy), interakcja ze stroną jest wymagana do zainicjowania kontekstu audio.
Projekt rozwijany w ramach Spatial Audio Lab.
