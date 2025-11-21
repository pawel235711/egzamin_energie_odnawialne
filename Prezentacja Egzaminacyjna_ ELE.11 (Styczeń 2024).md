# Prezentacja Egzaminacyjna: ELE.11 (Styczeń 2024)

_Przewodnik po egzaminie ELE.11 (styczeń 2024) dla technika energetyki odnawialnej_

---

## Wprowadzenie do Egzaminu ELE.11 (Styczeń 2024)

Egzamin zawodowy praktyczny ze stycznia 2024 roku w kwalifikacji ELE.11, "Eksploatacja urządzeń i systemów energetyki odnawialnej", skupiał się na diagnostyce i analizie problemów w istniejącej instalacji fotowoltaicznej. Zadanie egzaminacyjne symulowało realną sytuację serwisową, w której zdający musiał zlokalizować zwarcie, ocenić parametry pracy modułów oraz zidentyfikować nieprawidłowości na podstawie dokumentacji fotograficznej i pomiarów.

Kluczowe kompetencje weryfikowane w tym arkuszu to:
- **Lokalizacja usterek** w szeregu modułów fotowoltaicznych na podstawie pomiarów napięcia.
- **Analiza parametrów pracy falownika** i interpretacja komunikatów o błędach.
- **Obliczenia kluczowych wskaźników** modułu PV, takich jak współczynnik wypełnienia (FF) i sprawność (η).
- **Identyfikacja nieprawidłowości** na podstawie dokumentacji fotograficznej (np. hot-spoty, delaminacja, uszkodzenia mechaniczne).
- **Znajomość norm i wytycznych** dotyczących montażu i eksploatacji instalacji fotowoltaicznych.

---

## Główne Obszary Tematyczne Egzaminu (Styczeń 2024)

Arkusz egzaminacyjny ze stycznia 2024 koncentrował się na kompleksowej diagnostyce instalacji fotowoltaicznej. Poniższa tabela przedstawia kluczowe zagadnienia, które pojawiły się w zadaniu.

| Obszar Tematyczny | Kluczowe Zagadnienia |
| :--- | :--- |
| **Diagnostyka Elektryczna** | - Lokalizowanie miejsca zwarcia doziemnego w szeregu modułów PV przy użyciu pomiarów napięć (U+, U-).<br>- Analiza komunikatów o błędach falownika (np. `GridV.OutLim`) i dobór odpowiednich procedur serwisowych.<br>- Weryfikacja parametrów sieci AC (napięcie, częstotliwość) i porównanie ich z normami. |
| **Obliczenia Parametrów PV** | - Obliczanie współczynnika wypełnienia (FF) na podstawie charakterystyki prądowo-napięciowej modułu.<br>- Obliczanie rzeczywistej sprawności modułu (η) i porównywanie jej z wartością deklarowaną przez producenta.<br>- Wykorzystanie danych z tabeli pomiarowej (charakterystyka I-V) do znalezienia punktu mocy maksymalnej (MPP). |
| **Analiza Usterek Wizualnych** | - Rozpoznawanie typowych uszkodzeń modułów fotowoltaicznych na podstawie zdjęć (hot-spot, delaminacja, zabrudzenia, uszkodzenia mechaniczne).<br>- Identyfikacja błędów montażowych (np. nieprawidłowy montaż falownika, uszkodzone konektory).<br>- Proponowanie sposobów usunięcia zidentyfikowanych nieprawidłowości. |
| **Wiedza o Normach i Konserwacji** | - Znajomość wytycznych dotyczących przeglądów, konserwacji i eksploatacji instalacji PV.<br>- Dobór odpowiednich procedur czyszczenia i kontroli stanu technicznego komponentów. |

---

## Kluczowe Zagadnienia Matematyczne i Obliczenia (Styczeń 2024)

Arkusz ze stycznia 2024 roku wymagał od zdających praktycznego zastosowania wzorów do oceny stanu technicznego instalacji fotowoltaicznej. Poniżej znajdują się szczegółowe wyjaśnienia kluczowych obliczeń.

