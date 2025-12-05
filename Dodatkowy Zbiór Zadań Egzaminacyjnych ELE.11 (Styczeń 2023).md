_Przewodnik po egzaminie ELE.11 (styczeń 2023) dla technika energetyki odnawialnej_

---

## Wprowadzenie do Egzaminu ELE.11 (Styczeń 2023)

Egzamin zawodowy praktyczny ze stycznia 2023 roku w kwalifikacji ELE.11, "Eksploatacja urządzeń i systemów energetyki odnawialnej", koncentrował się na **projektowaniu autonomicznej (off-grid) instalacji fotowoltaicznej** dla domu letniskowego. W odróżnieniu od późniejszych arkuszy, które skupiały się na diagnostyce, ten egzamin sprawdzał umiejętności projektowe od podstaw.

Zadanie polegało na przeanalizowaniu zapotrzebowania na energię, obliczeniu kluczowych parametrów instalacji, doborze odpowiednich komponentów (modułów, inwertera, akumulatorów) oraz narysowaniu schematu połączeń. Był to kompleksowy test wiedzy z zakresu projektowania małych systemów fotowoltaicznych.

Kluczowe kompetencje weryfikowane w tym arkuszu to:
- **Obliczanie dobowego zapotrzebowania na energię** na podstawie listy odbiorników.
- **Analiza danych o nasłonecznieniu** i ich wykorzystanie w obliczeniach.
- **Obliczanie minimalnej mocy instalacji PV** oraz wymaganej liczby modułów.
- **Dobór pojemności akumulatorów** w zależności od wymaganego czasu podtrzymania i napięcia systemu.
- **Dobór komponentów** na podstawie ich kart katalogowych i parametrów.
- **Tworzenie schematów połączeń** elektrycznych.

---

## Główne Obszary Tematyczne Egzaminu (Styczeń 2023)

Arkusz egzaminacyjny ze stycznia 2023 obejmował pełen proces projektowy dla instalacji off-grid. Poniższa tabela przedstawia kluczowe zagadnienia, które pojawiły się w zadaniu.

| Obszar Tematyczny | Kluczowe Zagadnienia |
| :--- | :--- |
| **Analiza Energetyczna** | - Zestawienie dobowego zużycia energii (Wh) dla wszystkich odbiorników w domu letniskowym.<br>- Sumowanie zużycia w celu obliczenia całkowitego dziennego zapotrzebowania na energię (Qd).<br>- Analiza danych o średnim miesięcznym nasłonecznieniu (Nas) dla lokalizacji. |
| **Obliczenia Projektowe** | - Obliczanie minimalnej mocy szczytowej instalacji fotowoltaicznej (PPV) z uwzględnieniem sprawności systemu.<br>- Obliczanie minimalnej liczby modułów fotowoltaicznych (L) na podstawie ich mocy maksymalnej (Pmpp).<br>- Obliczanie wymaganej pojemności baterii akumulatorów (C) dla zapewnienia rezerwy energii na określoną liczbę dni (k). |
| **Dobór Komponentów** | - Wybór modułów fotowoltaicznych o odpowiedniej mocy i parametrach elektrycznych.<br>- Dobór inwertera (falownika) o właściwym napięciu pracy i mocy.<br>- Dobór akumulatorów o wymaganej pojemności i napięciu, a także określenie ich liczby. |
| **Schematy i Dokumentacja** | - Rysowanie schematu połączenia akumulatorów w celu uzyskania wymaganego napięcia systemowego.<br>- Uzupełnianie tabel projektowych z wynikami obliczeń i parametrami dobranych urządzeń.<br>- Identyfikacja symboli graficznych stosowanych w schematach instalacji PV. |

---

## Kluczowe Zagadnienia Matematyczne i Obliczenia (Styczeń 2023)

Arkusz ze stycznia 2023 roku był egzaminem typowo projektowym, co oznaczało konieczność wykonania szeregu obliczeń w celu poprawnego zwymiarowania instalacji. Poniżej znajdują się szczegółowe wyjaśnienia kluczowych wzorów i obliczeń.

### 1. Obliczanie Dobowego Zapotrzebowania na Energię (Qd)

Pierwszym krokiem w projektowaniu instalacji off-grid jest dokładne oszacowanie, ile energii będą zużywać wszystkie urządzenia w ciągu doby. W arkuszu należało zsumować dobowe zużycie energii (w watogodzinach [Wh]) dla wszystkich odbiorników wymienionych w Tabeli C.

