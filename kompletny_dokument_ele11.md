_Przewodnik po egzaminie ELE.11 (czerwiec 2024) dla technika energetyki odnawialnej_ # Prezentacja Egzaminacyjna: ELE.11 (Czerwiec 2024)

---

## Wprowadzenie do Egzaminu ELE.11 (Czerwiec 2024)

Egzamin zawodowy praktyczny z czerwca 2024 roku w kwalifikacji ELE.11, "Eksploatacja urządzeń i systemów energetyki odnawialnej", koncentruje się na diagnostyce i serwisowaniu słonecznej instalacji grzewczej w obiekcie hotelowym. Czas trwania egzaminu, wynoszący **180 minut**, wymaga od zdającego nie tylko wiedzy teoretycznej, ale przede wszystkim umiejętności praktycznego zastosowania wzorów, analizy danych i podejmowania decyzji w warunkach symulowanej awarii.

Kluczowe obszary weryfikowane w tym arkuszu to:
- **Analiza i identyfikacja usterek** w istniejącej instalacji słonecznej.
- **Dobór i zastosowanie przyrządów pomiarowych** do diagnostyki systemu.
- **Obliczenia sprawności kolektorów** na podstawie danych katalogowych i pomiarowych.
- **Obliczenia ciśnień w instalacji** (statycznego, wstępnego, napełniania).
- **Interpretacja wykresów** charakterystyk pracy kolektorów.

---

## Główne Obszary Tematyczne Egzaminu (Czerwiec 2024)

Arkusz egzaminacyjny z czerwca 2024 roku skupia się na kompleksowej analizie słonecznej instalacji grzewczej. Poniższa tabela przedstawia kluczowe zagadnienia, które pojawiły się w zadaniu.

| Obszar Tematyczny | Kluczowe Zagadnienia |
| :--- | :--- |
| **Diagnostyka Instalacji** | - Identyfikacja nieprawidłowości na podstawie opisu sytuacji (np. spadek temperatury c.w.u., ubytek czynnika).<br>- Wskazanie możliwych przyczyn usterek (np. przegrzanie czynnika, uszkodzenie czujnika temperatury).<br>- Dobór odpowiednich przyrządów pomiarowych (rotametr, manometr, refraktometr, pH-metr) do weryfikacji parametrów instalacji. |
| **Obliczenia Techniczne** | - Obliczanie sprawności kolektora słonecznego dla różnych różnic temperatur (ΔT) przy zadanym natężeniu promieniowania (E_g = 800 W/m²).<br>- Obliczanie ciśnienia statycznego (p_st), ciśnienia wstępnego w naczyniu przeponowym (p_wst) oraz ciśnienia napełniania (p_n) na podstawie wysokości instalacji (H).<br>- Konwersja jednostek ciśnienia (bar na MPa). |
| **Analiza Danych** | - Odczytywanie parametrów pracy kolektora (ΔT_min, ΔT_max, η_min, η_max) z wykresu charakterystyki sprawności η = f(ΔT).<br>- Porównywanie danych katalogowych kolektorów różnych serii (SV100, SV200, SV300).<br>- Rysowanie charakterystyki roboczej sprawności kolektora na podstawie obliczonych punktów. |

---

## Kluczowe Zagadnienia Matematyczne i Obliczenia (Czerwiec 2024)

Arkusz z czerwca 2024 wprowadził nowe wzory i typy obliczeń, koncentrując się na parametrach ciśnieniowych instalacji oraz analizie charakterystyk sprawności. Poniżej znajdują się szczegółowe wyjaśnienia.

### 1. Obliczenia Ciśnień w Instalacji Grzewczej

Prawidłowe ciśnienie w instalacji solarnej jest kluczowe dla jej bezpiecznej i wydajnej pracy. Egzamin wymagał obliczenia trzech podstawowych wartości ciśnienia na podstawie wysokości statycznej instalacji.

