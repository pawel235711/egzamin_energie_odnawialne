# Kompletny Zestaw Zadań Egzaminacyjnych ELE.11 (Styczeń 2022)

_Zadania oparte na schemacie i typologii z egzaminu praktycznego ze stycznia 2022_

---

## Wprowadzenie do Egzaminu ELE.11 (Styczeń 2022)

Egzamin zawodowy praktyczny ze stycznia 2022 roku w kwalifikacji ELE.11, "Eksploatacja urządzeń i systemów energetyki odnawialnej", koncentrował się na **analizie i ocenie parametrów pracy istniejącej słonecznej instalacji grzewczej**. W odróżnieniu od arkuszy projektowych, ten egzamin sprawdzał umiejętności obliczeniowe i diagnostyczne na podstawie dostarczonych danych pomiarowych i katalogowych.

Zadanie polegało na obliczeniu kluczowych parametrów pracy instalacji, takich jak ciśnienia, przepływy, zapotrzebowanie na ciepło i powierzchnia kolektorów, a następnie na ich ocenie i sformułowaniu zaleceń dla użytkownika. Był to kompleksowy test wiedzy z zakresu eksploatacji i analizy systemów solarnych.

Kluczowe kompetencje weryfikowane w tym arkuszu to:
- **Obliczanie parametrów hydraulicznych instalacji** (ciśnienie napełniania, ciśnienie wstępne, przepływ).
- **Obliczanie zapotrzebowania na ciepło** (netto i całkowite).
- **Obliczanie wymaganej powierzchni kolektorów** słonecznych.
- **Porównywanie wartości obliczonych z rzeczywistymi** i ocena poprawności działania instalacji.
- **Identyfikacja elementów instalacji** i ich funkcji.
- **Formułowanie zaleceń eksploatacyjnych** dla użytkownika.

---

## Kluczowe Zagadnienia Matematyczne i Obliczenia (Styczeń 2022)

Arkusz ze stycznia 2022 roku wymagał wykonania szeregu obliczeń w celu weryfikacji poprawności działania instalacji. Poniżej znajdują się szczegółowe wyjaśnienia kluczowych wzorów i obliczeń.

### 1. Obliczenia Ciśnień w Instalacji Grzewczej

- **Ciśnienie napełniania instalacji (Psol1):** Jest to ciśnienie, do jakiego należy napełnić zimną instalację. Zależy od wysokości hydrostatycznej (różnicy wysokości między najwyższym punktem instalacji a naczyniem przeponowym).
  > `Psol1 = 1,5 bar + 0,1 * Hhyd`
  > _Gdzie 1,5 bar to ciśnienie bazowe, a 0,1 bar to przyrost ciśnienia na każdy metr wysokości._

- **Ciśnienie wstępne w naczyniu przeponowym (Pn1):** To ciśnienie powietrza w naczyniu, które kompensuje zmiany objętości płynu solarnego pod wpływem temperatury. Musi być niższe od ciśnienia napełniania o co najmniej 0,3 bar, aby zapewnić rezerwę wodną.
  > `Psol1 ≥ Pn1 + 0,3 bar`

### 2. Obliczenia Przepływu i Zapotrzebowania na Ciepło

- **Całkowity przepływ w instalacji (Vkol):** Suma przepływów przez wszystkie kolektory połączone równolegle.
  > `Vkol = Skol * Lkol`
  > _Gdzie Skol to strumień przepływu przez jeden kolektor, a Lkol to liczba kolektorów._

- **Zapotrzebowanie na ciepło netto (Qz):** Ilość energii potrzebna do podgrzania określonej ilości wody od temperatury początkowej do końcowej.
  > `Qz = Lż * qcwud * cw * (Twc - Twz)`
  > _Gdzie Lż to liczba mieszkańców, qcwud to jednostkowe zużycie wody, cw to ciepło właściwe wody, a (Twc - Twz) to różnica temperatur._

- **Całkowite dobowe zapotrzebowanie na ciepło (Qcwu):** Suma zapotrzebowania netto oraz strat ciepła (np. straty podgrzewacza Qpg i straty na cyrkulacji Qcr).
  > `Qcwu = Qz + Qpg + Qcr`

### 3. Obliczenia Powierzchni Kolektorów Słonecznych