**Przykład zadania (na podstawie arkusza):**
Zsumuj dobowe zużycie energii dla domu letniskowego nr 2.

**Dane z Tabeli C (przykładowe):**
- Oświetlenie pokoju: 64 Wh
- Lodówka: 300 Wh
- Zasobnik c.w.u. (bojler): 1800 Wh
- ... (pozostałe urządzenia)

**Rozwiązanie:**
Sumujemy wartości z kolumny "Dobowe zużycie energii [Wh]":
`Qd = 64 + 24 + 6 + 5 + 200 + 45 + 300 + 1800 = 2444 Wh`

**Wniosek:** Całkowite dobowe zapotrzebowanie na energię wynosi **2444 Wh**, czyli **2,444 kWh**.

### 2. Obliczanie Minimalnej Mocy Instalacji Fotowoltaicznej (PPV)

Kolejny krok to obliczenie, jak dużą moc szczytową (mierzoną w watach [W]) musi mieć generator fotowoltaiczny, aby pokryć dzienne zapotrzebowanie na energię, uwzględniając przy tym warunki nasłonecznienia i straty w systemie.

> **Wzór na minimalną moc instalacji (PPV):**
> PPV = (Qd * GSTC) / (Nas * η)
> _Uwaga: W arkuszu podano wzór z `Nas/30`, co sugeruje użycie `Qd` w kWh i `Nas` w kWh/m²/miesiąc. Dla uproszczenia i zgodności jednostek, można przekształcić `Nas` na dzienne._

**Objaśnienie symboli:**
- **PPV** – minimalna moc instalacji [W].
- **Qd** – średnie dzienne zużycie energii [Wh/dzień].
- **GSTC** – natężenie promieniowania w warunkach STC (**1000 W/m²**).
- **Nas** – średnie dzienne nasłonecznienie [Wh/m²/dzień].
- **η** – sumaryczna sprawność instalacji (uwzględniająca straty na przewodach, inwerterze, akumulatorze; typowo przyjmuje się **0,75-0,85**).

**Przykład zadania (na podstawie danych z arkusza):**
Oblicz minimalną moc instalacji, przyjmując sprawność systemu η = 0,85.

**Dane z arkusza:**
- Qd = 2444 Wh
- Średnie miesięczne nasłonecznienie: 151009 Wh/m². Aby uzyskać wartość dzienną, dzielimy przez 30 dni: `Nas_dzienne = 151009 / 30 ≈ 5033,6 Wh/m²/dzień`.
- GSTC = 1000 W/m²
- η = 0,85 (założona sprawność systemu)

**Rozwiązanie krok po kroku:**
1.  **Podstawienie danych do wzoru:**
    `PPV = (2444 Wh * 1000 W/m²) / (5033,6 Wh/m² * 0,85)`

2.  **Obliczenie mianownika:**
    `5033,6 * 0,85 = 4278,56`

3.  **Obliczenie mocy PPV:**
    `PPV = 2444000 / 4278,56 ≈ 571,2 W`

**Wniosek:** Minimalna wymagana moc instalacji wynosi około **571 W**. W zasadach oceniania wynik (646-649 W) sugeruje przyjęcie niższej sprawności (około 0,75), co jest bezpieczniejszym założeniem projektowym.

### 3. Obliczanie Minimalnej Liczby Modułów (L)

Po obliczeniu wymaganej mocy instalacji, należy dobrać odpowiednią liczbę modułów fotowoltaicznych.

> **Wzór na liczbę modułów (L):**
> L = PPV / Pmpp

**Objaśnienie symboli:**
- **L** – liczba modułów [szt.].
- **PPV** – obliczona minimalna moc instalacji [W].
- **Pmpp** – moc maksymalna pojedynczego, wybranego modułu [W].

**Przykład zadania:**
Oblicz liczbę modułów, jeśli do projektu wybrano moduły o mocy **Pmpp = 330 W**.

**Rozwiązanie:**
1.  **Podstawienie danych:**
    `L = 571,2 W / 330 W ≈ 1,73`

2.  **Zaokrąglenie wyniku:**
    Liczbę modułów zawsze zaokrąglamy **w górę** do najbliższej liczby całkowitej.
    `L = 2 szt.`

**Wniosek:** Należy zainstalować minimum **2 moduły** o mocy 330 W każdy.

### 4. Obliczanie Pojemności Akumulatorów (C)

Ostatnim kluczowym obliczeniem jest dobór pojemności magazynu energii, który zapewni zasilanie w nocy oraz przez określoną liczbę dni bez słońca.

