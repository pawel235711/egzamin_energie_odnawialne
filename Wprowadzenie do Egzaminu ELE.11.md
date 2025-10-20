_Przewodnik po egzaminie ELE.11 dla technika energetyki odnawialnej_ # Prezentacja Egzaminacyjna: ELE.11

---

## Wprowadzenie do Egzaminu ELE.11

Egzamin zawodowy praktyczny w kwalifikacji ELE.11, "Eksploatacja urządzeń i systemów energetyki odnawialnej", sprawdza umiejętności niezbędne do pracy z nowoczesnymi technologiami OZE. Czas trwania egzaminu wynosi **180 minut**, co wymaga nie tylko wiedzy, ale również dobrej organizacji pracy i umiejętności rozwiązywania problemów pod presją czasu. Egzamin opiera się na podstawie programowej z 2019 roku i obejmuje szeroki zakres zagadnień, od instalacji fotowoltaicznych po systemy grzewcze wykorzystujące energię słoneczną.

Kluczowe obszary weryfikowane na egzaminie to:
- **Analiza dokumentacji technicznej** i identyfikacja nieprawidłowości w instalacjach.
- **Wykonywanie pomiarów** kontrolnych i ich interpretacja.
- **Dobór komponentów** i materiałów eksploatacyjnych, takich jak płyn solarny.
- **Planowanie prac serwisowych** i przeglądów technicznych.
- **Obliczenia** związane z wydajnością, zapotrzebowaniem na energię i parametrami pracy systemów.

---

## Główne Obszary Tematyczne Egzaminu

Egzamin ELE.11 koncentruje się na dwóch głównych technologiach energetyki odnawialnej: fotowoltaice oraz słonecznych instalacjach grzewczych. Poniższa tabela przedstawia kluczowe zagadnienia w każdym z tych obszarów.

| Obszar Technologiczny | Kluczowe Zagadnienia |
| :--- | :--- |
| **Instalacje Fotowoltaiczne (PV)** | - Parametry modułów fotowoltaicznych (moc, napięcie, prąd w warunkach STC).<br>- Identyfikacja i usuwanie usterek (np. uszkodzone złącza MC4, błędy inwertera).<br>- Pomiary po stronie DC i AC (napięcie obwodu otwartego, prąd zwarciowy).<br>- Obliczenia związane z bilansem energetycznym i autokonsumpcją.<br>- Zasady bezpieczeństwa przy pracy z instalacjami PV. |
| **Słoneczne Instalacje Grzewcze** | - Parametry kolektorów słonecznych (sprawność optyczna, współczynniki strat).<br>- Dobór i obliczenia ilości płynu solarnego.<br>- Wymiarowanie instalacji (powierzchnia kolektorów, pojemność zasobników).<br>- Kontrola parametrów pracy (ciśnienie, temperatura, przepływ).<br>- Obliczenia sprawności kolektorów i zapotrzebowania na ciepłą wodę użytkową (c.w.u.). |

---



## Kluczowe Zagadnienia Matematyczne i Obliczenia

Zrozumienie matematycznych podstaw jest kluczowe do prawidłowego wykonania zadań egzaminacyjnych. Poniżej znajdują się szczegółowe wyjaśnienia najważniejszych wzorów, jednostek i obliczeń, które pojawiają się na egzaminie ELE.11.

### 1. Jednostki i ich Konwersja

Poprawne operowanie jednostkami jest fundamentem w pracy technika. Błędy w tym obszarze mogą prowadzić do całkowicie nieprawidłowych wyników, nawet przy poprawnym zastosowaniu wzorów.