| Rodzaj Ciśnienia | Wzór | Objaśnienie |
| :--- | :--- | :--- |
| **Ciśnienie Statyczne (p_st)** | p_st = H × 0,1 | Określa ciśnienie wywierane przez słup cieczy w instalacji. **H** to wysokość w metrach od najniższego do najwyższego punktu instalacji. Współczynnik 0,1 przelicza metry słupa wody na bary. |
| **Ciśnienie Wstępne (p_wst)** | p_wst = p_st + 1,0 bar | Jest to ciśnienie azotu w naczyniu przeponowym przed napełnieniem instalacji czynnikiem. Zapewnia rezerwę ciśnienia i kompensuje zmiany objętości. Wartość 1,0 bar jest stałą wartością dodawaną w tym zadaniu. |
| **Ciśnienie Napełniania (p_n)** | p_n = p_wst + 0,3 bar | Minimalne ciśnienie, do jakiego należy napełnić zimną instalację, aby zapewnić prawidłową pracę. Wartość 0,3 bar to naddatek zapewniający odpowiednie ciśnienie w najwyższym punkcie instalacji. |

**Przykład zadania egzaminacyjnego (na podstawie arkusza):**
Oblicz wartości ciśnień dla instalacji, w której najwyższy punkt znajduje się 15 metrów powyżej naczynia przeponowego (H = 15 m).

**Rozwiązanie krok po kroku:**
1.  **Obliczenie ciśnienia statycznego (p_st):**
    p_st = 15 m × 0,1 bar/m = 1,5 bar

2.  **Obliczenie ciśnienia wstępnego (p_wst):**
    p_wst = 1,5 bar + 1,0 bar = 2,5 bar

3.  **Obliczenie ciśnienia napełniania (p_n):**
    p_n = 2,5 bar + 0,3 bar = 2,8 bar

4.  **Konwersja na megapaskale (MPa):**
    Należy pamiętać, że 1 bar = 0,1 MPa.
    - p_st = 1,5 bar = 0,15 MPa
    - p_wst = 2,5 bar = 0,25 MPa
    - p_n = 2,8 bar = 0,28 MPa

### 2. Analiza Wykresu Sprawności η = f(ΔT)

Egzamin wymagał umiejętności odczytywania danych z wykresu przedstawiającego zależność sprawności kolektora (η) od różnicy temperatur między absorberem a otoczeniem (ΔT).

**Jak czytać wykres?**
-   **Oś pionowa (Y):** Przedstawia sprawność kolektora (η) w procentach [%].
-   **Oś pozioma (X):** Przedstawia różnicę temperatur (ΔT) w Kelwinach [K] lub stopniach Celsjusza [°C].
-   **Linia charakterystyki:** Pokazuje, jak spada sprawność kolektora wraz ze wzrostem różnicy temperatur (im cieplejszy kolektor w stosunku do otoczenia, tym większe straty ciepła i niższa sprawność).

**Przykład zadania (na podstawie arkusza):**
Z wykresu dla kolektora SV300C odczytaj wartości sprawności dla ΔT_min = 40 K i ΔT_max = 60 K.

**Rozwiązanie:**
1.  **Znajdź ΔT = 40 K na osi poziomej.**
2.  **Przesuń się w górę do przecięcia z linią charakterystyki.**
3.  **Odczytaj wartość na osi pionowej.** Dla ΔT = 40 K, sprawność η wynosi około 70%.
4.  **Powtórz kroki dla ΔT = 60 K.** Dla tej wartości, sprawność η wynosi około 59%.

### 3. Obliczenia Sprawności Kolektora (zgodnie z arkuszem)

Podobnie jak w poprzednich egzaminach, kluczowym elementem było obliczenie sprawności kolektora przy użyciu wzoru, ale tym razem dla konkretnego natężenia promieniowania (E_g = 800 W/m²).

> **Wzór na sprawność kolektora:**
> η = η₀ - (k₁ · ΔT) / E_g - (k₂ · ΔT²) / E_g

**Objaśnienie symboli (zgodnie z arkuszem 2024):**
- **η₀** – sprawność optyczna (dla ΔT = 0 K).
- **k₁** – liniowy współczynnik strat ciepła [W/(m²·K)].
- **k₂** – kwadratowy współczynnik strat ciepła [W/(m²·K²)].
- **ΔT** – różnica temperatur [K].
- **E_g** – natężenie promieniowania słonecznego [W/m²].

**Przykład zadania (na podstawie arkusza dla kolektora SV300C):**
Oblicz sprawność kolektora SV300C dla ΔT = 50 K, wiedząc, że E_g = 800 W/m².
Dane katalogowe kolektora SV300C:
- η₀ = 0,868
- k₁ = 3,188 W/(m²·K)
- k₂ = 0,018 W/(m²·K²)