> **Wzór na pojemność akumulatora (C):**
> C = (Qd * k) / U

**Objaśnienie symboli:**
- **C** – pojemność akumulatora [Ah].
- **Qd** – średnie dzienne zużycie energii [Wh].
- **k** – ilość dni rezerwy (autonomii), czyli ile dni instalacja ma działać bez słońca (w zadaniu należało przyjąć **k=2**).
- **U** – napięcie pracy systemu (inwertera i akumulatorów), np. 12 V, 24 V lub 48 V.

**Przykład zadania:**
Oblicz wymaganą pojemność akumulatorów dla systemu o napięciu **24 V** i dwudniowej rezerwie energii.

**Rozwiązanie:**
1.  **Podstawienie danych:**
    `C = (2444 Wh * 2) / 24 V`

2.  **Obliczenie licznika:**
    `2444 * 2 = 4888 Wh`

3.  **Obliczenie pojemności:**
    `C = 4888 Wh / 24 V = 203,67 Ah`

**Wniosek:** Należy zastosować akumulatory o łącznej pojemności co najmniej **204 Ah** dla systemu 24 V. W praktyce dobiera się akumulatory z typoszeregu, np. 2x 12V 110Ah połączone szeregowo, co da 24V i 110Ah (za mało), lub 2x 12V 220Ah, co da 24V i 220Ah (prawidłowo).

---


# Dodatkowy Zbiór Zadań Egzaminacyjnych ELE.11 (Styczeń 2023)

_Zadania oparte na schemacie i typologii z egzaminu praktycznego ze stycznia 2023_

---

## Część 1: Obliczanie Dobowego Zapotrzebowania na Energię (Qd)

### Zadanie 1.1

Oblicz dobowe zapotrzebowanie na energię (Qd) dla małego warsztatu, w którym zainstalowano następujące odbiorniki:

| Odbiornik | Moc [W] | Dobowy czas pracy [h] |
| :--- | :--- | :--- |
| Oświetlenie LED | 50 | 8 |
| Wiertarka | 800 | 0.5 |
| Radio | 15 | 8 |
| Ładowarka do wkrętarki | 40 | 2 |

**Rozwiązanie:**
1.  **Obliczenie dobowego zużycia energii dla każdego odbiornika:**
    - Oświetlenie LED: `50 W * 8 h = 400 Wh`
    - Wiertarka: `800 W * 0.5 h = 400 Wh`
    - Radio: `15 W * 8 h = 120 Wh`
    - Ładowarka: `40 W * 2 h = 80 Wh`

2.  **Zsumowanie zużycia:**
    `Qd = 400 + 400 + 120 + 80 = 1000 Wh`

**Odpowiedź:** Dobowe zapotrzebowanie na energię wynosi **1000 Wh** (czyli 1 kWh).

### Zadanie 1.2

Uzupełnij poniższą tabelę, obliczając dobowe zużycie energii dla każdego urządzenia oraz sumaryczne zapotrzebowanie (Qd) dla altany ogrodowej.

| Odbiornik | Moc [W] | Dobowy czas pracy [h] | Dobowe zużycie energii [Wh] |
| :--- | :--- | :--- | :--- |
| Oświetlenie zewnętrzne | 20 | 5 | **100** |
| Pompa do oczka wodnego | 35 | 24 | **840** |
| Gniazdko do laptopa | 65 | 3 | **195** |
| **Razem** | - | - | **1135** |

**Rozwiązanie:**
- Oświetlenie: `20 W * 5 h = 100 Wh`
- Pompa: `35 W * 24 h = 840 Wh`
- Gniazdko: `65 W * 3 h = 195 Wh`
- Razem: `100 + 840 + 195 = 1135 Wh`

**Odpowiedź:** Całkowite dobowe zapotrzebowanie na energię wynosi **1135 Wh**.

---

## Część 2: Obliczanie Minimalnej Mocy Instalacji Fotowoltaicznej (PPV)

**Wzór do wykorzystania:** `PPV = (Qd * GSTC) / (Nas_dzienne * η)`

### Zadanie 2.1

Oblicz minimalną moc instalacji fotowoltaicznej (PPV) dla warsztatu z Zadania 1.1, przyjmując następujące dane:
- Dobowe zapotrzebowanie na energię: **Qd = 1000 Wh**
- Średnie dzienne nasłonecznienie dla lokalizacji: **Nas_dzienne = 4500 Wh/m²**
- Standardowe natężenie promieniowania: **GSTC = 1000 W/m²**
- Założona sprawność systemu: **η = 0,80**

