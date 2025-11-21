# ✅ **RINGKASAN BAB 1 & BAB 2 MODUL PRAKTIKUM BASIS DATA**
<a href="file:///C:/Users/LENOVO/AppData/Local/Packages/5319275A.WhatsAppDesktop_cv1g1gvanyjgm/LocalState/sessions/D9C69E31D28821249EE8B345A70ACB31B8EEC17E/transfers/2025-47/MODUL%20PRAKTIKUM%20BASIS%20DATA%20(1).pdf">MODUL PRAKTIKUM BASIS DATA.pdf</a>
---

# **📘 BAB 1 — Review Konversi ER Diagram ke Skema Relasi**

Bab ini membahas bagaimana cara mengubah *Entity Relationship Diagram (ERD)* menjadi **diagram relationship** dan **tabel fisik** di database. Tujuannya adalah agar mahasiswa memahami proses transformasi dari model konseptual ke model logis dan fisik.

### **1. Konsep Utama**

* **Entitas** = objek nyata yang datanya ingin disimpan (misal: Karyawan, Buku, Pasien).
* **Atribut** = informasi yang dimiliki entitas (nama, alamat, tgl_lahir).
* **Primary Key (PK)** = identitas unik (nip, id, kode).
* **Relasi** = hubungan antar entitas (one-to-one, one-to-many, many-to-many).
* **Kardinalitas** = jumlah hubungan (1..1, 1..N, N..M).

### **2. Aturan Konversi ER → Relasi**

Tiap jenis objek di ERD memiliki aturan konversi:

#### 🔹 *Entitas Kuat (Strong Entity)*

Selalu menjadi **1 tabel**. Semua atribut sederhana menjadi kolom. Atribut kunci menjadi **PK**.

#### 🔹 *Composite Attribute*

Atribut bercabang (contoh: alamat → jalan, kota, provinsi) dipecah menjadi beberapa kolom.

#### 🔹 *Multivalue Attribute*

Jika atribut memiliki banyak nilai (contoh: hobi), maka dibuat **tabel baru**.

#### 🔹 *Derived Attribute*

Atribut turunan (umur) tetap jadi kolom.

#### 🔹 *Weak Entity*

Menjadi tabel dan **PK-nya mengandung PK dari entitas kuat** (sebagai **FK**).

#### 🔹 *Relasi One-to-One*

Salah satu tabel akan menyimpan **FK** ke tabel lain.

#### 🔹 *Relasi One-to-Many (1..N)*

FK selalu ditempatkan pada tabel yang berada di sisi “many”.

#### 🔹 *Relasi Many-to-Many (N..M)*

Dikonversi menjadi **tabel relasi** baru berisi:

* kedua FK
* atribut relasi (jika ada)

#### 🔹 *Unary / Recursive Relationship*

Relasi pada tabel yang sama, dibuat dengan kolom FK ke dirinya sendiri.

#### 🔹 *Relasi Ternary*

Menghasilkan **4 tabel**: 3 tabel entitas + 1 tabel relasi.

#### 🔹 *Generalization / Specialization*

Ada dua metode:

1. **Superclass → Subclass** (PK superclass menjadi PK subclass).
2. **Subclass memiliki seluruh atribut superclass.**

### **3. Studi Kasus: Skema Pembayaran Apotik**

ERD apotek terdiri dari:

* Pasien (BPJS & Non-BPJS)
* Resep
* Obat
* Pembayaran
* Pegawai
  Konversi menghasilkan **13 tabel**, seperti:
* PASIEN
* RESEP
* OBAT
* DETAIL_OBAT
* PEMBAYARAN
* RETUR
* KATEGORI_OBAT, dll.

Ini menunjukkan bagaimana ERD kompleks dikonversi ke tabel yang siap digunakan.

---

# **📘 BAB 2 — Pengantar Basis Data & DDL**

Bab ini memperkenalkan dasar-dasar database, DBMS, MySQL, serta perintah dasar DDL.

### **1. Pengertian Database**

Database adalah **kumpulan data yang terorganisir**, disimpan secara sistematis, dan dapat diakses dengan mudah.

### **2. Pengertian DBMS**

DBMS (Database Management System) adalah perangkat lunak untuk:

* membuat,
* mengelola,
* mengakses,
* memanipulasi database.

Contoh DBMS:

* MySQL
* Oracle
* PostgreSQL
* Microsoft SQL Server

### **3. Tentang MySQL**

MySQL adalah DBMS populer yang:

* Cepat, ringan, stabil
* Open source
* Mendukung banyak OS (Windows, Linux, Mac)
* Mendukung multiuser dan multithread
* Menggunakan SQL sebagai bahasa query

XAMPP kini menggunakan MariaDB, namun sintaks sama.

### **4. Aplikasi Server & Client MySQL**

* MySQL Server berjalan sebagai service.
* MySQL Client digunakan melalui CLI/terminal (mysql.exe).
* Untuk login:

  ```
  mysql -u root -p
  ```

### **5. Mengakses MySQL via CMD**

Perintah dasar:

* Masuk folder MySQL
  `cd c:\xampp\mysql\bin`
* Login
  `mysql -u root -p`
* Keluar
  `\q`

### **6. Tipe Data di MySQL**

Contoh:

* INT → angka
* FLOAT → desimal
* DATE → YYYY-MM-DD
* DATETIME → lengkap dengan jam
* VARCHAR → string dinamis
* CHAR → string statis
* BLOB → data binary

### **7. Relational Database**

Database yang terdiri dari tabel-tabel yang saling terhubung melalui **primary key** dan **foreign key**.

### **8. Perintah DDL (Data Definition Language)**

#### 🔹 Membuat Database

```sql
create database praktikum;
```

#### 🔹 Melihat Database

```sql
show databases;
```

#### 🔹 Mengakses Database

```sql
use praktikum;
```

#### 🔹 Menghapus Database

```sql
drop database praktikum;
```

Bab ini memastikan mahasiswa paham bagaimana mengakses MySQL dan menggunakan perintah dasar DDL.

---

# 🖥️ **Apa itu CLI (Command Line Interface)?**

**CLI adalah antarmuka berbasis teks** yang memungkinkan pengguna memberikan perintah ke komputer melalui terminal atau command prompt.

Di MySQL, CLI digunakan untuk:

* menjalankan query
* membuat database
* membuat tabel
* memodifikasi data
* mengakses server MySQL

Contoh CLI MySQL:

```
mysql -u root -p
create database test;
use test;
show tables;
```