**Rozwiązanie krok po kroku:**
1.  **Podstawienie danych do wzoru:**
    η = 0,868 - (3,188 * 50) / 800 - (0,018 * 50²) / 800
2.  **Obliczenie strat liniowych:**
    (3,188 * 50) / 800 = 159,4 / 800 ≈ 0,199
3.  **Obliczenie strat kwadratowych:**
    (0,018 * 2500) / 800 = 45 / 800 = 0,05625
4.  **Obliczenie końcowej sprawności:**
    η = 0,868 - 0,199 - 0,05625 = 0,61275

**Odpowiedź:** Sprawność kolektora dla ΔT = 50 K wynosi około 0,613, czyli 61,3%.

---

## Analiza i Rozwiązywanie Zadań Egzaminacyjnych (Czerwiec 2024)

Przeanalizujmy teraz zadania z arkusza z czerwca 2024, koncentrując się na nowych elementach.

### Zadanie 1: Identyfikacja Przyrządów Pomiarowych

**Treść zadania (uproszczona):**
Do przedstawionych na zdjęciach przyrządów pomiarowych dopasuj ich nazwy i zastosowania w słonecznej instalacji grzewczej.

**Rozwiązanie w formie tabeli:**

| Przyrząd (Zdjęcie) | Nazwa Przyrządu | Zastosowanie w Instalacji Solarnej | Jednostka Odczytu |
| :--- | :--- | :--- | :--- |
| 1. Urządzenie z pływakiem | **Rotametr** | Pomiar natężenia przepływu czynnika roboczego | l/min lub m³/h |
| 2. Zegar z wskazówką | **Manometr** | Pomiar ciśnienia czynnika roboczego w instalacji | bar, MPa |
| 3. Paski papierowe | **Paski wskaźnikowe (lakmusowe)** | Pomiar odczynu (pH) czynnika roboczego | - (skala barwna) |
| 4. Urządzenie optyczne | **Refraktometr** | Pomiar temperatury zamarzania lub gęstości czynnika (glikolu) | °C, g/cm³ |
| 5. Sonda z wyświetlaczem | **pH-metr elektroniczny** | Precyzyjny pomiar odczynu (pH) czynnika roboczego | - (wartość pH) |

### Zadanie 2: Wskazanie Przyczyn Nieprawidłowości

**Treść zadania (uproszczona):**
Na podstawie listy stwierdzonych nieprawidłowości w instalacji grzewczej, wskaż ich możliwe przyczyny.

**Rozwiązanie w formie tabeli:**

| Nieprawidłowość | Możliwa Przyczyna |
| :--- | :--- |
| 1. Ubytek czynnika roboczego | Nieszczelność instalacji, wyciek na złączach lub odpowietrzniku. |
| 2. Brak sygnału z czujnika temperatury kolektora | Uszkodzenie czujnika, przerwa w przewodzie sygnałowym, błąd sterownika. |
| 3. Ciemne zabarwienie czynnika grzewczego | Przegrzanie i degradacja termiczna glikolu, korozja wewnętrzna instalacji. |
| 4. Wypływ czynnika przez zawór bezpieczeństwa | Zbyt wysokie ciśnienie w instalacji (np. w wyniku przegrzania), uszkodzony zawór bezpieczeństwa, zbyt małe lub uszkodzone naczynie przeponowe. |
| 5. Niska temperatura c.w.u. mimo prawidłowego ciśnienia | Zbyt mały przepływ czynnika roboczego, zapowietrzenie wymiennika ciepła w zasobniku, uszkodzenie pompy obiegowej. |
| 6. Duża różnica temperatur między kolektorem a podgrzewaczem (>40°C) | Zbyt mały przepływ czynnika roboczego, zakamienienie wymiennika ciepła, nieprawidłowe działanie pompy lub zaworów. |

---

## Podsumowanie i Wskazówki Egzaminacyjne (Czerwiec 2024)

1.  **Opanuj nowe wzory:** Skup się na wzorach dotyczących ciśnień (p_st, p_wst, p_n), ponieważ były one nowym elementem w tym arkuszu.
2.  **Ćwicz analizę wykresów:** Umiejętność szybkiego i precyzyjnego odczytywania danych z wykresów charakterystyk jest kluczowa. Zwracaj uwagę na jednostki na obu osiach.
3.  **Rozpoznawaj przyrządy pomiarowe:** Zapoznaj się z wyglądem i zastosowaniem podstawowych przyrządów używanych w technice grzewczej i solarnej.
4.  **Myśl przyczynowo-skutkowo:** Analizując usterki, staraj się łączyć objawy (np. ciemny glikol) z ich najbardziej prawdopodobnymi przyczynami (przegrzanie).
5.  **Zwróć uwagę na szczegóły w danych:** Arkusz zawierał tabele z danymi dla różnych typów kolektorów. Upewnij się, że używasz danych dla właściwego modelu (w tym przypadku SV300C).

