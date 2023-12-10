---
nav_order: 11
title: Recapitulare 1
has_children: false
---

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Recapitulare

## Missing Number

Având un șir de numere distincte `nums` care conține `n` elemente distincte din intervalul `[0, n]`, întoarceți singurul număr din acest interval care lipsește din șir.

Prototipul funcției este:

```Python
def missing_number(nums: List[int]) -> int:
    pass
```

Exemple:


```text
Input: nums = [3, 0, 1]
Output: 2

Input: nums = [0, 1]
Output: 2

Input: nums = [9, 6, 4, 2, 3, 5, 7, 0, 1]
Output: 8
```

## Move Zeroes

Având un șir de numere întregi `nums`, mutați toate zerourile la sfârșitul acestuia păstrând ordinea relativă a elementelor nenule.
Rețineți că trebuie să faceți aceasta in-place (în același vector fără a-i face o copie).

Prototipul funcției este:

```Python
def move_zeroes(nums: List[int]) -> None:
    pass
```

Exemple:


```text
Input: nums = [0, 1, 0, 3, 12]
Output: [1, 3, 12, 0, 0]

Input: nums = [0]
Output: [0]
```

## Two Sum

Având un tablou de numere întregi `nums`` și un număr întreg `target``, returnați indicii celor două numere astfel încât să se adune la valoarea `target`.
Puteți presupune că fiecare set de date va avea exact o soluție și că nu veți folosi de două ori același element.
Puteți returna răspunsul în orice ordine.

Prototipul funcției este:

```Python
def two_sum(nums: List[int], target: int) -> List[int]:
    pass
```

Exemple:


```text
Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explicație: nums[0] + nums[1] == 9

Input: nums = [3, 2, 4], target = 6
Output: [1, 2]

Input: nums = [3, 3], target = 6
Output: [0, 1]
```

## First Unique Character in a String

Având o șir `s`, găsiți primul caracter care nu se repetă și returnați indexul său. Dacă acesta nu există, returnați `-1`.

Prototipul funcției este:

```Python
def first_uniq_char(s: str) -> int:
    pass
```

Exemple:


```text
Input: s = "leetcode"
Output: 0

Input: s = "loveleetcode"
Output: 2

Input: s = "aabb"
Output: -1
```

## Merge Arrays

Sunt date două liste de numere întregi, `nums1` și `nums2`, sortate în ordine crescătoare. Interclasați `nums1` și `nums2` într-o singură listă care să conțină elementele ambelor liste sortate în ordine crescătoare.

Prototipul funcției este:

```Python
def merge(nums1: List[int], nums2: List[int]) -> List[int]:
```

Exemple:

```text
Input: nums1 = [1, 2, 3], nums2 = [2, 5, 6]
Output: [1, 2, 2, 3, 5, 6]

Input: nums1 = [1], nums2 = []
Output: [1]
```

## Remove Duplicates from Sorted Array

Având un vector de numere întregi `nums` sortat în ordine crescătoare, eliminați duplicatatele in-place astfel încât fiecare element unic să apară o singură dată. Ordinea relativă a elementelor trebuie păstrată. Apoi întoarceți numărul de elemente unice din `nums`.

Considerând că numărul de elemente unice din `nums` ca fiind `k`, cerința este să:

- Modificați vectorul `nums` astfel încât primele `k` elemente să conțină elementele unice în ordinea în care au apărut inițial în `nums`. Elementele rămase din `nums` nu sunt importante, la fel și dimensiunea lui `nums`.
- Întoarceți valoarea `k`.

Prototipul funcției este:

```Python
def remove_duplicates(nums: List[int]) -> int:
```

Exemple:

```text
Input: nums = [1, 1, 2]
Output: 2, nums = [1, 2, _]
Explicație: Funcția întoarce 2. Nu contează valoarea ultimului element rămas în `nums`

Example 2:

Input: nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]
Output: 5, nums = [0, 1, 2, 3, 4, _, _, _, _, _]
Explicație: Funcția întoarce 5. Nu contează valoarea ultimelor element rămase în `nums`
```