| Wielkość | Jednostka Podstawowa | Jednostki Pochodne i Przeliczniki |
| :--- | :--- | :--- |
| **Moc (P)** | Wat (W) | 1 kilowat (kW) = 1000 W<br>1 megawat (MW) = 1 000 000 W |
| **Energia (E)** | Dżul (J) | 1 kilowatogodzina (kWh) = 3 600 000 J<br>Często używane: kWh, kWh/m²·rok |
| **Napięcie (U)** | Wolt (V) | - |
| **Prąd (I)** | Amper (A) | - |
| **Pojemność (V)** | Metr sześcienny (m³) | 1 m³ = 1000 decymetrów sześciennych (dm³)<br>1 dm³ = 1 litr (L) |
| **Temperatura (T)** | Kelwin (K) | T[K] = T[°C] + 273,15<br>**Ważne:** Różnica temperatur (ΔT) ma tę samą wartość w K i °C. |
| **Ciśnienie (p)** | Paskal (Pa) | 1 bar = 100 000 Pa = 0,1 MPa |

**Przykład praktyczny:**
Na egzaminie często pojawia się konieczność przeliczenia mocy. Jeśli pojedynczy moduł fotowoltaiczny ma moc 350 W, to instalacja złożona z 10 takich modułów będzie miała moc całkowitą:

P_c = 10 * 350 W = 3500 W = 3,5 kW

### 2. Obliczenia Sprawności Kolektora Słonecznego

Sprawność kolektora to jeden z kluczowych parametrów, który określa, jak efektywnie urządzenie przetwarza energię słoneczną na ciepło. Wzór na sprawność uwzględnia zarówno charakterystykę samego kolektora, jak i warunki, w jakich pracuje.

> **Wzór na średnią sprawność kolektora:**
> η = η₀ - (a₁ · ΔT) / E_g - (a₂ · ΔT²) / E_g

**Objaśnienie symboli:**
- **η** – średnia sprawność kolektora (wartość bezwymiarowa, od 0 do 1).
- **η₀** – sprawność optyczna (maksymalna sprawność w idealnych warunkach, podawana przez producenta).
- **a₁** – liniowy współczynnik strat ciepła [W/(m²·K)].
- **a₂** – nieliniowy współczynnik strat ciepła [W/(m²·K²)].
- **ΔT** – różnica między średnią temperaturą absorbera a temperaturą otoczenia [K lub °C].
- **E_g** – średnie natężenie promieniowania słonecznego padającego na powierzchnię kolektora [W/m²].

**Przykład zadania egzaminacyjnego:**
Oblicz sprawność kolektora, mając dane:
- Sprawność optyczna (η₀) = 0,82
- Liniowy współczynnik strat (a₁) = 3,5 W/(m²·K)
- Nieliniowy współczynnik strat (a₂) = 0,015 W/(m²·K²)
- Średnia różnica temperatur (ΔT) = 40 K
- Średnie natężenie promieniowania (E_g) = 800 W/m²

**Rozwiązanie krok po kroku:**
1.  **Podstawienie danych do wzoru:**
    η = 0,82 - (3,5 * 40) / 800 - (0,015 * 40²) / 800
2.  **Obliczenie strat liniowych:**
    (3,5 * 40) / 800 = 140 / 800 = 0,175
3.  **Obliczenie strat nieliniowych:**
    (0,015 * 1600) / 800 = 24 / 800 = 0,03
4.  **Obliczenie końcowej sprawności:**
    η = 0,82 - 0,175 - 0,03 = 0,615

**Odpowiedź:** Średnia sprawność kolektora w podanych warunkach wynosi 0,615, czyli 61,5%.

### 3. Wymiarowanie Słonecznej Instalacji Grzewczej

Dobór odpowiedniej liczby kolektorów jest kluczowy dla zapewnienia wymaganej ilości ciepłej wody użytkowej (c.w.u.). Proces ten wymaga obliczenia zapotrzebowania na energię, a następnie określenia potrzebnej powierzchni kolektorów.

> **Wzór na wymaganą łączną powierzchnię apertury kolektorów:**
> F_kol = (z · (t_z - t_k) · c_w) / (3600 · η · E_kol)