Powodzenia na egzaminie!

---

## Podsumowanie Końcowe

Egzamin z czerwca 2024 roku stanowił doskonały przykład zadania problemowego, gdzie zdający musiał wcielić się w rolę serwisanta diagnozującego realne problemy w istniejącej instalacji. W odróżnieniu od zadań projektowych, ten arkusz kładł nacisk na umiejętności analityczne, diagnostyczne i znajomość praktycznych aspektów eksploatacji systemów solarnych.

Kluczowe kompetencje sprawdzane w tym egzaminie to:
-   **Wiedza o komponentach instalacji:** Nie tylko o kolektorach, ale również o osprzęcie takim jak naczynia przeponowe, zawory bezpieczeństwa i przyrządy pomiarowe.
-   **Zrozumienie fizyki instalacji:** Zależności między wysokością, ciśnieniem, temperaturą i sprawnością.
-   **Umiejętności diagnostyczne:** Łączenie objawów (skutków) z ich potencjalnymi przyczynami.

Solidne przygotowanie w tych obszarach jest gwarancją sukcesu na egzaminie praktycznym ELE.11.

Powodzenia!


# Dodatkowy Zbiór Zadań Egzaminacyjnych ELE.11

_Zadania oparte na schemacie i typologii z egzaminu praktycznego z czerwca 2024_

---

## Część 1: Obliczenia Ciśnień w Instalacji Solarnej

**Wzory do wykorzystania:**
- Ciśnienie statyczne: `p_st = H × 0,1` [bar]
- Ciśnienie wstępne w naczyniu: `p_wst = p_st + 1,0` [bar]
- Ciśnienie napełniania: `p_n = p_wst + 0,3` [bar]
- Przelicznik: `1 bar = 0,1 MPa`

### Zadanie 1.1

Słoneczna instalacja grzewcza została zamontowana na dachu budynku jednorodzinnego. Różnica wysokości między najwyższym punktem instalacji (kolektory) a miejscem montażu naczynia przeponowego wynosi **H = 12 metrów**. Oblicz ciśnienie statyczne (p_st), ciśnienie wstępne (p_wst) oraz ciśnienie napełniania (p_n). Wyniki podaj w barach oraz megapaskalach (MPa).

**Rozwiązanie:**
1.  **Ciśnienie statyczne (p_st):**
    `p_st = 12 m × 0,1 bar/m = 1,2 bar`
    `1,2 bar = 0,12 MPa`

2.  **Ciśnienie wstępne (p_wst):**
    `p_wst = 1,2 bar + 1,0 bar = 2,2 bar`
    `2,2 bar = 0,22 MPa`

3.  **Ciśnienie napełniania (p_n):**
    `p_n = 2,2 bar + 0,3 bar = 2,5 bar`
    `2,5 bar = 0,25 MPa`

**Odpowiedź:** Dla instalacji o wysokości 12 m, ciśnienie statyczne wynosi 1,2 bar (0,12 MPa), ciśnienie wstępne 2,2 bar (0,22 MPa), a ciśnienie napełniania 2,5 bar (0,25 MPa).

### Zadanie 1.2

Wysokość statyczna instalacji solarnej w budynku wielorodzinnym wynosi **H = 25 metrów**. Manometr zainstalowany w kotłowni wskazuje ciśnienie 2,5 bar. Sprawdź, czy ciśnienie w instalacji jest prawidłowe, obliczając teoretyczne ciśnienie napełniania.

**Rozwiązanie:**
1.  **Obliczenie ciśnienia statycznego (p_st):**
    `p_st = 25 m × 0,1 bar/m = 2,5 bar`

2.  **Obliczenie ciśnienia wstępnego (p_wst):**
    `p_wst = 2,5 bar + 1,0 bar = 3,5 bar`

3.  **Obliczenie teoretycznego ciśnienia napełniania (p_n):**
    `p_n = 3,5 bar + 0,3 bar = 3,8 bar`

