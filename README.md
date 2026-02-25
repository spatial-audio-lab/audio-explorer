# 🎧 3D Audio Explorer

Interaktywna przeglądarkowa aplikacja do tworzenia i eksplorowania **immersyjnych scenografii dźwiękowych** z pełnym przestrzennym pozycjonowaniem źródeł dźwięku. Wykorzystuje **Web Audio API** z modelem **HRTF** (Head-Related Transfer Function) dla precyzyjnej lokalizacji dźwięku w przestrzeni trójwymiarowej.

---

## ✨ Funkcjonalności

### 🗺️ Dwa tryby pracy

**Tryb Edycji (`Edit`)**
- Rozmieszczanie i **przeciąganie źródeł dźwięku** po przestrzeni 2D
- Podgląd etykiet ze skróconymi nazwami plików bezpośrednio na mapie
- Wizualny wskaźnik orientacji słuchacza (kierunek patrzenia + stożek percepcji)
- Precyzyjne pozycjonowanie bez ograniczeń ruchowych

**Tryb Eksploracji (`Explore`)**
- **Poruszanie się** po przestrzeni dźwiękowej w czasie rzeczywistym
- **Klikanie na mapę** — słuchacz automatycznie idzie do wskazanego miejsca z animowanym wskaźnikiem celu
- **Przeciąganie myszą** — obracanie kierunku patrzenia/słuchania
- Automatyczna aktualizacja parametrów przestrzennych (pozycja + orientacja) w Web Audio API

### 🎵 Silnik Audio Przestrzennego
- **Model HRTF** via `PannerNode` — symulacja percepcji przestrzennej z użyciem obu uszu
- **Model tłumienia `inverse distance`** — naturalne cichnienie z odległością (refDistance: 1m, maxDistance: 50m)
- Pełna aktualizacja pozycji i orientacji `AudioListener` w czasie rzeczywistym (positionX/Y/Z + forwardX/Y/Z)
- Obsługa wielu źródeł jednocześnie z indywidualnymi węzłami `PannerNode` + `GainNode`
- Pętlowe odtwarzanie (`loop: true`) dla ciągłych pejzaży dźwiękowych

### 📂 Zarządzanie Źródłami
- **Drag & Drop** lub kliknięcie — ładowanie plików audio (mp3, wav, ogg, flac i inne)
- Odczyt i dekodowanie przez `decodeAudioData` — pełna jakość bez kompresji
- Indywidualna kontrola **głośności** każdego źródła (suwak 0–100%)
- **Play / Pause / Stop** — dla wybranego źródła lub wszystkich jednocześnie
- Usuwanie źródeł z automatycznym zwolnieniem zasobów audio

### 💾 Sceny (Save/Load)
- **Zapis sceny** — eksport do pliku `.json` zawierającego pozycje źródeł, głośności i pozycję słuchacza
- **Wczytanie sceny** — dopasowanie po nazwie pliku i przywrócenie pozycji/parametrów
- Skrót klawiszowy `Ctrl+S` / `⌘+S` do szybkiego zapisu
- Badge nazwy sceny widoczny na mapie po wczytaniu

### 🗺️ Interfejs i Nawigacja
- **Minimap** — podgląd całej przestrzeni z pozycją słuchacza i wszystkich źródeł
- **Klikalna minimap** — teleportacja celu w trybie Eksploracji
- **HUD** — aktualne współrzędne `(X, Y)` i kąt orientacji w stopniach
- **Kompas** — animowana igła z płynną rotacją (eliminacja skoku 359°→0°)
- **Wskaźnik celu** — pulsująca animacja w miejscu klikniętym na mapie

### ⌨️ Sterowanie Klawiaturą
| Klawisz | Akcja |
|---------|-------|
| `W` / `↑` | Ruch do przodu |
| `S` / `↓` | Ruch do tyłu |
| `A` | Ruch w lewo (strafe) |
| `D` | Ruch w prawo (strafe) |
| `Q` / `←` | Obrót w lewo |
| `E` / `→` | Obrót w prawo |
| `Spacja` | Play/Pause wybranego źródła |
| `Ctrl+S` | Zapisz scenę |