**Objaśnienie symboli:**
- **F_kol** – łączna powierzchnia apertury kolektorów [m²].
- **z** – dobowe zapotrzebowanie na ciepłą wodę [dm³ lub kg, zakładając gęstość wody ≈ 1 kg/dm³].
- **t_z** – wymagana temperatura ciepłej wody w zasobniku [°C].
- **t_k** – temperatura zimnej wody (z sieci) [°C].
- **c_w** – ciepło właściwe wody [≈ 4,19 kJ/(kg·K)].
- **η** – obliczona wcześniej średnia sprawność kolektora.
- **E_kol** – średnia dobowa energia promieniowania słonecznego [kWh/m²].
- **3600** – współczynnik przeliczeniowy z kWh na kJ (1 kWh = 3600 kJ).

**Przykład zadania egzaminacyjnego:**
Rodzina zużywa 250 litrów ciepłej wody dziennie. Woda ma być podgrzana z 10°C do 55°C. Średnia sprawność kolektora wynosi 60% (η = 0,6), a średnia dobowa energia promieniowania to 4,5 kWh/m². Oblicz wymaganą powierzchnię kolektorów.

**Rozwiązanie krok po kroku:**
1.  **Podstawienie danych do wzoru:**
    F_kol = (250 * (55 - 10) * 4,19) / (3600 * 0,6 * 4,5)
2.  **Obliczenie licznika (zapotrzebowanie na energię w kJ):**
    250 * 45 * 4,19 = 47 137,5 kJ
3.  **Obliczenie mianownika (energia dostarczona przez 1 m² kolektora w kJ):**
    3600 * 0,6 * 4,5 = 9720 kJ/m²
4.  **Obliczenie wymaganej powierzchni:**
    F_kol = 47 137,5 / 9720 ≈ 4,85 m²

**Dobór liczby kolektorów:**
Jeśli pojedynczy kolektor ma powierzchnię apertury F_ap = 2,1 m², to liczbę kolektorów (L_k) obliczamy:

L_k = F_kol / F_ap = 4,85 / 2,1 ≈ 2,31

Ponieważ nie można zainstalować ułamkowej liczby kolektorów, **wynik zawsze zaokrąglamy w górę** do najbliższej liczby całkowitej. W tym przypadku należy zainstalować **3 kolektory**.

### 4. Obliczenia Pojemności w Instalacji

Na egzaminie może pojawić się zadanie związane z obliczeniem całkowitej pojemności płynu w instalacji grzewczej lub pojemności naczynia wzbiorczego.

> **Wzór na pojemność orurowania:**
> V_r = (π · d²) / 4 · L · 1000

**Objaśnienie symboli:**
- **V_r** – pojemność orurowania [dm³].
- **d** – wewnętrzna średnica rury [m].
- **L** – długość rury [m].
- **1000** – współczynnik konwersji z m³ na dm³.

**Przykład:** Oblicz pojemność 20 metrów rury o średnicy wewnętrznej 22 mm (0,022 m).

V_r = (π · 0,022²) / 4 · 20 · 1000 ≈ (3,14159 · 0,000484) / 4 · 20000 ≈ 7,6 dm³

Całkowita pojemność instalacji (V_A) to suma pojemności kolektorów (V_k), grupy pompowej (V_gp), wężownicy zasobnika (V_w) i orurowania (V_r).

---

## Analiza i Rozwiązywanie Zadań Egzaminacyjnych

Przeanalizujmy teraz przykładowe zadania z arkuszy egzaminacyjnych, koncentrując się na krokach prowadzących do poprawnego rozwiązania.

### Zadanie 1: Bilans Energetyczny i Autokonsumpcja (na podstawie arkusza z czerwca 2025)

**Treść zadania (uproszczona):**
Instalacja PV o mocy 5 kWp wyprodukowała w ciągu roku 4800 kWh energii. Roczne zapotrzebowanie budynku na energię wynosi 5500 kWh. Współczynnik autokonsumpcji (energii zużytej na bieżąco) wynosi 0,3. Oblicz ilość energii oddanej do sieci oraz ilość energii, którą trzeba będzie dokupić.

**Rozwiązanie:**
1.  **Energia zużyta na bieżąco (autokonsumpcja):**
    E_auto = Produkcja roczna * Współczynnik autokonsumpcji
    E_auto = 4800 kWh * 0,3 = 1440 kWh

