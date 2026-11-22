# Programming, Pseudocode (Rinaldi Munir ITB / Telkom University), Go, and C++

Use this reference when course materials, summaries, or exercises involve programming, algorithms, data structures, ADT design, Notasi Algoritmik pseudocode, Go (Golang), or C++.

## 1. Reference-First Rule

- **User/course example wins:** If the user supplies a reference example, lecturer slide, or practicum template, adopt its **exact** notation (assignment operator, parameter keywords, `I.S./F.S.` comment style, ADT/type names, indexing base, pointer syntax, and file layout).
- **Separate pseudocode from implementation:** Keep Notasi Algoritmik pseudocode and runnable code (Go / C++) in distinct, clearly labeled sections. Never leak C++/Go syntax (`cout`, `fmt.Scan`, `++`, `{}` blocks) into Notasi Algoritmik, and never leave pseudocode keywords inside runnable Go/C++ files.
- **1-to-1 logic parity:** When both pseudocode and Go/C++ are produced for the same problem, keep algorithm logic, loop bounds, and edge-case handling aligned. Explicitly note any language adaptation (e.g., `1`-based array in pseudocode mapped to `0`-based indexing in Go/C++).

---

## 2. Notasi Algoritmik / Pseudocode (Rinaldi Munir ITB & Telkom University)

Follow standard Indonesian academic **Notasi Algoritmik** (Rinaldi Munir — STEI ITB, and Telkom University ADT/Struktur Data conventions):

### Core Structure
- **Program:** `program NamaProgram` → `kamus` → `algoritma` → `endprogram`
- **Procedure:**
  ```text
  procedure namaProsedur(input/output L : List, input x : Infotype, output P : Address)
  { I.S. kondisi awal sebelum prosedur dijalankan.
    F.S. kondisi akhir setelah prosedur dijalankan. }
  Kamus
      { variabel lokal }
  Algoritma
      { langkah-langkah }
  endprocedure
  ```
- **Function:**
  ```text
  function namaFungsi(input L : List) -> TipeHasil
  { Mengembalikan ... }
  Kamus
      { variabel lokal }
  Algoritma
      { langkah-langkah }
      return hasil
  endfunction
  ```

### Types, Records, Arrays, and Pointers
- Type aliases: `type Infotype : integer`
- Records / structs:
  ```text
  type DataMahasiswa <
      nim : string,
      nama : string,
      nilai : real
  >
  ```
- Fixed arrays: `type TabInt : array [1..NMAX] of integer` (follow source indexing: `1..N` or `0..N-1`)
- Pointers & dynamic nodes:
  - `type Address : pointer to ElmList`
  - `type ElmList < info : Infotype, next : Address >`
  - Field access: `L.first` (record field), `P->info` / `P->next` (pointer-to-record field)
  - Null & memory primitives: `NIL`, `allocate(P)`, `deallocate(P)`

### Operators & Control Flow
- **Assignment vs. Equality (pick one style matching the supplied reference and stay 100% consistent):**
  - *Classic Rinaldi Munir (ITB):* `<-` for assignment, `=` for equality, `!=` or `≠` for inequality.
  - *Telkom University ADT variant:* `=` for assignment, `==` for equality, `!=` for inequality, `->` for function return type and pointer field access.
  - If no reference example is given, state the chosen operator convention in one brief line at the top.
- **Control blocks** (always close blocks explicitly):
  - `if <cond> then ... else ... endif`
  - `while <cond> do ... endwhile`
  - `for i <- a to b do ... endfor` (or `downto`)
  - `repeat ... until <cond>`
  - `depend on` / `case`
- **I/O:** `input(x)`, `output(x)`
- **Parameter modes:** Always mark `input`, `output`, or `input/output` on procedure parameters, and `input` on function parameters.

---

## 3. Go (Golang)

- **Course-appropriate Go:** Match the course's Go level (e.g., `package main`, `fmt.Scan` / `fmt.Print` for introductory algorithms, `bufio.NewScanner` / `bufio.NewWriter` when large I/O or line-based input requires it; fixed-size arrays `[NMAX]T` with length `n` when the course models static arrays, or slices `[]T` when dynamic).
- **Parameter mapping from pseudocode:**
  - `input x : T` → pass by value `x T` (or read-only slice/pointer if large struct)
  - `output` / `input/output x : T` → pointer parameter `x *T` (or explicit return values if idiomatic and allowed by the prompt)
- **Compilable, clean code:**
  - No unused imports or unused variables (Go fails to compile on them).
  - Keep struct/type definitions, helper functions, and `main()` cleanly ordered and copy-ready.
  - Map `while` loops cleanly to Go's `for cond { ... }` and `repeat ... until cond` to `for { ...; if cond { break } }`.
- **Verification:** Run `go run` / `go test` on meaningful normal and boundary cases when execution tools exist; otherwise manually verify types, pointer dereferences, array/slice bounds, and termination.

---

## 4. C++

- **C++ is not C:** Use standard C++ idioms and headers (`<iostream>`, `<string>`, etc.) unless the course explicitly restricts them. Preserve provided ADT names, typedefs, `define`/`#ifndef` guards, and indexing conventions.
- **Modular ADT layout:** When the course/practicum splits ADT files, present `header.h`, `implementation.cpp`, and `main.cpp` in clearly separated, copyable code blocks with matching filenames.
- **Parameter mapping from pseudocode:**
  - `input x : T` → `T x` or `const T& x`
  - `output` / `input/output x : T` → reference `T& x` (e.g., `List &L`, `address &P`)
- **Pointer & boundary safety:**
  - Always check empty structure (`first == nullptr`/`NIL`), single-element structure (`first == last`), insertion/deletion at head, middle, and tail, pointer reconnection order (connect new node before breaking predecessor link), and detaching deleted nodes (`P->next = nullptr`, `P->prev = nullptr`) before reuse.
- **Verification:** Compile (e.g., `g++ -Wall -Wextra`) and run small test cases when execution tools exist; otherwise trace declarations, pointer updates, and edge cases manually and state that compilation/execution was not run.