- **Pole powierzchni kolektorów słonecznych (A):** Teoretyczna powierzchnia potrzebna do pokrycia części zapotrzebowania na ciepło, uwzględniając nasłonecznienie.
  > `A = Qcwur * U / H`
  > _Gdzie Qcwur to roczne zapotrzebowanie na ciepło, U to udział pokrycia przez instalację solarną, a H to roczne nasłonecznienie._

- **Rzeczywista powierzchnia kolektorów (Arz):** Powierzchnia, jaką muszą mieć realne kolektory, uwzględniając ich sprawność.
  > `Arz = A / ηks`
  > _Gdzie ηks to średnia roczna sprawność kolektora._

---

# Rozszerzony Zestaw Zadań Egzaminacyjnych ELE.11 (Styczeń 2022)

_Zadania oparte na schemacie i typologii z egzaminu praktycznego ze stycznia 2022_

---

## Część 1: Obliczenia Ciśnień w Instalacji Grzewczej

**Kluczowe wzory:**
- Ciśnienie napełniania instalacji: `Psol1 = 1,5 bar + 0,1 * Hhyd`
- Warunek dla ciśnienia wstępnego: `Psol1 ≥ Pn1 + 0,3 bar`

### Zadanie 1.1

Oblicz ciśnienie napełniania instalacji (Psol1) oraz maksymalne dopuszczalne ciśnienie wstępne w naczyniu przeponowym (Pn1) dla instalacji, w której wysokość hydrostatyczna (Hhyd) wynosi **8 m**.

**Rozwiązanie:**
1.  **Obliczenie ciśnienia napełniania (Psol1):**
    - `Psol1 = 1,5 bar + 0,1 * 8`
    - `Psol1 = 1,5 bar + 0,8 bar`
    - `Psol1 = 2,3 bar`

2.  **Obliczenie maksymalnego ciśnienia wstępnego (Pn1):**
    - `Pn1 ≤ Psol1 - 0,3 bar`
    - `Pn1 ≤ 2,3 bar - 0,3 bar`
    - `Pn1 ≤ 2,0 bar`

**Odpowiedź:** Ciśnienie napełniania instalacji wynosi **2,3 bar**, a maksymalne ciśnienie wstępne w naczyniu to **2,0 bar**.

### Zadanie 1.2

Wysokość od najwyższego punktu instalacji do naczynia przeponowego wynosi **11,5 m**. Oblicz Psol1 i Pn1.

**Rozwiązanie:**
1.  **Obliczenie Psol1:**
    - `Psol1 = 1,5 bar + 0,1 * 11,5`
    - `Psol1 = 1,5 bar + 1,15 bar`
    - `Psol1 = 2,65 bar`

2.  **Obliczenie Pn1:**
    - `Pn1 ≤ 2,65 bar - 0,3 bar`
    - `Pn1 ≤ 2,35 bar`

**Odpowiedź:** Ciśnienie napełniania wynosi **2,65 bar**, a ciśnienie wstępne nie powinno przekraczać **2,35 bar**.

### Zadanie 1.3

Zmierzono ciśnienie napełniania instalacji i wyniosło ono **1,9 bar**. Jaka jest wysokość hydrostatyczna (Hhyd) tej instalacji? Jakie powinno być ciśnienie wstępne w naczyniu?

**Rozwiązanie:**
1.  **Obliczenie wysokości hydrostatycznej (Hhyd):**
    - `Psol1 = 1,5 bar + 0,1 * Hhyd`
    - `1,9 bar = 1,5 bar + 0,1 * Hhyd`
    - `0,4 bar = 0,1 * Hhyd`
    - `Hhyd = 0,4 / 0,1 = 4 m`

2.  **Obliczenie Pn1:**
    - `Pn1 ≤ 1,9 bar - 0,3 bar`
    - `Pn1 ≤ 1,6 bar`

**Odpowiedź:** Wysokość hydrostatyczna instalacji wynosi **4 m**, a ciśnienie wstępne powinno być nie większe niż **1,6 bar**.

---

## Część 2: Obliczenia Przepływu i Zapotrzebowania na Ciepło

**Kluczowe wzory:**
- Całkowity przepływ w instalacji: `Vkol = Skol * Lkol`
- Zapotrzebowanie na ciepło netto: `Qz = Lż * qcwud * cw * (Twc - Twz)`
- Całkowite dobowe zapotrzebowanie na ciepło: `Qcwu = Qz + Qpg + Qcr`

### Zadanie 2.1

Instalacja składa się z **5 kolektorów**. Strumień przepływu czynnika przez jeden kolektor (Skol) wynosi **1,2 dm³/min**. Oblicz całkowity przepływ w instalacji (Vkol).

