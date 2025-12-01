## 0. Wprowadzenie

Komputer wszystko widzi jako **ciąg bitów**: 0 i 1.
Żeby rozumieć, co on z tym robi, warto ogarnąć:

* różne **systemy liczbowe** (dziesiętny, binarny, szesnastkowy),
* **jak zamieniać** liczby między tymi systemami,
* jak zapisywane są **liczby ujemne**,
* czym są **operacje bitowe** (AND, OR, XOR, NOT, przesunięcia),
* jak to wszystko wykorzystać w **praktycznych zadaniach**.

Ten tutorial prowadzi Cię krok po kroku:

1. Systemy liczbowe
2. Reprezentacja liczb ujemnych
3. Operacje bitowe
4. Zadania od podstaw do zaawansowanych
5. Krótko o liczbach zmiennoprzecinkowych (FP)
6. Strategie rozwiązywania zadań

---

## 1. Systemy liczbowe – „język” komputera

Na co dzień używamy systemu **dziesiętnego (podstawa 10)**.
Komputer używa systemu **dwójkowego (podstawa 2)**.
Często wygodnie jest też korzystać z **szesnastkowego (podstawa 16)**.

### 1.1 Najważniejsze systemy

| System         | Podstawa | Dozwolone cyfry       | Przykład | Gdzie się przydaje               |
| -------------- | -------- | --------------------- | -------- | -------------------------------- |
| Dziesiętny     | 10       | 0–9                   | 42       | normalne liczenie                |
| Dwójkowy (bin) | 2        | 0, 1                  | 101010₂  | wewnętrznie w komputerze         |
| Szesnastkowy   | 16       | 0–9, A, B, C, D, E, F | 2A₁₆     | adresy pamięci, kolory (#FF00FF) |

Cyfry w systemie 16:

* A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.

### 1.2 Dlaczego HEX jest wygodny?

Każda **jedna cyfra HEX** odpowiada **dokładnie 4 bitom** (tzw. nibble):

* 0000₂ = 0₁₆
* 1011₂ = B₁₆
* 1111₂ = F₁₆

Przykład:

* 1011 1100₂
  – dzielimy na grupy po 4 bity: `1011` `1100`
  – 1011₂ = B, 1100₂ = C
  – wynik: BC₁₆

Duże, długie liczby binarne zapisane w HEX są po prostu **czytelniejsze**.

---

## 2. Konwersje między systemami

### 2.1 Z dziesiętnego na binarny – „dzielenie przez 2”

**Przepis:**

1. Dzielisz liczbę przez 2.
2. Zapisujesz **resztę** (0 albo 1).
3. Wynik dzielenia znowu dzielisz przez 2.
4. Powtarzasz aż wynik będzie 0.
5. Odczytujesz reszty **od dołu do góry**.

**Przykład:** 29₁₀ → ?₂

```text
29 ÷ 2 = 14, reszta 1
14 ÷ 2 =  7, reszta 0
 7 ÷ 2 =  3, reszta 1
 3 ÷ 2 =  1, reszta 1
 1 ÷ 2 =  0, reszta 1
```

Reszty od dołu: **11101₂**

> 29₁₀ = 11101₂

### 2.2 Z binarnego na dziesiętny – „waga bitów”

Każdy bit ma swoją wagę:
od prawej: 2⁰, 2¹, 2², 2³, ...

**Przykład:** 10110₂ → ?₁₀

```text
 1   0   1   1   0
 ↑   ↑   ↑   ↑   ↑
2⁴ 2³  2²  2¹  2⁰
```

Liczymy:

* 1·2⁴ = 16
* 0·2³ = 0
* 1·2² = 4
* 1·2¹ = 2
* 0·2⁰ = 0

Suma: 16 + 0 + 4 + 2 + 0 = **22**

> 10110₂ = 22₁₀

---

## 3. Jak komputer zapisuje liczby ujemne?

Computer musi rozróżnić liczby dodatnie i ujemne.
Popularne sposoby:

1. **Znak-moduł (ZM)** – prosty, ale niewygodny
2. **Uzupełnienie do dwóch (U2)** – standard w praktyce

### 3.1 Znak-moduł (ZM)

* Najstarszy bit (MSB) = **znak**

  * 0 → liczba dodatnia
  * 1 → liczba ujemna
* Pozostałe bity = wartość bezwzględna.

Na 8 bitach:

* +5 → 00000101₂
* -5 → 10000101₂

**Wady:**

* są **dwa zera**: +0 (00000000₂) i -0 (10000000₂),
* dodawanie/odejmowanie jest skomplikowane.

### 3.2 Uzupełnienie do dwóch (U2) – standard

W U2:

* liczby **dodatnie** – jak zwykły zapis binarny,
* liczby **ujemne** – specjalna konstrukcja z „odwróceniem bitów + 1”.

**Jak zakodować np. -5 na 8 bitach?**

1. Weź wartość bezwzględną: 5₁₀ → 00000101₂
2. Zaneguj wszystkie bity (NOT): 11111010₂
3. Dodaj 1:
   11111010₂ + 00000001₂ = 11111011₂

> -5₁₀ = 11111011₂ (U2, 8 bitów)

**Jak odczytać liczbę ujemną z U2?**

Załóżmy 11111011₂ (8 bitów):

1. MSB = 1 → liczba ujemna.
2. Negujemy wszystkie bity: 00000100₂
3. Dodajemy 1: 00000100₂ + 1 = 00000101₂ → 5
4. Dodajemy minus: -5.

**Zalety U2:**

* jest tylko **jedno zero**: 00000000₂,
* **dodawanie i odejmowanie** działa tak samo na dodatnich i ujemnych,
* procesor ma prostszą logikę.

---

## 4. Operacje bitowe – AND, OR, XOR, NOT, przesunięcia

Najpierw intuicja:

* liczba = ciąg bitów, np. 10101010₂
* operacje bitowe zmieniają te bity „jeden pod drugim”.

### 4.1 Podstawowe operacje

Pokażmy na pojedynczych bitach (a, b ∈ {0,1}).

#### AND (koniunkcja)

„1 tylko wtedy, gdy oba bity są 1”

| a | b | a AND b |
| - | - | ------- |
| 0 | 0 | 0       |
| 0 | 1 | 0       |
| 1 | 0 | 0       |
| 1 | 1 | 1       |

Przykład na bajtach:

```text
 11001010
&10101100
=10001000
```

#### OR (alternatywa)

„1 jeśli przynajmniej jeden bit to 1”

| a | b | a OR b |
| - | - | ------ |
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 1      |

#### XOR (exclusive OR)

„1 jeśli bity są **różne**”

| a | b | a XOR b |
| - | - | ------- |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

Przydatne np. do przełączania bitów.

#### NOT (negacja, ~)

Zamienia 0 ↔ 1

* ~0 = 1
* ~1 = 0

Na 8 bitach: ~10110000₂ = 01001111₂

---

### 4.2 Przesunięcia bitowe

* `x << k` – przesunięcie w lewo o k bitów
  → w praktyce: **mnożenie przez 2ᵏ** (dla dodatnich liczb bez przepełnienia).
* `x >> k` – przesunięcie w prawo o k bitów
  → w praktyce: **dzielenie całkowite przez 2ᵏ**.

Przykład (bez przepełnienia):

* 00010110₂ (22₁₀) << 1 → 00101100₂ (44₁₀)
* 00010110₂ (22₁₀) >> 2 → 00000101₂ (5₁₀)

---

### 4.3 Maski bitowe – operacje na konkretnych bitach

**Maska bitowa** = liczba, w której z góry ustawiamy odpowiednie bity na 1, a inne na 0.
Potem używamy AND / OR / XOR / NOT, żeby:

* sprawdzać bity,
* ustawiać bity,
* zerować bity,
* przełączać bity.

Załóżmy, że numerujemy bity od 0 (najmłodszy bit, LSB).

#### Sprawdzanie bitu `k`

```text
if (x AND (1 << k)) != 0:
    // bit k jest 1
else:
    // bit k jest 0
```

#### Ustawianie bitu `k` na 1

```text
x = x OR (1 << k)
```

#### Zerowanie bitu `k` (ustawienie na 0)

```text
x = x AND (~(1 << k))
```

#### Przełączanie bitu `k` (0→1, 1→0)

```text
x = x XOR (1 << k)
```

---

## 5. Zadania praktyczne – poziom podstawowy

### Zadanie 1: Konwersja DEC → BIN

**Treść:** Zamień 42₁₀ na zapis binarny.

**Rozwiązanie (dzielenie przez 2):**

```text
42 ÷ 2 = 21, reszta 0
21 ÷ 2 = 10, reszta 1
10 ÷ 2 =  5, reszta 0
 5 ÷ 2 =  2, reszta 1
 2 ÷ 2 =  1, reszta 0
 1 ÷ 2 =  0, reszta 1
```

Czytamy reszty od dołu: **101010₂**

> 42₁₀ = 101010₂

---

### Zadanie 2: Konwersja BIN → DEC

**Treść:** Zamień 110101₂ na system dziesiętny.

**Rozwiązanie:**

```text
1·2⁵ + 1·2⁴ + 0·2³ + 1·2² + 0·2¹ + 1·2⁰
= 32 + 16 + 0 + 4 + 0 + 1
= 53
```

> 110101₂ = 53₁₀

---

### Zadanie 3: Sprawdzanie parzystości bitowo

**Idea:**
Liczba jest parzysta, jeśli **najmłodszy bit (LSB)** jest 0.

**Pseudokod:**

```text
if (x AND 1) == 0:
    wypisz "Liczba jest parzysta"
else:
    wypisz "Liczba jest nieparzysta"
```

---

## 6. Zadania średnio-zaawansowane

### Zadanie 4: Tworzenie liczby w U2

**Treść:** Zapisz -10 w 8-bitowym kodzie U2.

1. 10₁₀ → 00001010₂
2. Negacja: 11110101₂
3. Dodaj 1: 11110101₂ + 1₂ = 11110110₂

> -10₁₀ = 11110110₂ (U2, 8 bitów)

---

### Zadanie 5: Zliczanie ustawionych bitów (liczba jedynek)

**Treść:**
Napisz algorytm, który dla liczby x liczy, ile w jej zapisie binarnym jest 1.

**Proste rozwiązanie:**

```text
licznik = 0
while x > 0:
    if (x AND 1) == 1:
        licznik = licznik + 1
    x = x >> 1
wypisz licznik
```

**Szybszy trik (algorytm Kernighana):**

```text
licznik = 0
while x != 0:
    x = x AND (x - 1)  // usuwa ostatnią jedynkę
    licznik = licznik + 1
```

---

### Zadanie 6: Odwracanie kolejności bitów (dla 8 bitów)

**Treść:**
Odwróć kolejność bitów 8-bitowej liczby.
Przykład: 10110000₂ → 00001101₂.

**Idea:**
„Zdejmujemy” LSB z liczby wejściowej i dokładamy go na koniec liczby wynikowej.

**Pseudokod:**

```text
wynik = 0
for i od 0 do 7:
    wynik = wynik << 1          // robimy miejsce na nowy bit
    if (wejscie AND 1) == 1:    // jeśli LSB wejścia to 1
        wynik = wynik OR 1      // ustawiamy LSB wyniku na 1
    wejscie = wejscie >> 1      // przesuwamy wejście w prawo
wypisz wynik
```

---

### Zadanie 7: Czy 3 najstarsze bity = 3 najmłodsze?

**Treść (8 bitów):**
Dla liczby A sprawdź, czy **3 najstarsze** bity są takie same jak **3 najmłodsze**.

**Kroki:**

1. 3 najmłodsze bity: maska 0b00000111 = 7₁₀

   ```text
   najmlodsze = A AND 7
   ```

2. 3 najstarsze bity: trzeba przesunąć A tak, żeby 3 MSB trafiły na pozycję 0–2.
   Na 8 bitach oznacza to przesunięcie o 5 w prawo:

   ```text
   najstarsze = A >> 5   // teraz 3 najstarsze wiszą jako 3 najmłodsze
   ```

3. Porównujemy:

```text
if najmlodsze == najstarsze:
    wypisz "TAK, są identyczne"
else:
    wypisz "NIE, są różne"
```

---

## 7. Liczby zmiennoprzecinkowe (FP) – mini-wprowadzenie

Wyobraź sobie zapis w stylu **notacji naukowej**:

> 6,25 · 10³,  1,01 · 2⁻³  itd.

W zapisie FP (np. uproszczony 8-bitowy format):

* 1 bit – **znak**
* 3 bity – **cecha** (wykładnik z nadmiarem, tzw. bias)
* 4 bity – **mantysa** (część ułamkowa w systemie binarnym, zwykle z ukrytą jedynką z przodu).

### 7.1 Co to jest nadmiar (bias)?

Jeśli cecha ma 3 bity, to można zapisać 0…7.
Umawiamy się na **nadmiar 3** (bias = 3).

* zapisany wykładnik E_zap = E_prawdziwy + bias
* czyli E_prawdziwy = E_zap − bias.

Przykład: cecha 101₂ = 5₁₀

* E_prawdziwy = 5 − 3 = 2 → potęga 2².

### 7.2 Przykład kodowania liczby

**Przykład z oryginału (uproszczony):**
Załóżmy format: 1 bit znak, 3 bity cecha (bias = 3), 4 bity mantysa.

Chcemy zakodować liczbę 2.5₁₀.

1. Na binarny: 2.5₁₀ = 10.1₂

2. Normalizacja: chcemy formę 1.xxxx₂ · 2ᴱ

   10.1₂ = 1.01₂ · 2¹

3. Składniki:

   * znak = 0 (liczba dodatnia)
   * E_prawdziwy = 1 → E_zap = 1 + 3 = 4 = 100₂
   * mantysa = część po przecinku: .01 → 0100 (uzupełniamy do 4 bitów)

4. Połączenie:

   znak | cecha | mantysa
   0    | 100   | 0100

> Zapis: 01000100₂ (w naszym uproszczonym FP)

Nie musisz tego znać na pamięć – ważne jest zrozumienie idei:
**normalizujemy**, zapisujemy wykładnik z nadmiarem, mantysę jako ułamek binarny.

---

## 8. Zadania zaawansowane – skrótowo

### 8.1 Dodawanie liczb w formacie FP

Schemat ogólny:

1. **Konwersja** obu liczb na format FP (znak, cecha, mantysa).
2. **Wyrównanie wykładników** – przesuwasz mantysę tej liczby, która ma mniejszą cechę.
3. **Dodajesz mantysy** (uwzględniając znaki).
4. **Normalizujesz wynik** – znowu doprowadzasz do postaci 1.xxx₂ · 2ᴱ.
5. **Aktualizujesz cechę** (dodajesz bias).
6. Jeśli trzeba, obcinasz mantysę do dostępnej liczby bitów → powstaje błąd zaokrąglenia.

---

### 8.2 Dodawanie w U2 i overflow

Przykład (8 bitów): dodaj dwie liczby w U2 i sprawdź overflow.

**Zasada (U2, overflow):**

* jeśli dodajesz dwie **dodatnie** i wyjdzie **ujemna** → overflow,
* jeśli dodajesz dwie **ujemne** i wyjdzie **dodatnia** → też overflow.

Patrzysz tylko na **MSB** (bity znaków):

* MSB(a), MSB(b), MSB(wyniku) → na ich podstawie stwierdzasz, czy było przepełnienie.

---

### 8.3 Konwersja 17.613₁₀ na system o podstawie 3 (dokładność do 5 miejsc po przecinku)

**Część całkowita (17):** dzielenie przez 3

```text
17 ÷ 3 = 5, reszta 2
 5 ÷ 3 = 1, reszta 2
 1 ÷ 3 = 0, reszta 1
```

Odczytując reszty od dołu: **122₃**

**Część ułamkowa (0.613):** mnożenie przez 3

```text
0.613 * 3 = 1.839 → cyfra: 1
0.839 * 3 = 2.517 → cyfra: 2
0.517 * 3 = 1.551 → cyfra: 1
0.551 * 3 = 1.653 → cyfra: 1
0.653 * 3 = 1.959 → cyfra: 1
```

Daje to w przybliżeniu: 0.12111₃

> 17.613₁₀ ≈ 122.12111₃ (do 5 miejsc po przecinku)

---

### 8.4 Odczyt liczby z tablicy bitów w U2 (n bitów)

Załóżmy tablica A[0..n-1]:

* A[0] = LSB,
* A[n-1] = MSB (bit znaku).

W U2:

* bity od 0 do n-2 mają **dodatnie wagi**: 2⁰, 2¹, ..., 2ⁿ⁻²
* bit A[n-1] ma **ujemną wagę**: −2ⁿ⁻¹.

**Pseudokod:**

```text
wartosc = 0

// dodatnia część:
for i od 0 do n-2:
    if A[i] == 1:
        wartosc = wartosc + 2^i

// ujemna część (bit znaku)
if A[n-1] == 1:
    wartosc = wartosc - 2^(n-1)

wypisz wartosc
```

---

## 9. Wskazówki i strategie rozwiązywania zadań

### 9.1 Systemy liczbowe

1. **Zapisuj wszystkie kroki** – łatwo się pomylić o 1.
2. Przy konwersji **bin → dec** zawsze wypisz wagi bitów: 2⁰, 2¹, 2², …
3. Zawsze dopytaj się sam siebie:

   * „Czy wynik ma sens?”
   * „Czy liczba w nowym systemie mniej więcej pasuje do wielkości oryginału?”

### 9.2 Operacje bitowe

1. Zawsze **rozpisuj liczby binarnie** pod sobą.
2. Przy bitach używaj masek – nie zgaduj, pisz `1 << k`.
3. Ćwicz na małych liczbach (8 bitów) – łatwiej zauważyć błędy.

