# **Spatial Audio Explorer**

Interaktywne środowisko przeglądarkowe do symulacji i badania akustyki przestrzennej. Narzędzie wykorzystuje standard **Web Audio API** oraz modelowanie **HRTF** (Head-Related Transfer Function) do precyzyjnej lokacji źródeł dźwięku w przestrzeni dwuwymiarowej z odwzorowaniem sferycznym.

## **Kluczowe funkcjonalności**

* **Renderowanie przestrzenne:** Pełna implementacja węzłów PannerNode oraz AudioListener, umożliwiająca analizę zmian natężenia i barwy dźwięku w zależności od pozycji (![][image1]) oraz rotacji słuchacza.  
* **Architektura dwutrybowa:**  
  * **Tryb Projektowy (Edit):** Precyzyjne rozmieszczanie źródeł sygnału w przestrzeni laboratoryjnej.  
  * **Tryb Eksploracji (Explore):** Interaktywna weryfikacja sceny dźwiękowej z perspektywy użytkownika końcowego.  
* **Monitorowanie parametrów:** Podgląd współrzędnych geograficznych oraz kąta orientacji w czasie rzeczywistym (HUD).  
* **Analiza dystansu:** Wizualizacja tłumienia sygnału zgodnie z modelem fizycznym inverse distance.

## **Zastosowanie**

Projekt służy jako platforma do:

1. Prototypowania systemów audio w środowiskach wirtualnych.  
2. Badań nad percepcją dźwięku przestrzennego.  
3. Tworzenia dynamicznych opraw akustycznych dla gier i symulacji RPG.  
4. Edukacji w zakresie inżynierii dźwięku i akustyki cyfrowej.

## **Specyfikacja sterowania**

| **Interakcja** | **Funkcja** |

| **W, A, S, D** | Translacja pozycji słuchacza w osiach X/Y |

| **Q, E** | Manipulacja rotacją (azymut słuchacza) |

| **LPM (Mapa)** | Definiowanie wektora ruchu do celu |

| **Przeciąganie (Explore)** | Zmiana orientacji wektora patrzenia |

| **Przeciąganie (Edit)** | Relokacja wybranych źródeł sygnału |

| **Spacja** | Kontrola stanu odtwarzania (Play/Pause) |

## **Architektura techniczna**

Aplikacja jest w pełni autonomiczna i nie wymaga zewnętrznych zależności (Zero-dependency):

* **Web Audio API:** Silnik przetwarzania sygnałów i renderowania 3D.  
* **HTML5 Canvas:** System wizualizacji wektorowej środowiska.  
* **Vanilla JavaScript (ES6+):** Zarządzanie stanem i obsługa zdarzeń.

## **Uruchomienie projektu**

1. Sklonuj repozytorium:  
   git clone \[https://github.com/spatial-audio-lab/audio-explorer.git\](https://github.com/spatial-audio-lab/audio-explorer.git)

2. Otwórz plik index.html w środowisku zgodnym z Web Audio API (Chrome 60+, Firefox 55+, Edge 79+).  
3. **Uwaga:** Ze względów bezpieczeństwa (Autoplay Policy), interakcja ze stroną jest wymagana do zainicjowania kontekstu audio.

*Projekt rozwijany w ramach Spatial Audio Lab.*

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEEAAAAZCAYAAABuKkPfAAAC6UlEQVR4Xu2Xv2sUURDH9zCCoqCF55H7sXs/sDhUVA4ExTKgQbAwjWBhaXOFWGhr43+QSisRUTCQQrCJhRgLsRBTxIAgkRBIJcGARRA9v9/beeHtZPdufwkp9gPD3puZNzs7b/a9PccpKCgoiKDValU8zxso+eW6bg/XLuSHsv3WMcKoVCqH4PtGzaVM237NZvO29rHtScDchzpWiATuH6DRaJyCwybkOYYTRo/xDOSL5ZoYzN+QBOa0rd1uH4F+odfr7de2JMiibek4WGQPtq+wPdK2MCZYABaCBaECAc4zAK/aOQkSl0XYsPVMislRbH0akOd9dNU7WycFHnYjf9u2SBDkiiTb5xjXVchV7ZcUxL0hcQOtjsTvQbcQO8EIEP8A4swzf1tvCsCFtPVjMclCtjEsaXtKSog3y7h2l2XtsBGUpMCbqe7BiVK9F9qWBemyv5A+31OwpH1ywhSACzmjjbHAxE8SYF3bsiCn0AoSXMN1lYlqnzzgg0P+UJwUnTysoKzSBxYi67uqkeNwhQXRtjxg68sCBk4CjLvVavWY7RvGsABI8iMHmNRnMOguaccMcF945vnH5M4RnBdcPDkKn/IbxbZBd9MZ1xWe30JLDCRj85E064ybHBOuBOItsxu0LSujjsJ6vX4Q+te2bhdwuBi2g+rjMgw557nZsVgjV1dehUGctjTIww0w9462GSQHdu0a/M7aNuimPH+j3/WRRvbJF+JjCXCSOmNEsKOQy1KEz6jm6bCvLdgmxYdd09V2wnm4Vwf2RXmgZqfTOe5Y94vC9b8CGX85onjmJNjGPa5JPpPI9wRuc0vmUvg6BIFy2nKgrENatJXL5cP4/VbZWagpHUdWgTvxT8gFbSfQ39WxIN/ibI7SCYz/3byqNtCdgW0rJL4tO8/235B3/RWqX9O2PPD8/eklF0fb9gxI8Dpa74kzZk9Ii+v/J3ig9XsKFOE95JzW5wViL9ZqtbrWFxQUFBTkzD9lHgJCvLn6xwAAAABJRU5ErkJggg==>