## Google I/O 2019
## Czy jest się czego bać?

---
### Aplikacje Google

- Podgląd modeli 3d w aplikacji Google z poziomu wyszukiwania |
- Dodatkowe możliwości Google Lens |
- Wypełnianie formularzy przez Google Asisstant |
- Dostępność Google Assistant offline |
- Incognito mode w kolejnych aplikacjach (mapy, yt) |

---

## Bubbles
- Jednolite API do budowania okien rysujących się nad UI systemu (jak w przypadku Massengera) |
- Ułatwi implementacje tego typu zachować w aplikacji |
- W Androidzie Q tylko jako opcjonalne API (dostepne w Dev opcjach) |
- Stare api (System Alert Window) zostanie w przyszłości oznaczone jako przestarzałe i za pare lat usunięte |

+++?image=images/bubbles4.png&size=auto 80%

+++?image=images/bubbles3.png&size=auto 80%

---

## Ciemny motyw
- Android Q wprowadza możliwość wybrania w systemie opcji motywu (ciemny oraz jasny) |
- Będzie to traktowane jako Configuration change |
- Settings & Quick Setting |
- Dodana zostanie opcje wymuszenia ciemnego motywy aplikacji przez inwersje (zazwyczaj) kolorów |
- Wsparcie dla poprzednich wersji systemu poprzez DayNight w AppCompat oraz Material components |

+++?image=images/dark-theme.png&size=auto 80%

+++

## Do rozważenia
- Opcja wymuszenia ciemnego motywu pozwala na to zarówno developerom jak i użytkownikom, czy powinniśmy zatem zawsze mieć na uwadze dwa warianty kolorystyczne? |
- Wsparcie dla fluttera pojawia sie równocześnie z Androidem |
- Zaleca sie 3 opcje w aplikacji Light, Dark i System (Q+) / Battery (<=P) |
- Jeszcze większy nacisk na poprawne wykorzystanie motywów i atrybutów w aplikacjach |

+++ 