2.  **Energia oddana do sieci (nadwyżka):**
    E_oddana = Produkcja roczna - E_auto
    E_oddana = 4800 kWh - 1440 kWh = 3360 kWh

3.  **Energia pobrana z sieci (do dokupienia):**
    E_pobrana = Zapotrzebowanie roczne - E_auto
    E_pobrana = 5500 kWh - 1440 kWh = 4060 kWh

**Wniosek:** Mimo że instalacja wyprodukowała znaczną ilość energii, ze względu na niedopasowanie czasowe produkcji i zużycia, konieczne jest dokupienie 4060 kWh energii z sieci. Nadwyżka 3360 kWh zostanie sprzedana do sieci (lub rozliczona w systemie opustów).

### Zadanie 2: Dobór Płynu Solarnego (na podstawie arkusza ze stycznia 2025)

**Treść zadania (uproszczona):**
Całkowita pojemność instalacji solarnej wynosi 24 dm³. Należy dobrać płyn solarny, dostępny w opakowaniach 5, 10 i 20 dm³. Należy uwzględnić 10% naddatek płynu na potrzeby serwisowe. Podaj, jakie opakowania należy zakupić, aby zminimalizować koszt.

**Rozwiązanie:**
1.  **Obliczenie całkowitej wymaganej ilości płynu:**
    V_wymagana = Pojemność instalacji * (1 + naddatek)
    V_wymagana = 24 dm³ * 1,10 = 26,4 dm³

2.  **Analiza dostępnych opakowań i dobór optymalnej kombinacji:**
    - Opcja A: 1x 20 dm³ + 1x 10 dm³ = 30 dm³ (nadmiar 3,6 dm³)
    - Opcja B: 3x 10 dm³ = 30 dm³ (nadmiar 3,6 dm³)
    - Opcja C: 1x 20 dm³ + 2x 5 dm³ = 30 dm³ (nadmiar 3,6 dm³)
    - Opcja D: 2x 10 dm³ + 2x 5 dm³ = 30 dm³ (nadmiar 3,6 dm³)
    - Opcja E: 1x 20 dm³ + 1x 5 dm³ = 25 dm³ (**za mało!**)

    W tym przypadku, aby zminimalizować koszt (zakładając, że cena za litr jest niższa w większych opakowaniach), najbardziej optymalnym wyborem będzie **jedna z opcji A, B, C lub D, w zależności od cen jednostkowych opakowań**. Na egzaminie często należy po prostu wskazać kombinację, która spełnia wymagania. Najprostsza to **1x 20 dm³ + 1x 10 dm³**.

---

## Podsumowanie i Wskazówki Egzaminacyjne

1.  **Czytaj uważnie polecenia:** Zwróć uwagę na jednostki, wymagane zaokrąglenia i zakres zadania.
2.  **Zarządzaj czasem:** Masz 180 minut – podziel ten czas na poszczególne części zadania i nie spędzaj zbyt wiele czasu nad jednym problemem.
3.  **Sprawdzaj obliczenia:** Pomyłki w prostych działaniach to częsty błąd. Jeśli masz czas, zweryfikuj swoje wyniki.
4.  **Pisz czytelnie:** Twoja praca będzie oceniana przez egzaminatora. Klarowny zapis obliczeń i odpowiedzi ułatwi ocenę i może zadziałać na Twoją korzyść.
5.  **Nie zostawiaj pustych miejsc:** Nawet jeśli nie jesteś pewien wyniku, zapisz swoje próby obliczeń i tok rozumowania. Często można uzyskać punkty za poszczególne etapy rozwiązania.

Powodzenia na egzaminie!


## Przykładowe Zadania z Rozwiązaniami

Poniżej przedstawiono szczegółowe rozwiązania przykładowych zadań, które mogą pojawić się na egzaminie ELE.11. Każde zadanie zostało rozwiązane krok po kroku, z wyjaśnieniem zastosowanych wzorów i przekształceń.

### Zadanie 1: Obliczenie Pojemności Płynu Solarnego

