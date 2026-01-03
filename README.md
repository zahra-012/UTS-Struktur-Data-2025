# UTS-Struktur-Data-2025
UTS Struktur Data - Stack &amp; Queue Implementation

## Identitas Mahasiswa
- Nama: siti zahratun aini
- NIM: 103012400293
- Kelas: IF-48-03


---

##  Kompetensi yang Dikerjakan

### 1. STACK - Game Pertarungan 
- **Fitur Program**:
  - ATTACK (Damage: 30)
  - DEFENSE (Damage: 5)
  - UNDO/REDO System
  - Total Damage Calculator
  - Menu Interaktif

##  Cara Menjalankan Program

### Compile & Run

#### Menggunakan Code::Blocks:
1. Buka file `stack_game.cpp` di Code::Blocks
2. Klik menu **Build** → **Build and Run** (atau tekan F9)
3. Program akan berjalan di terminal

---

##  Penjelasan Struktur Program

### Struktur Data Stack
```cpp
struct Stack {
    string info[2025];  // Array untuk menyimpan aksi
    int top;            // Penunjuk elemen teratas
};
```

### Fungsi-Fungsi Utama

#### 1. ADT Stack Dasar
- `create_stack()` - Inisialisasi stack kosong
- `is_empty()` - Mengecek apakah stack kosong
- `is_full()` - Mengecek apakah stack penuh
- `push()` - Menambah elemen ke stack
- `pop()` - Mengeluarkan elemen teratas dari stack

#### 2. Fungsi Khusus Game
- `manageAction()` - Mengelola aksi ATTACK, DEFENSE, UNDO, REDO
- `totalDamage()` - Menghitung total damage dari semua aksi
- `displayStack()` - Menampilkan isi stack
- `displayMenu()` - Menampilkan menu game

---

##  Cara Bermain

### Menu Game:
```
1. ATTACK (Damage: 30)
2. DEFENSE (Damage: 5)
3. UNDO
4. REDO
5. Lihat Stack Aksi
6. Lihat Stack Redo
7. Hitung Total Damage
8. Reset Game
0. Keluar
```

### Contoh Gameplay:
```
Pilih menu: 1 → ATTACK ditambahkan
Pilih menu: 1 → ATTACK ditambahkan
Pilih menu: 2 → DEFENSE ditambahkan
Pilih menu: 5 → Stack: [ATTACK ATTACK DEFENSE]
Pilih menu: 3 → UNDO: DEFENSE dibatalkan
Pilih menu: 4 → REDO: DEFENSE dikembalikan
Pilih menu: 7 → Total Damage = 30 + 30 + 5 = 65
```

### Aturan UNDO/REDO:
- **UNDO**: Membatalkan aksi terakhir dan memindahkannya ke Stack Redo
- **REDO**: Mengembalikan aksi yang dibatalkan dari Stack Redo ke Stack Aksi
- Jika melakukan aksi baru (ATTACK/DEFENSE), Stack Redo akan dikosongkan

---

##  Struktur Repository
```
UTS-Struktur-Data-2025/
│
├── README.md                          # Dokumentasi lengkap
│
└── implementasi/                      # Implementasi program
    └── stack_game.cpp                 # Program Stack Game C++
```

---

##  Penjelasan Algoritma

### 1. Prosedur Push
```
Jika stack tidak penuh:
  - Naikkan nilai top
  - Masukkan data ke posisi top
```

### 2. Fungsi Pop
```
Jika stack kosong:
  - Return string kosong
Jika tidak:
  - Simpan data teratas
  - Turunkan nilai top
  - Return data yang disimpan
```

### 3. Prosedur ManageAction
```
Jika aksi = "UNDO":
  - Pop dari Stack Aksi
  - Push ke Stack Redo
Jika aksi = "REDO":
  - Pop dari Stack Redo
  - Push ke Stack Aksi
Jika aksi lainnya:
  - Push aksi ke Stack Aksi
  - Kosongkan Stack Redo
```

### 4. Fungsi TotalDamage
```
Inisialisasi damage = 0
Selama stack tidak kosong:
  - Pop aksi dari stack
  - Jika ATTACK: tambah damage 30
  - Jika DEFENSE: tambah damage 5
Return total damage
```

---

## Referensi
- Slide Kuliah Struktur Data - Telkom University
- Soal UTS STD S1-IF Ganjil 2025/2026
- Materi Stack (LIFO - Last In First Out)

---


**UTS Struktur Data**