## Elevation w Dark theme (oś Z)
- Zwrócono uwage na wysokość elementów narzucaną przez Material Design i problem z wyświetlaniem cienia w ciemnym motywie |
- Naturalnym rozwiązaniem tego problemu ma być elevation overlay |
- Elevation overlay ma rozjaśniać tło elementu z siłą efektu równą wysokości |
- MDC od wersji 1.1 wspiera takie zachowanie |
+++
![elevation](https://storage.googleapis.com/spec-host-backup/mio-design%2Fassets%2F1MHUUJUUsP5V7UUaeeVrgzOuJ6r4FFlIG%2Fdarktheme-light-dark-elevation.mp4)

--- 
### Nawigacja gestami

- W Androidzie 10 nawigacja w końcu została jawnie podzielona na dwie opcje |
- Nawigacja standardowa trzy przyciskowa będzie jedną z opcji nawigacji dla Androida Q+ i standardem dla wersji < Q |
- Nową opcją nawigacji będą gesty |
- Swipe left i right dla cofania -> system przechwytuje teraz dotyk przy krawędziach ekranu (do wyłączenia). |
- Swipe z dołu urządzenia w celu wywołania managera zadań lub wyjścia do ekranu głównego (zależy od siły). Niemożliwe do wyłączenia |

+++?image=images/gestureEdges.PNG&size=auto 80%

+++

### Wpływ na design i development
- Aby utworzyć jak najlepsze doświadczenie dla użytkowników zaleca się tworzenia interfejsów użytkownika od krawędzi do krawędzi |
- Uwzględnia to status bar a także navigation bar. Należy pamietać aby widoki pozwalające na interakcje odsunąć od tych miejsc |
- Gesty wysuwania z dołu bardzo podobne do iOS (takżę wizualnie) |
- Uważać na krawędzie boczne podczas tworzenia widoków |
- Aktualizacja bibliotek jest ważniejsza niż kiedykolwiek |

---

## Mniejsze zmiany

- Nowy wygląd i działanie Share (wyswietla co udostępniamy itd. (screen)) |
- Separacja sekcji powiadomień na te ważne i mniej ważne (dostępna do ustawienia dla usera) |
- Hyphenation już nie będzie włączona by default (regres od api 23) |
- Android ART przyśpieszy start aplikacji o 15% na nowej wersji |
- Generational Garbage Collector (podział na young collect (częstszy) i full-heap collection (stary)) | 
- TLS 1.3 domyślnie włączony |
+++
- Możliwość zapisania do PowerManagera na powiadomienie o zbyt wysokiej temperaturze 
- Przyśpieszenie możliwości ML na androidzie |
- Dostęp do HardwareRenderer |
- Settings Panel |
- Podejście kotlin first w bibliotekach |
- Apply changes zastąpi Instant Run |

---
## Jetpack w skrócie

- Do przestarzałych api dołącza android.preferences |
- Biblioteki Android w wersjach 1.xx będą dostawały coraz mniej aktualizacji |
- WorkManager otrzymuje wersje 2.0.1/1.01 |
- Navigation 1.0/2.0 stable |
- Nowe biblioteki: Benchmarking, Security, VM Saved State i inne |
- ViewBindings i ViewPager2 (na recyclerze) |

+++
## Work manager
- Możliwość ręcznej inicjalizacji |
- Nadchodzi integracja z Google play services (lepsza wydajność na API<23) |
- Wsparcie dla testów w Robolectric |
- Wsparcie dla ForegroundService dla dłuższych tasków (obecnie max = 10min) |
+++

### Navigation Component

- (Wersja 2.1) dodano nowy scope view modeli - per navigation graph 
- (Wersja 2.1) dodano nowy destination w navigation graph - dialogi |
- Uzuełniono sporą część dokumentacji (naprawde) |
- Zapowiedziano (koniec roku) Dynamic Feature Navigation (nawigacja w modułowych projektach) |
- Trwa zmiana fragmentów i bibliotek, od których zależy nawigacja tak aby ją rozbudować |

---
+++ 
## CameraX

- Nowa biblioteka mająca uprościć korzystanie z Aparatu |
- Ma pozwolić na korzystanie z zaawansowanych możliwości urządzeń jak Night Mode, HDR itp. |
- Dodatkowe uproszczenia uwzględniają Preview, Analize obrazu oraz zapis zdjęć |

+++ 
### Jetpack Compose
- Google dostrzegło problem tworzenia UI na androidzie |
- Nowy system zakłada deklaratywne tworzenie layoutów poprzez funkcje pisane w Kotlinie |
- Całość bardzo przypomina system zaprezentowany w Flutterze |
- W tym momencie dostępne tylko w AOSP |

+++

### Security 

- Zaprezentowano Adiantum - szyfrowanie dla urzadzeń Low End |
- 100% urządzeń wchodzących na rynek z Androidem Q będzie wspierało szyfrowanie |
- Nowa biblioteka androidx.security ma ułatwić szyfrowanie danych przez aplikacje (np. shared prefs)|
- Zmiany w Biometric prompt |
- Android 7+ z certyfikatem FIDO2 |

---
## Nowości w Google Play

- Możliwość aktualizacji wewnątrz aplikacji |
- Wymuszanie aktualizacji z poziomu konsoli (i troche kodu) |
- Statystyki / raport zmian wielkości APK |
- Internal AppSharing - nie wymaga version code, podpisu itd. |

---
## Android studio
- 3.5 skupia sie na poprawie wydajności i poprawie błędów |
- Poprawiona obsługa DataBinding |
- Wskazówki dotyczace optymalizacji dzialania (zwiekszenie ilości ramu, wykluczenie antywirusa) |

--- 
## Flutter
- Technical preview Flutter for Web |
- Dart v2.3
- Zapowiedź nowych elementów języka Nullable types oraz Extension methods |

+++
### Nowe elementy Dart 2.3


---
## Podsumowanie
- I/O sprzeczności developerskich z jednej strony uproszczenia a z drugiej jeszcze większe komplikacje |
- Duży nacisk na deklaratywne tworzenie UI |
- Poprawa bieżących mechanizmów |
- Podwyższanie min Api w celu skorzystania z bibliotek Jetpack (security - 23+) |