**Treść zadania:**
Słoneczna instalacja grzewcza składa się z 3 kolektorów o pojemności 1,72 dm³ każdy, orurowania o długości 15 m i średnicy wewnętrznej 20 mm, wężownicy zasobnika o pojemności 9,40 dm³ oraz grupy pompowej o pojemności 0,70 dm³. Oblicz całkowitą pojemność instalacji oraz ilość płynu solarnego potrzebnego do napełnienia instalacji, uwzględniając 10% naddatek.

**Rozwiązanie:**

1. **Obliczenie pojemności kolektorów:**
   V_k = 3 × 1,72 dm³ = 5,16 dm³

2. **Obliczenie pojemności orurowania:**
   V_r = π × (d²/4) × L × 10³
   V_r = π × (0,02²/4) × 15 × 1000
   V_r = π × 0,0001 × 15 × 1000
   V_r = 3,14159 × 0,0001 × 15 × 1000
   V_r = 4,71 dm³

3. **Całkowita pojemność instalacji:**
   V_A = V_k + V_gp + V_w + V_r
   V_A = 5,16 + 0,70 + 9,40 + 4,71
   V_A = 19,97 dm³

4. **Ilość płynu z uwzględnieniem naddatku:**
   V_płynu = V_A × 1,10
   V_płynu = 19,97 × 1,10
   V_płynu = 21,97 dm³ ≈ 22 dm³

5. **Dobór opakowań:**
   Dostępne opakowania: 5 dm³, 10 dm³, 20 dm³
   Optymalne rozwiązanie: 1 × 20 dm³ + 1 × 5 dm³ = 25 dm³

**Odpowiedź:** Całkowita pojemność instalacji wynosi 19,97 dm³. Potrzebujemy 22 dm³ płynu solarnego, co wymaga zakupu opakowań o łącznej pojemności 25 dm³ (1 × 20 dm³ + 1 × 5 dm³).

### Zadanie 2: Weryfikacja Parametrów Instalacji Fotowoltaicznej

**Treść zadania:**
Instalacja fotowoltaiczna składa się z 10 modułów o mocy 400 W każdy. Napięcie obwodu otwartego pojedynczego modułu wynosi 37,29 V, a natężenie prądu zwarcia 13,66 A. Sprawdź, czy falownik o mocy nominalnej 3,5 kW jest odpowiednio dobrany do tej instalacji. Wykonaj niezbędne obliczenia.

**Rozwiązanie:**

1. **Obliczenie całkowitej mocy instalacji:**
   P_instalacji = 10 × 400 W = 4000 W = 4 kW

2. **Porównanie mocy instalacji z mocą falownika:**
   P_instalacji = 4 kW > P_falownika = 3,5 kW

3. **Sprawdzenie współczynnika przewymiarowania:**
   Współczynnik = P_instalacji / P_falownika = 4 / 3,5 = 1,14

**Odpowiedź:** Falownik o mocy 3,5 kW jest niewystarczający dla instalacji o mocy 4 kW. Współczynnik przewymiarowania wynosi 1,14, co oznacza, że w okresach maksymalnej produkcji falownik może ograniczać moc instalacji. Zaleca się wymianę falownika na model o mocy co najmniej 4 kW.

### Zadanie 3: Obliczenie Sprawności Kolektora Słonecznego

**Treść zadania:**
Kolektor słoneczny ma następujące parametry: sprawność optyczna η₀ = 0,753, liniowy współczynnik strat a₁ = 4,10 W/(m²·K), nieliniowy współczynnik strat a₂ = 0,02 W/(m²·K²). Średnia różnica między temperaturą absorbera a temperaturą otoczenia wynosi 33 K, a średnie natężenie promieniowania słonecznego to 660 W/m². Oblicz sprawność kolektora w tych warunkach.

**Rozwiązanie:**

1. **Podstawienie danych do wzoru:**
   η = η₀ - (a₁ × ΔT) / E_g - (a₂ × ΔT²) / E_g
   η = 0,753 - (4,10 × 33) / 660 - (0,02 × 33²) / 660

2. **Obliczenie strat liniowych:**
   (4,10 × 33) / 660 = 135,3 / 660 = 0,205