### 1. Lokalizacja Zwarcia Doziemnego w Szeregu Modułów

Jednym z kluczowych zadań była lokalizacja zwarcia doziemnego w łańcuchu 5 modułów połączonych szeregowo. Do tego celu wykorzystano pomiary napięć między biegunami a ziemią (U+ i U-) oraz napięcie całego szeregu (UDC).

> **Wzór na lokalizację zwarcia (od strony bieguna dodatniego):**
> n+ = (U+ / UDC) * n

**Objaśnienie symboli:**
- **n+** – numer modułu (licząc od strony bieguna dodatniego), przy którym wystąpiło zwarcie.
- **U+** – napięcie zmierzone pomiędzy dodatnim biegunem szeregu a uziemieniem [V].
- **UDC** – napięcie całkowite szeregu modułów (napięcie obwodu otwartego) [V].
- **n** – całkowita liczba modułów w szeregu.

**Przykład zadania egzaminacyjnego (na podstawie arkusza):**
Zlokalizuj zwarcie w szeregu 5 modułów, wiedząc, że pomiary dały następujące wyniki:
- U+ = 90 V
- U- = 135 V
- UDC = 225 V (co jest sumą U+ i U-)
- n = 5

**Rozwiązanie krok po kroku:**
1.  **Podstawienie danych do wzoru:**
    `n+ = (90 V / 225 V) * 5`

2.  **Obliczenie stosunku napięć:**
    `90 / 225 = 0,4`

3.  **Obliczenie numeru modułu:**
    `n+ = 0,4 * 5 = 2`

**Wniosek:** Zwarcie znajduje się za drugim modułem, licząc od strony bieguna dodatniego, czyli **pomiędzy modułem nr 2 a modułem nr 3**.

### 2. Obliczanie Współczynnika Wypełnienia (Fill Factor - FF)

Współczynnik wypełnienia jest kluczowym parametrem określającym "jakość" charakterystyki prądowo-napięciowej modułu fotowoltaicznego. Im wyższy FF (bliższy jedności), tym bardziej "prostokątna" jest charakterystyka i tym wyższa jest sprawność modułu.

> **Wzór na współczynnik wypełnienia (FF):**
> FF = (Impp * Umpp) / (Isc * Uoc)

**Objaśnienie symboli:**
- **Impp** – prąd w punkcie mocy maksymalnej [A].
- **Umpp** – napięcie w punkcie mocy maksymalnej [V].
- **Isc** – prąd zwarcia (dla U=0V) [A].
- **Uoc** – napięcie obwodu otwartego (dla I=0A) [V].

**Przykład zadania (na podstawie danych z arkusza):**
Oblicz współczynnik wypełnienia FF dla modułu, którego charakterystykę prądowo-napięciową przedstawiono w tabeli pomiarowej.

**Dane odczytane z tabeli:**
- Punkt mocy maksymalnej (MPP): **Impp = 7,61 A**, **Umpp = 18,38 V** (wiersz, gdzie moc jest największa).
- Prąd zwarcia (Isc): **8,10 A** (dla U=0V).
- Napięcie obwodu otwartego (Uoc): **22,90 V** (dla I=0A).

**Rozwiązanie krok po kroku:**
1.  **Obliczenie mocy maksymalnej (Pmpp):**
    `Pmpp = 7,61 A * 18,38 V = 139,87 W`

2.  **Obliczenie mocy teoretycznej (Pteoret):**
    `Pteoret = 8,10 A * 22,90 V = 185,49 W`

3.  **Obliczenie współczynnika FF:**
    `FF = 139,87 W / 185,49 W ≈ 0,754`

**Wniosek:** Obliczony współczynnik wypełnienia wynosi **0,75**, co jest zgodne z wartością deklarowaną przez producenta (0,75).

### 3. Obliczanie Sprawności Modułu Fotowoltaicznego (η)