**Odpowiedź:** Teoretyczne ciśnienie napełniania dla tej instalacji powinno wynosić 3,8 bar. Wskazanie manometru (2,5 bar) jest znacznie niższe, co sugeruje zbyt niskie ciśnienie w instalacji (prawdopodobnie ubytek czynnika roboczego).

### Zadanie 1.3

Serwisant odczytał z dokumentacji technicznej, że ciśnienie wstępne w naczyniu przeponowym powinno wynosić **p_wst = 1,8 bar**. Oblicz, jaka jest maksymalna wysokość statyczna (H) instalacji, dla której to naczynie zostało dobrane, oraz jakie powinno być ciśnienie napełniania (p_n).

**Rozwiązanie:**
1.  **Obliczenie ciśnienia statycznego (p_st) na podstawie p_wst:**
    `p_wst = p_st + 1,0 bar  =>  p_st = p_wst - 1,0 bar`
    `p_st = 1,8 bar - 1,0 bar = 0,8 bar`

2.  **Obliczenie wysokości statycznej (H) na podstawie p_st:**
    `p_st = H × 0,1 bar/m  =>  H = p_st / 0,1`
    `H = 0,8 bar / 0,1 bar/m = 8 metrów`

3.  **Obliczenie ciśnienia napełniania (p_n):**
    `p_n = p_wst + 0,3 bar`
    `p_n = 1,8 bar + 0,3 bar = 2,1 bar`

**Odpowiedź:** Naczynie zostało dobrane do instalacji o maksymalnej wysokości statycznej 8 metrów. Ciśnienie napełniania dla tej instalacji powinno wynosić 2,1 bar.

---

## Część 2: Obliczenia Sprawności i Analiza Wykresów

**Wzór do wykorzystania:**
- Sprawność kolektora: `η = η₀ - (k₁ · ΔT) / E_g - (k₂ · ΔT²) / E_g`

### Zadanie 2.1

Na podstawie danych katalogowych dla kolektora **SV200E**, oblicz jego sprawność roboczą dla różnicy temperatur **ΔT = 30 K** oraz **ΔT = 70 K**. Obliczenia wykonaj dla natężenia promieniowania słonecznego **E_g = 800 W/m²**. Narysuj uzyskaną charakterystykę na wykresie.

**Dane katalogowe kolektora SV200E:**
- Sprawność optyczna (η₀) = 0,827
- Liniowy współczynnik strat (k₁) = 3,721 W/(m²·K)
- Kwadratowy współczynnik strat (k₂) = 0,019 W/(m²·K²)

**Rozwiązanie:**

1.  **Obliczenie sprawności dla ΔT = 30 K:**
    `η_30K = 0,827 - (3,721 * 30) / 800 - (0,019 * 30²) / 800`
    `η_30K = 0,827 - 111,63 / 800 - (0,019 * 900) / 800`
    `η_30K = 0,827 - 0,1395 - 17,1 / 800`
    `η_30K = 0,827 - 0,1395 - 0,0214 = 0,6661`
    **Sprawność dla ΔT = 30 K wynosi 66,6%.**

2.  **Obliczenie sprawności dla ΔT = 70 K:**
    `η_70K = 0,827 - (3,721 * 70) / 800 - (0,019 * 70²) / 800`
    `η_70K = 0,827 - 260,47 / 800 - (0,019 * 4900) / 800`
    `η_70K = 0,827 - 0,3256 - 93,1 / 800`
    `η_70K = 0,827 - 0,3256 - 0,1164 = 0,385`
    **Sprawność dla ΔT = 70 K wynosi 38,5%.**

**Rysowanie charakterystyki:**
Na pustym wykresie η = f(ΔT) należy zaznaczyć trzy punkty:
- Punkt 1: (ΔT=0, η=82,7%) - sprawność optyczna
- Punkt 2: (ΔT=30, η=66,6%)
- Punkt 3: (ΔT=70, η=38,5%)
Następnie należy połączyć te punkty krzywą (lekko opadającą parabolą).

### Zadanie 2.2

Poniżej przedstawiono uproszczony wykres charakterystyki sprawności dla kolektora **SV100B**. Odczytaj z wykresu przybliżoną sprawność dla **ΔT = 20 K** i **ΔT = 80 K**. Następnie oblicz dokładną wartość sprawności dla **ΔT = 50 K** przy **E_g = 1000 W/m²**, korzystając z danych z tabeli.