3. **Obliczenie strat nieliniowych:**
   (0,02 × 33²) / 660 = (0,02 × 1089) / 660 = 21,78 / 660 = 0,033

4. **Obliczenie końcowej sprawności:**
   η = 0,753 - 0,205 - 0,033 = 0,515

**Odpowiedź:** Sprawność kolektora w podanych warunkach wynosi 0,515 (51,5%).

### Zadanie 4: Obliczenie Liczby Kolektorów Słonecznych

**Treść zadania:**
Rodzina 5-osobowa zużywa dziennie 210 dm³ ciepłej wody użytkowej. Woda ma być podgrzana z 13°C do 50°C. Średnia sprawność kolektora wynosi 0,515, a średnia dobowa energia promieniowania słonecznego to 2,9 kWh/m². Powierzchnia apertury pojedynczego kolektora wynosi 2,30 m². Oblicz wymaganą liczbę kolektorów.

**Rozwiązanie:**

1. **Obliczenie wymaganej powierzchni kolektorów:**
   F_kol = (z × (t_w - t_k) × c_w) / (3600 × η × E_kol)
   F_kol = (210 × (50 - 13) × 4,19) / (3600 × 0,515 × 2,9)
   F_kol = (210 × 37 × 4,19) / (3600 × 0,515 × 2,9)
   F_kol = 32 550,3 / 5 387,1 = 6,04 m²

2. **Obliczenie liczby kolektorów:**
   L_k = F_kol / F_ap = 6,04 / 2,30 = 2,63

3. **Zaokrąglenie w górę do liczby całkowitej:**
   L_k = 3 kolektory

**Odpowiedź:** Aby zapewnić wystarczającą ilość ciepłej wody dla 5-osobowej rodziny, należy zainstalować 3 kolektory słoneczne.

### Zadanie 5: Identyfikacja i Usunięcie Usterek w Instalacji Fotowoltaicznej

**Treść zadania:**
Na podstawie dokumentacji z kontroli instalacji fotowoltaicznej zidentyfikuj usterki i nieprawidłowości oraz zaproponuj sposób ich usunięcia. Dokumentacja zawiera następujące informacje:
1. Zabrudzenie modułu fotowoltaicznego.
2. Podwyższona temperatura 5 złączy MC4.
3. Brak podkładek uziemiających pod klemami końcowymi.
4. Kod błędu 2061 na inwerterze: "Nieprawidłowe uziemienie".
5. Niesprawny wyłącznik różnicowoprądowy po stronie AC.

**Rozwiązanie:**

| Nr | Usterka/Nieprawidłowość | Sposób usunięcia |
| --- | --- | --- |
| 1 | Zabrudzenie modułu fotowoltaicznego | Mycie modułów przy użyciu wody z detergentem przeznaczonym do paneli fotowoltaicznych, a następnie spłukanie czystą wodą. |
| 2 | Podwyższona temperatura złączy MC4 | Wymiana uszkodzonych złączy MC4 na nowe, sprawdzenie poprawności połączeń elektrycznych. |
| 3 | Brak podkładek uziemiających | Uzupełnienie podkładek uziemiających pod klemami końcowymi zgodnie z instrukcją montażu. |
| 4 | Nieprawidłowe uziemienie (kod 2061) | Wyłączenie falownika, sprawdzenie połączenia przewodu PE do falownika, sprawdzenie połączenia przewodu neutralnego, sprawdzenie połączenia z transformatorem separacyjnym. |
| 5 | Niesprawny wyłącznik różnicowoprądowy | Wymiana wyłącznika różnicowoprądowego na nowy, o odpowiednich parametrach, zgodny z dokumentacją techniczną instalacji. |

**Odpowiedź:** Zidentyfikowano 5 usterek w instalacji fotowoltaicznej. Dla każdej z nich zaproponowano odpowiedni sposób usunięcia, zgodnie z zasadami bezpieczeństwa i standardami branżowymi.

### Zadanie 6: Bilans Energetyczny Budynku z Instalacją Fotowoltaiczną