### 📱 Responsywność Mobile
- **Bottom sheet** z obsługą gestów swipe (rozwinięcie/zwinięcie/peek)
- **FAB** (Floating Action Button) — globalny Play/Pause wszystkich źródeł
- Osobna lista źródeł z dużymi przyciskami touch-friendly (min. 44×44px)
- Pełna obsługa `touchstart` / `touchmove` / `touchend` na canvasie

---

## 🛠️ Architektura Techniczna

Aplikacja jest w pełni **autonomiczna** — zero zewnętrznych zależności, jeden plik HTML:

| Technologia | Zastosowanie |
|-------------|--------------|
| **Web Audio API** | Silnik DSP, PannerNode, GainNode, AudioListener |
| **HTML5 Canvas 2D** | Mapa główna i minimap w czasie rzeczywistym |
| **Vanilla JavaScript ES6+** | Stan aplikacji, game loop, obsługa eventów |
| **CSS Custom Properties** | System kolorów i responsywność |

### Pętla gry (Game Loop)
Aplikacja działa w oparciu o `requestAnimationFrame` z delta-time (`dt`), co zapewnia płynne poruszanie się niezależnie od FPS. Słuchacz porusza się z prędkością 6 jednostek/s, obraca się z prędkością 90°/s.

### Układ Współrzędnych
Przestrzeń to kwadrat `±25 jednostek` (25m × 25m). Jednostka ≈ 1 metr akustyczny. Oś `X` = lewo/prawo, oś `Y` = przód/tył. Wysokość (oś pionowa) = 0 (płaska scena 2D z HRTF w przestrzeni horyzontalnej).

---

## 🎧 Jak Zacząć

> **Używaj słuchawek** — efekt przestrzenny jest perceptualny i wymaga izolacji kanałów L/R.

1. Otwórz `index.html` w przeglądarce (Chrome 90+, Firefox 90+, Safari 14.1+, Edge 90+)
2. Kliknij dowolnie na stronie, aby odblokować `AudioContext` (wymóg przeglądarek)
3. Przeciągnij lub wgraj pliki audio (mp3, wav, ogg...)
4. Kliknij **▶ All** lub pojedynczy przycisk Play przy źródle
5. Przełącz na tryb **Eksploracja** i chodź po przestrzeni klawiszami `WASD`

### Skąd Wziąć Dźwięki?

| Biblioteka | Licencja | Charakterystyka |
|-----------|----------|-----------------|
| [Freesound.org](https://freesound.org/browse/tags/cc0/) | CC0 / CC-BY | Ogromna baza efektów i ambientów |
| [Mixkit](https://mixkit.co/free-sound-effects/) | Darmowa | Efekty dźwiękowe |
| [Pixabay Audio](https://pixabay.com/sound-effects/) | CC0 | Bez wymaganej atrybucji |
| [BBC Sound Effects](https://sound-effects.bbcrewind.co.uk/) | Osobisty | Profesjonalne nagrania terenowe |
| [Aporee.org](https://aporee.org/maps/) | CC-BY | Field recordings z całego świata |

---

## 🌐 Kompatybilność

| Przeglądarka | Wersja Min. | Status |
|-------------|------------|--------|
| Chrome / Chromium | 90+ | ✅ Pełna obsługa |
| Firefox | 90+ | ✅ Pełna obsługa |
| Safari | 14.1+ | ✅ Pełna obsługa |
| Edge | 90+ | ✅ Pełna obsługa |
| Mobile Chrome | Tak | ✅ + UI mobilne |
| Mobile Safari | iOS 14.1+ | ✅ + UI mobilne |

> ⚠️ Ze względu na **Autoplay Policy** przeglądarek, kontekst audio aktywuje się po pierwszej interakcji użytkownika (klik lub dotyk).

---

## 📁 Struktura Projektu

```
spatial-audio-lab/
├── index.html      # Cała aplikacja (self-contained, zero dependencies)
└── README.md       # Dokumentacja
```

---

*Projekt rozwijany w ramach [Spatial Audio Lab](https://github.com/spatial-audio-lab).*