**(Wykres należy sobie wyobrazić jako linię prostą dla uproszczenia, łączącą punkt (0, 75.4) i (100, 20))**

**Dane katalogowe kolektora SV100B:**
- Sprawność optyczna (η₀) = 0,754
- Liniowy współczynnik strat (k₁) = 4,15 W/(m²·K)
- Kwadratowy współczynnik strat (k₂) = 0,0114 W/(m²·K²)

**Rozwiązanie:**
1.  **Odczyt z wykresu (szacunkowy):**
    - Dla ΔT = 20 K, sprawność wynosi ok. 65-68%.
    - Dla ΔT = 80 K, sprawność wynosi ok. 30-33%.

2.  **Obliczenie sprawności dla ΔT = 50 K (E_g = 1000 W/m²):**
    `η_50K = 0,754 - (4,15 * 50) / 1000 - (0,0114 * 50²) / 1000`
    `η_50K = 0,754 - 207,5 / 1000 - (0,0114 * 2500) / 1000`
    `η_50K = 0,754 - 0,2075 - 28,5 / 1000`
    `η_50K = 0,754 - 0,2075 - 0,0285 = 0,518`
    **Dokładna sprawność dla ΔT = 50 K wynosi 51,8%.**

### Zadanie 2.3

Serwisant stwierdził, że sprawność kolektora SV300C przy natężeniu promieniowania **E_g = 900 W/m²** i różnicy temperatur **ΔT = 45 K** wyniosła **η = 60%**. Sprawdź obliczeniowo, czy wynik pomiaru serwisanta jest poprawny. Wykorzystaj dane katalogowe z poprzednich zadań.

**Dane katalogowe kolektora SV300C:**
- η₀ = 0,868
- k₁ = 3,188 W/(m²·K)
- k₂ = 0,018 W/(m²·K²)

**Rozwiązanie:**
1.  **Obliczenie teoretycznej sprawności:**
    `η_teoret. = 0,868 - (3,188 * 45) / 900 - (0,018 * 45²) / 900`
    `η_teoret. = 0,868 - 143,46 / 900 - (0,018 * 2025) / 900`
    `η_teoret. = 0,868 - 0,1594 - 36,45 / 900`
    `η_teoret. = 0,868 - 0,1594 - 0,0405 = 0,6681`

**Odpowiedź:** Teoretyczna sprawność kolektora w tych warunkach powinna wynosić około **66,8%**. Wynik pomiaru serwisanta (60%) jest znacznie niższy, co może wskazywać na problemy z instalacją, takie jak zabrudzenie powierzchni kolektora, ubytek czynnika lub jego degradacja.

---

## Część 3: Diagnostyka, Usterki i Przyrządy Pomiarowe

### Zadanie 3.1

Podczas przeglądu słonecznej instalacji grzewczej, serwisant musi skorzystać z szeregu narzędzi diagnostycznych. Uzupełnij poniższą tabelę, dopasowując nazwę przyrządu do jego zastosowania i typowej jednostki odczytu.

| Nazwa Przyrządu | Zastosowanie w Instalacji Solarnej | Jednostka Odczytu |
| :--- | :--- | :--- |
| 1. Anemometr | | m/s, km/h |
| 2. | Pomiar temperatury na powierzchni kolektora lub rur | °C |
| 3. Manometr różnicowy | | Pa, mbar |
| 4. | Pomiar natężenia prądu pompy obiegowej | A (Amper) |
| 5. Luksomierz | | lx (luks) |

**Rozwiązanie:**

| Nazwa Przyrządu | Zastosowanie w Instalacji Solarnej | Jednostka Odczytu |
| :--- | :--- | :--- |
| 1. Anemometr | Pomiar prędkości wiatru (istotne przy ocenie strat ciepła kolektora) | m/s, km/h |
| 2. **Pirometr (lub termometr kontaktowy)** | Pomiar temperatury na powierzchni kolektora lub rur | °C |
| 3. Manometr różnicowy | Pomiar spadku ciśnienia na filtrze lub pompie obiegowej | Pa, mbar |
| 4. **Miernik cęgowy (amperomierz cęgowy)** | Pomiar natężenia prądu pompy obiegowej | A (Amper) |
| 5. Luksomierz | Pomiar natężenia oświetlenia (może być użyty do szacunkowej oceny promieniowania słonecznego) | lx (luks) |

