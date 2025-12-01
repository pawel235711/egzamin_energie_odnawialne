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








### 4.2 Przesunięcia bitowe (rozszerzone)

* `x << k` – przesunięcie w lewo o `k` bitów
  → w praktyce: **mnożenie przez** (2^k) (dla dodatnich liczb, bez przepełnienia).

* `x >> k` – przesunięcie w prawo o `k` bitów
  → w praktyce: **dzielenie całkowite przez** (2^k) (część ułamkowa jest ucinana).

Przykład z Twojego tekstu (bez przepełnienia):

```text
00010110₂ (22₁₀) << 1 → 00101100₂ (44₁₀)
00010110₂ (22₁₀) >> 2 → 00000101₂ (5₁₀)
```

---

## 1. Przesunięcie w lewo `<<` – mnożenie przez 2ᵏ

### Przykład 1: 6 << 2

Weźmy liczbę 6:

```text
6₁₀ = 00000110₂  (przykładowo 8-bitowo)
```

Operacja:

```text
00000110₂ << 2
```

**Co się dzieje krok po kroku?**

1. Każdy bit przesuwamy o 2 pozycje w lewo.
2. Z prawej strony **dopisujemy 2 zera**.
3. Bity, które “wypadną” poza zakres po lewej stronie, są tracone (tu nic nie wypada, bo liczba ma małe bity).

Przesunięcie:

```text
   00000110₂   (6)
<< 2
= 00011000₂   (24)
```

Sprawdzenie w dziesiętnym:

* (6 · 2^2 = 6 · 4 = 24)

Czyli:

```text
6 << 2 = 24
```

---

### Przykład 2: 9 << 3

Liczba 9:

```text
9₁₀ = 00001001₂
```

Operacja:

```text
00001001₂ << 3
```

Krok po kroku:

1. Przesuwamy bity o 3 miejsca w lewo.
2. Z prawej strony dopisujemy 3 zera.

```text
   00001001₂   (9)
<< 3
= 01001000₂   (72)
```

Sprawdzenie w dziesiętnym:

* (9 · 2^3 = 9 · 8 = 72)

---

### Przykład 3: co się stanie, gdy bity “wypadną”?

Załóżmy 8-bitowe liczby i weźmy 100:

```text
100₁₀ = 01100100₂
```

Operacja:

```text
01100100₂ << 2
```

Przesunięcie:

```text
   01100100₂  (100)
<< 2
= 10010000₂  (144)
```

* (100 · 2^2 = 100 · 4 = 400),
  ale **w 8 bitach nie zmieści się 400**, więc realnie (na 8 bitach) mamy tylko `10010000₂ = 144`.
* To pokazuje **przepełnienie** – nadmiarowa część wyniku po lewej stronie jest obcinana.

(Jeśli w Twoim materiale nie chcesz wchodzić w przepełnienie, możesz zaznaczyć, że “zakładamy wystarczającą liczbę bitów”.)

---

## 2. Przesunięcie w prawo `>>` – dzielenie całkowite przez 2ᵏ

### Przykład 4: 20 >> 2

Liczba 20:

```text
20₁₀ = 00010100₂
```

Operacja:

```text
00010100₂ >> 2
```

Krok po kroku:

1. Każdy bit przesuwamy o 2 miejsca w prawo.
2. Bity z prawej strony **wypadają** (są tracone).
3. Z lewej strony dopisujemy zera (dla liczb bez znaku / dodatnich).

Przesunięcie:

```text
   00010100₂   (20)
>> 2
= 00000101₂   (5)
```

Sprawdzenie w dziesiętnym:

* (20 ÷ 2^2 = 20 ÷ 4 = 5)

---

### Przykład 5: 5 >> 1 (ucięcie części ułamkowej)

Liczba 5:

```text
5₁₀ = 00000101₂
```

Operacja:

```text
00000101₂ >> 1
```

Przesunięcie:

```text
   00000101₂   (5)
>> 1
= 00000010₂   (2)
```

W dziesiętnym:

* (5 ÷ 2 = 2.5),
* ale przesunięcie bitowe wykonuje **dzielenie całkowite**, więc część ułamkowa `.5` jest **ucięta** → zostaje 2.

Czyli:

```text
5 >> 1 = 2
```

---

### Przykład 6: 19 >> 1 i 19 >> 2

Liczba 19:

```text
19₁₀ = 00010011₂
```

**a) 19 >> 1**

```text
   00010011₂  (19)
>> 1
= 00001001₂  (9)
```

* (19 ÷ 2 = 9.5) → wynik całkowity: 9.

**b) 19 >> 2**

```text
   00010011₂  (19)
>> 2
= 00000100₂  (4)
```