**Treść zadania:**
Budynek jednorodzinny ma roczne zapotrzebowanie na energię elektryczną wynoszące 4500 kWh. Na dachu zainstalowano instalację fotowoltaiczną o mocy 5 kWp, która produkuje rocznie 4800 kWh energii. Współczynnik autokonsumpcji (WAK) wynosi 0,3. Oblicz:
1. Ilość energii zużywanej bezpośrednio z instalacji PV.
2. Ilość energii oddawanej do sieci.
3. Ilość energii pobieranej z sieci.
4. Czy instalacja pokrywa całkowite zapotrzebowanie budynku na energię elektryczną?

**Rozwiązanie:**

1. **Energia zużywana bezpośrednio (autokonsumpcja):**
   E_auto = E_PV × WAK = 4800 kWh × 0,3 = 1440 kWh

2. **Energia oddawana do sieci:**
   E_oddana = E_PV - E_auto = 4800 kWh - 1440 kWh = 3360 kWh

3. **Energia pobierana z sieci:**
   E_pobrana = E_zapotrzebowanie - E_auto = 4500 kWh - 1440 kWh = 3060 kWh

4. **Analiza bilansu energetycznego:**
   - Produkcja całkowita: 4800 kWh
   - Zapotrzebowanie całkowite: 4500 kWh
   - Energia zużywana bezpośrednio: 1440 kWh (32% zapotrzebowania)
   - Energia pobierana z sieci: 3060 kWh (68% zapotrzebowania)

**Odpowiedź:** Instalacja fotowoltaiczna produkuje więcej energii (4800 kWh) niż wynosi zapotrzebowanie budynku (4500 kWh), jednak ze względu na niski współczynnik autokonsumpcji (0,3), tylko 1440 kWh jest zużywane bezpośrednio. Pozostałe 3060 kWh musi być pobrane z sieci. Instalacja oddaje do sieci 3360 kWh nadwyżki energii. W sensie ilościowym instalacja pokrywa zapotrzebowanie budynku, ale ze względu na niedopasowanie czasowe produkcji i zużycia, konieczne jest korzystanie z sieci jako magazynu energii.

---

## Praktyczne Wskazówki do Egzaminu

### Organizacja Pracy na Egzaminie

Egzamin ELE.11 trwa 180 minut, co wymaga dobrej organizacji czasu. Poniżej przedstawiono sugerowany podział czasu na poszczególne etapy pracy:

1. **Zapoznanie się z zadaniem (10-15 minut)**
   - Przeczytaj dokładnie całe zadanie
   - Zidentyfikuj, co dokładnie należy obliczyć/wykonać
   - Sprawdź, jakie dane są dostępne w tabelach i załącznikach

2. **Planowanie rozwiązania (10-15 minut)**
   - Określ kolejność działań
   - Wybierz odpowiednie wzory i metody
   - Zaplanuj, które tabele będziesz wypełniać

3. **Wykonanie obliczeń i zadań (120-130 minut)**
   - Systematycznie rozwiązuj kolejne punkty zadania
   - Zapisuj wszystkie obliczenia pośrednie
   - Sprawdzaj jednostki przy każdym kroku

4. **Sprawdzenie i korekta (20-30 minut)**
   - Przejrzyj wszystkie obliczenia
   - Sprawdź, czy odpowiedziałeś na wszystkie pytania
   - Upewnij się, że wypełniłeś wszystkie wymagane tabele

### Najczęstsze Błędy i Jak Ich Unikać

1. **Błędy w jednostkach**
   - **Problem:** Mieszanie jednostek, np. W i kW, m³ i dm³.
   - **Rozwiązanie:** Zawsze zapisuj jednostki przy każdej wartości i sprawdzaj ich zgodność przed wykonaniem obliczeń.

2. **Nieprawidłowe zaokrąglenia**
   - **Problem:** Zbyt wczesne zaokrąglanie wyników pośrednich, co prowadzi do błędów w wyniku końcowym.
   - **Rozwiązanie:** Zaokrąglaj tylko wynik końcowy, a w obliczeniach pośrednich zachowaj jak największą dokładność.