### Zadanie 3.2

Do podanych objawów nieprawidłowego działania instalacji solarnej dopisz co najmniej dwie możliwe przyczyny.

| Objaw (Skutek) | Możliwe Przyczyny |
| :--- | :--- |
| 1. Głośna, "kawitacyjna" praca pompy obiegowej | a) Zbyt niskie ciśnienie w instalacji (poniżej ciśnienia parowania czynnika).<br>b) Zapowietrzenie instalacji. |
| 2. Częste, krótkotrwałe otwieranie się zaworu bezpieczeństwa | a) Uszkodzone lub zbyt małe naczynie przeponowe (brak kompensacji objętości).<br>b) Zbyt wysokie ciśnienie napełniania instalacji. |
| 3. Kolektory są gorące, ale zasobnik c.w.u. pozostaje zimny | a) Zatrzymana lub uszkodzona pompa obiegowa.<br>b) Całkowite zapowietrzenie wymiennika ciepła w zasobniku. |
| 4. Mimo słonecznej pogody, sterownik nie uruchamia pompy | a) Uszkodzony czujnik temperatury na kolektorze (pokazuje zbyt niską temperaturę).<br>b) Przerwa w obwodzie elektrycznym czujnika lub pompy. |

### Zadanie 3.3

**Opis Sytuacji:** Właściciel domu jednorodzinnego zgłasza, że jego 5-letnia instalacja solarna działa znacznie mniej wydajnie niż w poprzednich latach. Rachunki za podgrzewanie wody gazem znacząco wzrosły. Ciśnienie na manometrze w kotłowni wydaje się być w normie.

**Polecenie:** Zaproponuj plan przeglądu serwisowego. Wymień w punktach, jakie czynności wykonasz i jakich przyrządów użyjesz, aby zdiagnozować problem.

**Rozwiązanie (Przykładowy Plan Przeglądu):**

1.  **Wywiad z użytkownikiem i weryfikacja dokumentacji:**
    -   Sprawdzenie historii serwisowej instalacji.
    -   Dopytanie o szczegóły (czy były jakieś alarmy na sterowniku, czy słychać nietypowe dźwięki).

2.  **Kontrola wizualna instalacji:**
    -   **Kolektory:** Sprawdzenie czystości powierzchni, ocena pod kątem uszkodzeń mechanicznych (np. pęknięcia szyby), kontrola szczelności połączeń.
    -   **Kotłownia:** Sprawdzenie szczelności wszystkich połączeń, ocena stanu izolacji na rurach.

3.  **Sprawdzenie parametrów czynnika roboczego:**
    -   **Przyrząd:** Refraktometr.
    -   **Czynność:** Pobranie próbki czynnika i sprawdzenie jego temperatury zamarzania. Niska odporność na zamarzanie świadczy o degradacji lub rozcieńczeniu glikolu.
    -   **Przyrząd:** Paski wskaźnikowe lub pH-metr.
    -   **Czynność:** Sprawdzenie odczynu pH czynnika. Kwaśny odczyn (pH < 7) świadczy o degradacji i może powodować korozję.

4.  **Kontrola ciśnienia i naczynia przeponowego:**
    -   **Przyrząd:** Manometr (wbudowany w instalację) oraz manometr serwisowy.
    -   **Czynność:** Porównanie ciśnienia w zimnej instalacji z obliczonym ciśnieniem napełniania. Sprawdzenie ciśnienia wstępnego w naczyniu przeponowym (po opróżnieniu części instalacji).

5.  **Weryfikacja pracy układu pompowego i sterowania:**
    -   **Przyrząd:** Termometr (pirometr), miernik cęgowy.
    -   **Czynność:** Uruchomienie instalacji w trybie ręcznym. Sprawdzenie, czy pompa pracuje (słuchowo i przez pomiar poboru prądu miernikiem cęgowym). Zmierzenie temperatury rur przed i za pompą, aby potwierdzić przepływ. Sprawdzenie wskazań czujników temperatury na sterowniku i porównanie ich z pomiarem pirometrem.

6.  **Wnioski i zalecenia:**
    -   Na podstawie zebranych informacji, sformułowanie diagnozy (np. "Zdegradowany czynnik roboczy o niskim pH i obniżonej temperaturze zamarzania, co zmniejsza wydajność cieplną i stwarza ryzyko korozji. Zalecana wymiana czynnika i płukanie instalacji.").

---