Sprawność modułu określa, jaka część energii słonecznej padającej na jego powierzchnię jest konwertowana na energię elektryczną.

> **Wzór na sprawność modułu (η):**
> η = Pmax / (E * S)

**Objaśnienie symboli:**
- **η** – sprawność modułu (wartość bezwymiarowa).
- **Pmax** – moc maksymalna modułu w warunkach STC [W].
- **E** – natężenie promieniowania słonecznego w warunkach STC (standardowo **1000 W/m²**).
- **S** – powierzchnia modułu [m²].

**Przykład zadania (na podstawie danych z arkusza):**
Oblicz sprawność modułu o mocy maksymalnej 140 W i wymiarach podanych na rysunku.

**Dane z arkusza:**
- Moc maksymalna (Pmax) z tabeli pomiarowej: **139,87 W** (wartość obliczona, w zadaniu można też przyjąć P_mpp = 140 W z danych ogólnych).
- Wymiary modułu: 1130 mm x 670 mm.
- Natężenie promieniowania (E): 1000 W/m² (standardowe warunki testowania - STC).

**Rozwiązanie krok po kroku:**
1.  **Przeliczenie wymiarów na metry:**
    `1130 mm = 1,13 m`
    `670 mm = 0,67 m`

2.  **Obliczenie powierzchni modułu (S):**
    `S = 1,13 m * 0,67 m = 0,7571 m²`

3.  **Podstawienie danych do wzoru na sprawność:**
    `η = 139,87 W / (1000 W/m² * 0,7571 m²)`

4.  **Obliczenie sprawności:**
    `η = 139,87 / 757,1 ≈ 0,1847`

**Wniosek:** Obliczona sprawność modułu wynosi około **0,18** (czyli 18%), co jest zgodne z wartością deklarowaną przez producenta (0,18).

---


# Dodatkowy Zbiór Zadań Egzaminacyjnych ELE.11 (Styczeń 2024)

_Zadania oparte na schemacie i typologii z egzaminu praktycznego ze stycznia 2024_

---

## Część 1: Lokalizacja Zwarcia Doziemnego w Szeregu Modułów

**Wzór do wykorzystania:** `n+ = (U+ / UDC) * n`

### Zadanie 1.1

W instalacji fotowoltaicznej składającej się z **8 modułów** połączonych szeregowo (n=8) doszło do zwarcia doziemnego. Pomiary wykonane przez serwisanta dały następujące wyniki:
- Napięcie między biegunem dodatnim a ziemią: **U+ = 120 V**
- Napięcie między biegunem ujemnym a ziemią: **U- = 120 V**
- Napięcie całkowite szeregu: **UDC = 240 V**

Zlokalizuj, pomiędzy którymi modułami wystąpiło zwarcie.

**Rozwiązanie:**
1.  **Podstawienie danych do wzoru:**
    `n+ = (120 V / 240 V) * 8`
2.  **Obliczenie stosunku napięć:**
    `120 / 240 = 0,5`
3.  **Obliczenie numeru modułu:**
    `n+ = 0,5 * 8 = 4`

**Odpowiedź:** Zwarcie znajduje się za czwartym modułem, licząc od strony bieguna dodatniego, czyli **pomiędzy modułem nr 4 a modułem nr 5**.

### Zadanie 1.2

Instalacja PV składa się z **10 modułów** (n=10). Zmierzono napięcie **U+ = 60 V** oraz napięcie całego szeregu **UDC = 300 V**. Gdzie znajduje się zwarcie?

**Rozwiązanie:**
1.  **Podstawienie danych do wzoru:**
    `n+ = (60 V / 300 V) * 10`
2.  **Obliczenie stosunku napięć:**
    `60 / 300 = 0,2`
3.  **Obliczenie numeru modułu:**
    `n+ = 0,2 * 10 = 2`

**Odpowiedź:** Zwarcie znajduje się za drugim modułem, licząc od strony bieguna dodatniego, czyli **pomiędzy modułem nr 2 a modułem nr 3**.

