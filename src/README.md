# Struktur Komponen
===================
-- src
|-- components
|-- pages
|-- App.svelte
|-- main.js
|-- README.md
|-- server.js

## Pengenalan Folder
====================
### Components
Folder berisi banyak komponen Svelte yang nantinya di import dan digunakan didalam folder pages.
di dalam component bisa dibuat folder lagi guna "mewadahi" komponen dengan nama folder yang sama
contoh:
|-- navbar
    |-- Navbar.svelte

jika dalam komponen tersebut memungkinkan untuk buat lagi komponen kecil, bisa dibuat dengan contoh nama folder "utils"
contoh:
|-- navbar
    |-- utils
    |   |-- SearchInput.svelte
    |-- Navbar.svelte

### Pages
Berfungsi untuk membuat halaman Svelte dari beberapa komponen di folder components yang nantinya digunakan sebagai acuan Router di App.svelte