**Rozwiązanie:**
- `Vkol = 1,2 dm³/min * 5`
- `Vkol = 6 dm³/min`

**Odpowiedź:** Całkowity przepływ w instalacji wynosi **6 dm³/min**.

### Zadanie 2.2

Oblicz dobowe zapotrzebowanie na ciepło netto (Qz) dla **5-osobowej** rodziny. Jednostkowe zużycie c.w.u. wynosi **45 dm³/(os.·d)**, ciepło właściwe wody to **0,00116 kWh/(kg·K)**, a temperatura wody ciepłej i zimnej to odpowiednio **50°C** i **8°C**.

**Rozwiązanie:**
1.  **Obliczenie różnicy temperatur:**
    - `ΔT = 50°C - 8°C = 42°C = 42 K`

2.  **Obliczenie Qz:**
    - `Qz = 5 os. * 45 dm³/(os.·d) * 0,00116 kWh/(kg·K) * 42 K`
    - `Qz = 225 * 0,00116 * 42`
    - `Qz ≈ 10,96 kWh/d`

**Odpowiedź:** Dobowe zapotrzebowanie na ciepło netto wynosi około **10,96 kWh/d**.

### Zadanie 2.3

Oblicz całkowite dobowe zapotrzebowanie na ciepło (Qcwu), jeśli zapotrzebowanie netto (Qz) wynosi **8,1 kWh/d**, straty ciepła podgrzewacza (Qpg) to **2,8 kWh/d**, a straty na cyrkulacji (Qcr) to **1,5 kWh/d**.

**Rozwiązanie:**
- `Qcwu = 8,1 kWh/d + 2,8 kWh/d + 1,5 kWh/d`
- `Qcwu = 12,4 kWh/d`

**Odpowiedź:** Całkowite dobowe zapotrzebowanie na ciepło wynosi **12,4 kWh/d**.

---

## Część 3: Obliczenia Powierzchni Kolektorów Słonecznych

**Kluczowe wzory:**
- Pole powierzchni kolektorów słonecznych: `A = Qcwuc * U / H`
- Rzeczywista powierzchnia kolektorów: `Arz = A / ηks`

### Zadanie 3.1

Oblicz pole powierzchni kolektorów słonecznych (A), jeśli roczne zapotrzebowanie na ciepło (Qcwur) wynosi **3200 kWh**, udział rocznego pokrycia przez instalację (U) to **0,65**, a suma całkowitego rocznego promieniowania (H) to **1200 kWh/m²**.

**Rozwiązanie:**
- `A = (3200 kWh * 0,65) / 1200 kWh/m²`
- `A = 2080 / 1200`
- `A ≈ 1,73 m²`

**Odpowiedź:** Wymagane pole powierzchni kolektorów wynosi **1,73 m²**.

### Zadanie 3.2

Oblicz rzeczywistą powierzchnię kolektorów (Arz), jeśli obliczone pole (A) wynosi **2,2 m²**, a średnia roczna sprawność kolektora (ηks) to **0,48**.

**Rozwiązanie:**
- `Arz = 2,2 m² / 0,48`
- `Arz ≈ 4,58 m²`

**Odpowiedź:** Rzeczywista powierzchnia kolektorów powinna wynosić około **4,58 m²**.

### Zadanie 3.3

Całkowite dobowe zapotrzebowanie na ciepło (Qcwu) wynosi **11,7 kWh/d**. Oblicz roczne zapotrzebowanie (Qcwur), a następnie pole powierzchni kolektorów (A) i rzeczywistą powierzchnię (Arz). Przyjmij U = 0,6, H = 1150 kWh/m² oraz ηks = 0,5.

**Rozwiązanie:**
1.  **Obliczenie rocznego zapotrzebowania (Qcwur):**
    - `Qcwur = 11,7 kWh/d * 365 d = 4270,5 kWh`

2.  **Obliczenie pola powierzchni (A):**
    - `A = (4270,5 kWh * 0,6) / 1150 kWh/m²`
    - `A = 2562,3 / 1150`
    - `A ≈ 2,23 m²`

3.  **Obliczenie rzeczywistej powierzchni (Arz):**
    - `Arz = 2,23 m² / 0,5`
    - `Arz = 4,46 m²`

**Odpowiedź:** Wymagane pole powierzchni to **2,23 m²**, a rzeczywista powierzchnia to **4,46 m²**.

---