* (19 ÷ 4 = 4.75) → wynik całkowity: 4.

Znów widać: **część ułamkowa jest obcinana**, nie zaokrąglana.

---

## 3. Krótkie podsumowanie “intuicyjne”

* `<< k`

  * przesuwa bity w lewo,
  * z prawej dopisuje `k` zer,
  * **zazwyczaj** odpowiada `x * 2^k`.

* `>> k`

  * przesuwa bity w prawo,
  * z lewej dopisuje zera (dla dodatnich liczb bez znaku),
  * bity z prawej “spadają” i są tracone,
  * **zazwyczaj** odpowiada `x // 2^k` (dzielenie całkowite).

Jeśli chcesz, mogę też dopisać **osobną sekcję o liczbach ujemnych i przesunięciu arytmetycznym vs logicznym**, ale do podstaw zwykle wystarczy to, co powyżej.







Przypomnienie formatu (8 bitów):

* **1 bit – znak**
* **3 bity – cecha (wykładnik z nadmiarem, bias = 3)**
* **4 bity – mantysa** (ułamek po ukrytej jedynce: `1.xxxx₂`)

---

## 7.1 Bias – więcej przykładów

Mamy 3 bity na cechę → można zapisać wartości od 0 do 7.
Bias = 3, więc:

[
E_{\text{prawdziwy}} = E_{\text{zapisany}} - 3
]

Tabela:

| Bity cechy | (E_{\text{zapisany}}) | (E_{\text{prawdziwy}}) | Potęga   |
| ---------- | --------------------- | ---------------------- | -------- |
| 000        | 0                     | 0 − 3 = **−3**         | (2^{-3}) |
| 001        | 1                     | 1 − 3 = **−2**         | (2^{-2}) |
| 010        | 2                     | 2 − 3 = **−1**         | (2^{-1}) |
| 011        | 3                     | 3 − 3 = **0**          | (2^{0})  |
| 100        | 5                     | 5 − 3 = **2**          | (2^{2})  |
| 101        | 5                     | 5 − 3 = **2**          | (2^{2})  |
| 110        | 6                     | 6 − 3 = **3**          | (2^{3})  |
| 111        | 7                     | 7 − 3 = **4**          | (2^{4})  |

Przykład „na czuja”:

* Cecha = `010₂` → 2 → (E_{\text{prawdziwy}} = 2 − 3 = -1) → pomnożymy mantysę przez (2^{-1} = \frac{1}{2}).
* Cecha = `110₂` → 6 → (E_{\text{prawdziwy}} = 3) → pomnożymy mantysę przez (2^3 = 8).

---

## 7.2 Przykłady kodowania liczb

### Przykład 1: zakoduj 0.75₁₀

**Krok 1: na binarny**

0.75₁₀ = ¾ = 0.11₂ (bo 0.5 + 0.25)

**Krok 2: normalizacja do postaci 1.xxxx₂ · 2ᴱ**

0.11₂ = 1.1₂ · 2⁻¹
(przesunęliśmy przecinek o 1 w prawo, więc wykładnik = −1)

Czyli:

* mantysa (z ukrytą jedynką) = 1.1₂
* (E_{\text{prawdziwy}} = -1)

**Krok 3: cecha z biasem**

Bias = 3, więc:
[
E_{\text{zapisany}} = E_{\text{prawdziwy}} + \text{bias} = -1 + 3 = 2
]

2 w binarnym = `010₂` → to są **3 bity cechy**.

**Krok 4: mantysa do 4 bitów**

Mamy 1.1₂ → zapisujemy tylko część ułamkową `.1` jako 4 bity:

* `.1` = `.1000` (uzupełniamy zerami)

Mantysa = `1000`.

**Krok 5: znak**

Liczba dodatnia → znak = 0.

**Cały zapis:**

* znak: `0`
* cecha: `010`
* mantysa: `1000`

**Wynik:** `0 010 1000₂` → **00101000₂**

---

### Przykład 2: zakoduj 5.5₁₀

**Krok 1: na binarny**

5.5₁₀ = 5 + 0.5 = `101.1₂`

**Krok 2: normalizacja**

101.1₂ = 1.011₂ · 2²
(przecinek przesunięty o 2 miejsca w lewo)

* mantysa (z ukrytą jedynką) = 1.011₂
* (E_{\text{prawdziwy}} = 2)

**Krok 3: cecha z biasem**

[
E_{\text{zapisany}} = 2 + 3 = 5
]

5₁₀ = `101₂` → cecha = `101`.

**Krok 4: mantysa 4-bitowa**

1.011₂ → część po przecinku: `.011` → `0110` (dopadamy 0 z prawej)

Mantysa = `0110`.