3. **Pomijanie kroków w obliczeniach**
   - **Problem:** Przeskakiwanie etapów obliczeń, co utrudnia sprawdzenie i może prowadzić do błędów.
   - **Rozwiązanie:** Zapisuj każdy krok obliczeń, nawet jeśli wydaje się oczywisty.

4. **Błędna interpretacja danych z tabel**
   - **Problem:** Nieprawidłowe odczytanie lub interpretacja danych z tabel i wykresów.
   - **Rozwiązanie:** Dokładnie analizuj tabele, zwracając uwagę na jednostki i opisy kolumn.

5. **Nieuwzględnienie wszystkich elementów w obliczeniach**
   - **Problem:** Pominięcie niektórych składników w obliczeniach, np. przy sumowaniu pojemności instalacji.
   - **Rozwiązanie:** Twórz listy kontrolne elementów, które należy uwzględnić w obliczeniach.

### Przydatne Wzory i Przekształcenia

Poniżej zestawiono najważniejsze wzory, które warto znać na pamięć przed przystąpieniem do egzaminu:

| Zagadnienie | Wzór | Objaśnienie |
| :--- | :--- | :--- |
| **Moc elektryczna** | P = U × I | P - moc [W], U - napięcie [V], I - prąd [A] |
| **Energia elektryczna** | E = P × t | E - energia [kWh], P - moc [kW], t - czas [h] |
| **Sprawność kolektora** | η = η₀ - (a₁ × ΔT)/E_g - (a₂ × ΔT²)/E_g | η - sprawność, η₀ - sprawność optyczna, a₁, a₂ - współczynniki strat, ΔT - różnica temperatur, E_g - natężenie promieniowania |
| **Powierzchnia kolektorów** | F_kol = (z × (t_z - t_k) × c_w)/(3600 × η × E_kol) | F_kol - powierzchnia [m²], z - zapotrzebowanie na wodę [dm³], t_z, t_k - temperatury wody, c_w - ciepło właściwe wody, η - sprawność, E_kol - energia promieniowania |
| **Liczba kolektorów** | L_k = F_kol / F_ap | L_k - liczba kolektorów, F_kol - wymagana powierzchnia, F_ap - powierzchnia apertury jednego kolektora |
| **Pojemność orurowania** | V_r = π × (d²/4) × L × 10³ | V_r - pojemność [dm³], d - średnica [m], L - długość [m] |
| **Całkowita pojemność instalacji** | V_A = V_k + V_gp + V_w + V_r | V_A - pojemność całkowita, V_k - pojemność kolektorów, V_gp - pojemność grupy pompowej, V_w - pojemność wężownicy, V_r - pojemność orurowania |
| **Współczynnik autokonsumpcji** | WAK = E_auto / E_PV | WAK - współczynnik autokonsumpcji, E_auto - energia zużyta bezpośrednio, E_PV - energia wyprodukowana |

---

## Podsumowanie

Egzamin zawodowy ELE.11 sprawdza praktyczne umiejętności w zakresie eksploatacji urządzeń i systemów energetyki odnawialnej. Kluczem do sukcesu jest zrozumienie podstawowych zasad fizyki, umiejętność wykonywania obliczeń matematycznych oraz znajomość specyfiki instalacji fotowoltaicznych i słonecznych instalacji grzewczych.

Najważniejsze zagadnienia, które należy opanować przed egzaminem, to:
1. Obliczenia związane ze sprawnością kolektorów słonecznych
2. Wymiarowanie instalacji (dobór liczby kolektorów, obliczanie pojemności)
3. Bilanse energetyczne w instalacjach fotowoltaicznych
4. Identyfikacja i usuwanie typowych usterek w instalacjach OZE
5. Planowanie prac serwisowych i przeglądów technicznych

Systematyczne przygotowanie, rozwiązywanie przykładowych zadań oraz zrozumienie wzorów i zależności matematycznych pozwoli na pewne i sprawne wykonanie zadań egzaminacyjnych.

Powodzenia na egzaminie!