**Rozwiązanie:**
1.  **Podstawienie danych do wzoru:**
    `PPV = (1000 Wh * 1000 W/m²) / (4500 Wh/m² * 0,80)`

2.  **Obliczenie mianownika:**
    `4500 * 0,80 = 3600`

3.  **Obliczenie mocy PPV:**
    `PPV = 1000000 / 3600 ≈ 277,8 W`

**Odpowiedź:** Minimalna wymagana moc instalacji wynosi około **278 W**.

### Zadanie 2.2

Dla altany ogrodowej z Zadania 1.2 (Qd = 1135 Wh) planuje się instalację PV. Średnie miesięczne nasłonecznienie w okresie letnim wynosi **145 kWh/m²**. Przyjmij sprawność systemu **η = 0,78**. Oblicz wymaganą moc PPV.

**Rozwiązanie:**
1.  **Przeliczenie jednostek:**
    - `Qd = 1135 Wh`
    - `Nas_miesieczne = 145 kWh/m² = 145000 Wh/m²`
    - `Nas_dzienne = 145000 Wh/m² / 30 dni ≈ 4833 Wh/m²/dzień`

2.  **Podstawienie danych do wzoru:**
    `PPV = (1135 Wh * 1000 W/m²) / (4833 Wh/m² * 0,78)`

3.  **Obliczenie mianownika:**
    `4833 * 0,78 ≈ 3769,7`

4.  **Obliczenie mocy PPV:**
    `PPV = 1135000 / 3769,7 ≈ 301,1 W`

**Odpowiedź:** Należy zaprojektować instalację o mocy co najmniej **302 W**.

---

## Część 3: Obliczanie Pojemności Akumulatorów (C)

**Wzór do wykorzystania:** `C = (Qd * k) / U`

### Zadanie 3.1

Oblicz wymaganą pojemność magazynu energii (C) dla warsztatu z poprzednich zadań, który ma być zasilany z instalacji o napięciu **12 V**. System ma zapewnić zasilanie przez **3 dni** bez słońca (k=3).
- Dobowe zapotrzebowanie na energię: **Qd = 1000 Wh**
- Ilość dni rezerwy: **k = 3**
- Napięcie systemu: **U = 12 V**

**Rozwiązanie:**
1.  **Podstawienie danych do wzoru:**
    `C = (1000 Wh * 3) / 12 V`

2.  **Obliczenie licznika:**
    `1000 * 3 = 3000 Wh`

3.  **Obliczenie pojemności:**
    `C = 3000 Wh / 12 V = 250 Ah`

**Odpowiedź:** Wymagana pojemność akumulatorów dla systemu 12 V wynosi **250 Ah**.

### Zadanie 3.2

Dla altany ogrodowej (Qd = 1135 Wh) projektant zdecydował się na system o napięciu **24 V**. Wymagana jest rezerwa energii na **2 dni** (k=2). Jaką minimalną pojemność musi mieć bateria akumulatorów?

**Rozwiązanie:**
1.  **Podstawienie danych do wzoru:**
    `C = (1135 Wh * 2) / 24 V`

2.  **Obliczenie licznika:**
    `1135 * 2 = 2270 Wh`

3.  **Obliczenie pojemności:**
    `C = 2270 Wh / 24 V ≈ 94,6 Ah`

**Odpowiedź:** Należy zastosować akumulatory o łącznej pojemności co najmniej **95 Ah** dla systemu 24 V.

### Zadanie 3.3

Zaprojektowano system fotowoltaiczny, w którym zainstalowano baterię akumulatorów o pojemności **C = 200 Ah** pracującą w systemie o napięciu **U = 48 V**. Na ile dni pełnej autonomii (k) wystarczy zgromadzona energia, jeśli dobowe zapotrzebowanie na energię wynosi **Qd = 3500 Wh**?

**Rozwiązanie:**
1.  **Przekształcenie wzoru:**
    `C = (Qd * k) / U  =>  k = (C * U) / Qd`

2.  **Podstawienie danych:**
    `k = (200 Ah * 48 V) / 3500 Wh`

3.  **Obliczenie licznika (całkowitej energii w akumulatorze):**
    `200 * 48 = 9600 Wh`

4.  **Obliczenie liczby dni autonomii:**
    `k = 9600 Wh / 3500 Wh ≈ 2,74 dnia`

**Odpowiedź:** Zgromadzona energia wystarczy na około **2,74 dnia** autonomii. W praktyce oznacza to, że system zapewni pełne zasilanie przez 2 dni.

---