### Zadanie 1.3

W szeregu składającym się z **6 modułów** (n=6) zwarcie wystąpiło za piątym modułem (pomiędzy modułem 5 a 6). Jakiego wyniku pomiaru napięcia **U+** powinien spodziewać się serwisant, jeśli napięcie całego szeregu **UDC wynosi 180 V**?

**Rozwiązanie:**
1.  **Przekształcenie wzoru:**
    `n+ = (U+ / UDC) * n  =>  U+ = (n+ / n) * UDC`
2.  **Podstawienie danych:**
    - `n+ = 5` (zwarcie jest *za* piątym modułem)
    - `n = 6`
    - `UDC = 180 V`
3.  **Obliczenie napięcia U+:**
    `U+ = (5 / 6) * 180 V`
    `U+ = 0,8333... * 180 V ≈ 150 V`

**Odpowiedź:** Serwisant powinien spodziewać się wyniku pomiaru **U+ około 150 V**.

---

## Część 2: Obliczanie Współczynnika Wypełnienia (FF) i Sprawności (η)

**Wzory do wykorzystania:**
- `FF = (Impp * Umpp) / (Isc * Uoc)`
- `η = Pmax / (E * S)`

### Zadanie 2.1

Na podstawie poniższej, uproszczonej charakterystyki prądowo-napięciowej modułu PV, oblicz jego współczynnik wypełnienia (FF).

- Prąd zwarcia (Isc) = **9,0 A**
- Napięcie obwodu otwartego (Uoc) = **40,0 V**
- Prąd w punkcie mocy maksymalnej (Impp) = **8,2 A**
- Napięcie w punkcie mocy maksymalnej (Umpp) = **33,0 V**

**Rozwiązanie:**
1.  **Obliczenie mocy maksymalnej (Pmpp):**
    `Pmpp = 8,2 A * 33,0 V = 270,6 W`
2.  **Obliczenie mocy teoretycznej (Pteoret):**
    `Pteoret = 9,0 A * 40,0 V = 360,0 W`
3.  **Obliczenie współczynnika FF:**
    `FF = 270,6 W / 360,0 W = 0,7516`

**Odpowiedź:** Współczynnik wypełnienia dla tego modułu wynosi około **0,75**.

### Zadanie 2.2

Oblicz sprawność modułu fotowoltaicznego o wymiarach **1,65 m x 0,99 m**, którego moc maksymalna w warunkach STC (E = 1000 W/m²) wynosi **Pmax = 310 W**.

**Rozwiązanie:**
1.  **Obliczenie powierzchni modułu (S):**
    `S = 1,65 m * 0,99 m = 1,6335 m²`
2.  **Podstawienie danych do wzoru na sprawność:**
    `η = 310 W / (1000 W/m² * 1,6335 m²)`
3.  **Obliczenie sprawności:**
    `η = 310 / 1633,5 ≈ 0,1897`

**Odpowiedź:** Sprawność modułu wynosi około **0,19** (czyli 19%).

### Zadanie 2.3

Moduł fotowoltaiczny o sprawności **η = 20%** i powierzchni **S = 1,8 m²** jest testowany w warunkach STC (E = 1000 W/m²). Jego napięcie obwodu otwartego **Uoc = 48 V**, a prąd zwarcia **Isc = 9,5 A**. Oblicz jego współczynnik wypełnienia (FF).

**Rozwiązanie:**
1.  **Obliczenie mocy maksymalnej (Pmax) na podstawie sprawności:**
    `η = Pmax / (E * S)  =>  Pmax = η * E * S`
    `Pmax = 0,20 * 1000 W/m² * 1,8 m² = 360 W`
2.  **Obliczenie mocy teoretycznej (Pteoret):**
    `Pteoret = Isc * Uoc = 9,5 A * 48 V = 456 W`
3.  **Obliczenie współczynnika FF:**
    `FF = Pmax / Pteoret = 360 W / 456 W ≈ 0,789`