**Krok 5: znak**

5.5 jest dodatnie → znak = 0.

**Cały zapis:**

* znak: `0`
* cecha: `101`
* mantysa: `0110`

**Wynik:** `0 101 0110₂` → **01010110₂**

**Kontrola (dekodowanie w głowie):**

* cecha `101₂` = 5 → (E_{\text{prawdziwy}} = 5−3 = 2)
* mantysa `0110` → 1.011₂ = 1 + 0 + 0.25 + 0.125 = 1.375
* wartość = 1.375 · 2² = 1.375 · 4 = 5.5 ✔️

---

### Przykład 3: zakoduj −3.25₁₀

**Krok 1: wartość bez znaku na binarny**

3.25₁₀ = 3 + 0.25 = `11.01₂`

**Krok 2: normalizacja**

11.01₂ = 1.101₂ · 2¹

* mantysa (z ukrytą jedynką) = 1.101₂
* (E_{\text{prawdziwy}} = 1)

**Krok 3: cecha**

[
E_{\text{zapisany}} = 1 + 3 = 4
]

4₁₀ = `100₂` → cecha = `100`.

**Krok 4: mantysa (4 bity)**

1.101₂ → część po przecinku `.101` → `1010`

Mantysa = `1010`.

**Krok 5: znak**

Liczba ujemna → znak = **1**.

**Cały zapis:**

* znak: `1`
* cecha: `100`
* mantysa: `1010`

**Wynik:** `1 100 1010₂` → **11001010₂**

---

## 7.3 Przykłady dekodowania (z bitów na liczbę)

Teraz w drugą stronę: mamy 8 bitów i chcemy uzyskać liczbę dziesiętną.

---

### Przykład 4: zdekoduj 00110000₂

Rozbijamy na części:

* znak: `0`
* cecha: `011`
* mantysa: `0000`

**Krok 1: znak**

`0` → liczba dodatnia.

**Krok 2: cecha**

`011₂` = 3₁₀
[
E_{\text{prawdziwy}} = 3 − 3 = 0
]
czyli będziemy mnożyć przez (2^0 = 1).

**Krok 3: mantysa**

Mantysa `0000` oznacza ułamek `0.0000₂`.

Cała część znacząca to:

[
1.0000₂ = 1
]

**Krok 4: wartość**

[
\text{wartość} = (+) 1 · 2^0 = 1
]

**Odpowiedź:** `00110000₂` koduje **1.0₁₀**

---

### Przykład 5: zdekoduj 00101000₂ (to nasza liczba 0.75)

Rozbijmy:

* znak: `0`
* cecha: `010`
* mantysa: `1000`

**Krok 1: znak**

`0` → dodatnia.

**Krok 2: cecha**

`010₂` = 2
[
E_{\text{prawdziwy}} = 2 − 3 = -1
]

**Krok 3: mantysa**

Mantysa = `1000` → to ułamek `0.1000₂` za ukrytą jedynką:
całość = `1.1000₂`.

Policzmy:

* 1 = 1
* 0.1000₂ = 1·(1/2) = 0.5

Razem: 1 + 0.5 = 1.5.

**Krok 4: wartość**

[
\text{wartość} = (+) 1.5 · 2^{-1} = 1.5 · 0.5 = 0.75
]

**Odpowiedź:** 00101000₂ → **0.75₁₀**

---

### Przykład 6: zdekoduj 10100100₂ (przykład z liczbą ujemną)

Rozbicie:

* znak: `1`
* cecha: `010`
* mantysa: `0100`

**Krok 1: znak**

`1` → liczba ujemna.

**Krok 2: cecha**

`010₂` = 2 →
[
E_{\text{prawdziwy}} = 2 - 3 = -1
]

**Krok 3: mantysa**

Mantysa `0100` → ułamek `0.0100₂`
Całość: `1.0100₂`.

Liczbowo:

* 1 = 1
* 0.0100₂ = 1·(1/4) = 0.25

Razem: 1.25.

**Krok 4: wartość**

[
\text{wartość} = (-) 1.25 · 2^{-1} = -1.25 · 0.5 = -0.625
]

**Odpowiedź:** 10100100₂ → **−0.625₁₀**








[
(-1)^{znak} · 1.mantysa₂ · 2^{E_{\text{prawdziwy}}}
]

---

## 🔹 Krok 1. Zamiana liczby dziesiętnej na binarną

Liczba:
[
1000.25_{10} = 1000 + 0.25
]

### Część całkowita:

1000₁₀ =
512 + 256 + 128 + 64 + 32 + 8 →
→ bity: **1111101000₂**

Czyli:
[
1000_{10} = 1111101000_2
]

### Część ułamkowa:

0.25 × 2 = 0.5 → bit = 0
0.5 × 2 = 1.0 → bit = 1
→ koniec (mamy dokładnie 0.25)

[
0.25_{10} = 0.01_2
]

### Połączmy:

[
1000.25_{10} = 1111101000.01_2
]

---

## 🔹 Krok 2. Normalizacja binarna

Chcemy postać:
[
1.xxxxx₂ · 2^E
]

Przesuwamy przecinek, aż zostanie **1.11110100001₂**

Ile przesunięć?
Przecinek był za ostatnim zerem (po „1000.01”), a teraz jest po pierwszej jedynce — **9 miejsc w lewo**.

[
1111101000.01_2 = 1.11110100001_2 · 2^9
]

---

## 🔹 Krok 3. Ustal elementy float-a

| składnik               | wartość                            |
| ---------------------- | ---------------------------------- |
| znak                   | 0 (liczba dodatnia)                |
| mantysa                | część po przecinku = `11110100001` |
| (E_{\text{prawdziwy}}) | 9                                  |

---

## 🔹 Krok 4. Oblicz cechę (z biasem)

Dla uproszczenia przyjmijmy format **8-bitowy** (1 znak, 3 cecha, 4 mantysa), jak wcześniej:
Bias = 3 →
[
E_{\text{zapisany}} = 9 + 3 = 12_{10} = 1100_2
]

Ale 3 bity nie wystarczą, bo 1100 ma 4 bity.
Więc weźmy **format 16-bitowy (half-precision)**, który ma:

* 1 bit znak
* 5 bitów cechy (bias = 15)
* 10 bitów mantysy

[
E_{\text{zapisany}} = 9 + 15 = 24_{10} = 11000_2
]

---

## 🔹 Krok 5. Zbuduj zapis binarny IEEE-style

| Pole               | Bity       | Wartość |
| ------------------ | ---------- | ------- |
| znak               | 1          | 0       |
| cecha (5 bitów)    | 11000      |         |
| mantysa (10 bitów) | 1111010000 |         |

👉 Uwaga: mantysę zaokrąglamy do 10 bitów po przecinku.
(Mieliśmy `11110100001`, więc ucinamy ostatnie 1).

---

### ✅ Wynikowy zapis:

```
0 | 11000 | 1111010000
```

W całości:

```
0110001111010000₂
```

---

## 🔹 Krok 6. Sprawdzenie (dekodowanie w drugą stronę)

* cecha = `11000₂` = 24
  → (E_{\text{prawdziwy}} = 24 - 15 = 9)
* mantysa = `1.1111010000₂`
  = 1 + 0.5 + 0.25 + 0.125 + 0.0625 + 0 + 0.015625 = **1.953125**

[
\text{Wartość} = 1.953125 · 2^9 = 1.953125 · 512 = 999.9999 \approx 1000.0
]

Bingo 🎯 — lekka różnica z powodu ograniczenia mantysy (10 bitów).

---

## 🔹 7. Intuicyjnie: co tu się dzieje?

| krok | co robisz                           | efekt                   |
| ---- | ----------------------------------- | ----------------------- |
| 1    | zamieniasz 1000.25 na binarny       | 1111101000.01           |
| 2    | normalizujesz                       | 1.11110100001 × 2⁹      |
| 3    | dodajesz bias (np. +15)             | zapisany wykładnik = 24 |
| 4    | ucinasz mantysę do długości formatu | 10 bitów                |
| 5    | sklejasz znak + cecha + mantysa     | `0 11000 1111010000`    |

---

## 🔹 8. Bonus – co by było z 0.25?

Zróbmy mini wersję dla porównania:

[
0.25_{10} = 0.01_2 = 1.0_2 · 2^{-2}
]
[
E_{\text{prawdziwy}} = -2,\quad E_{\text{zapisany}} = 15 - 2 = 13_{10} = 01101_2
]

→
znak = 0
cecha = 01101
mantysa = 0000000000

wynik:

```
0 01101 0000000000
```

czyli w half-precision zapis binarny dla 0.25 = `0011010000000000`.

---

## 🔹 Podsumowanie (1000.25 w FP)

| Format              | Bias | Cecha (E_zap)     | Mantysa (binarnie)      | Cały zapis                            |
| ------------------- | ---- | ----------------- | ----------------------- | ------------------------------------- |
| 8-bit (teoretyczny) | 3    | (za mały zakres)  | —                       | —                                     |
| 16-bit (half)       | 15   | 11000₂            | 1111010000              | **0110001111010000₂**                 |
| 32-bit (single)     | 127  | 136₁₀ = 10001000₂ | 11110100001000000000000 | **01000100011110100001000000000000₂** |

---