**Odpowiedź:** Współczynnik wypełnienia tego modułu wynosi około **0,79**.

---

## Część 3: Diagnostyka, Usterki i Analiza Danych

### Zadanie 3.1

Falownik w instalacji fotowoltaicznej zgłasza błąd `GridV.OutLim`, co oznacza, że napięcie w sieci AC jest poza dopuszczalnym zakresem. Zgodnie z Rozporządzeniem Ministra Klimatu i Środowiska, dopuszczalny zakres napięcia w sieci wynosi od 0,85 Un do 1,1 Un. Znamionowe napięcie sieci (Un) to 230 V.

Serwisant zmierzył napięcie w gniazdku i wyniosło ono **255 V**. Czy pomiar potwierdza przyczynę błędu? Uzasadnij odpowiedź obliczeniami.

**Rozwiązanie:**
1.  **Obliczenie górnej granicy dopuszczalnego napięcia:**
    `Umax = 1,1 * Un = 1,1 * 230 V = 253 V`

2.  **Porównanie wyniku pomiaru z granicą:**
    `255 V > 253 V`

**Odpowiedź:** Tak, pomiar potwierdza przyczynę błędu. Zmierzone napięcie **255 V** jest wyższe niż maksymalne dopuszczalne napięcie w sieci, które wynosi **253 V**. Falownik prawidłowo się wyłączył, aby chronić siebie i sieć.

### Zadanie 3.2

Do podanych na zdjęciach (hipotetycznych) usterek w instalacji fotowoltaicznej dopasuj ich nazwy oraz zaproponuj sposób usunięcia.

| Zdjęcie (Opis) | Nazwa Nieprawidłowości | Sposób Usunięcia |
| :--- | :--- | :--- |
| 1. Ciemne, okrągłe plamy widoczne na module w kamerze termowizyjnej. | **Hot-spot (gorący punkt)** | Wymiana modułu (usterka nieodwracalna). |
| 2. Widoczne pęcherze powietrza i odspojenie folii na tylnej stronie modułu. | **Delaminacja** | Wymiana modułu (usterka postępująca, prowadzi do korozji). |
| 3. Gruba warstwa ptasich odchodów na powierzchni kilku modułów. | **Zabrudzenie instalacji** | Umycie modułów wodą demineralizowaną i miękką szczotką. |
| 4. Falownik zamontowany w nasłonecznionym miejscu, bez przestrzeni wentylacyjnej. | **Nieprawidłowy montaż falownika** | Przeniesienie falownika w chłodne, zacienione miejsce z zachowaniem wymaganych odstępów montażowych. |
| 5. Stopiony i nadpalony plastikowy element łączący dwa przewody. | **Uszkodzony konektor (złącze MC4)** | Odcięcie uszkodzonych konektorów i zaciśnięcie nowych, z zachowaniem prawidłowej polaryzacji. |

### Zadanie 3.3

Zgodnie z normą PN-HD 60364-6, minimalna wymagana rezystancja izolacji dla obwodu o napięciu **do 500 V** wynosi **1 MΩ**. Podczas przeglądu instalacji o napięciu Uoc = 450 V, serwisant zmierzył rezystancję izolacji między przewodami DC a uziemieniem, uzyskując wyniki:
- R_iso (DC+/PE) = **0,8 MΩ**
- R_iso (DC-/PE) = **1,2 MΩ**

Czy stan izolacji instalacji jest prawidłowy? Uzasadnij odpowiedź.

**Odpowiedź:** Stan izolacji instalacji **jest nieprawidłowy**. Mimo że rezystancja izolacji między biegunem ujemnym a ziemią (1,2 MΩ) jest w normie, to rezystancja zmierzona między biegunem dodatnim a ziemią (**0,8 MΩ**) jest niższa niż minimalna wymagana wartość **1 MΩ**. Świadczy to o uszkodzeniu izolacji po stronie dodatniej i wymaga natychmiastowej interwencji serwisowej.

---
