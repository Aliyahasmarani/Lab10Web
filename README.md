# Lab10Web

# Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab10_php_oop pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

# Buat file baru dengan nama mobil.php

```
<?php

/**
 * Program sederhana pendefinisian class dan pemanggilan class.
 **/
class Mobil
{
    private $warna;
    private $merk;
    private $harga;
    public function __construct()
    {
        $this->warna = "Biru";
        $this->merk = "BMW";
        $this->harga = "10000000";
    }
    public function gantiWarna($warnaBaru)
    {
        $this->warna = $warnaBaru;
    }
    public function tampilWarna()
    {
        echo "Warna mobilnya : " . $this->warna;
    }
}
// membuat objek mobil
$a = new Mobil();
$b = new Mobil();
// memanggil objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();
// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();
```

## PENJELASAN

### 1. Class Mobil:

#### - Properti:
> $warna: Menyimpan informasi warna mobil.

> $merk: Menyimpan informasi merk mobil.

> $harga: Menyimpan informasi harga mobil.

#### - Metode:
> __construct(): Constructor yang dipanggil ketika objek diinisialisasi. Pada constructor, nilai default untuk warna, merk, dan harga diatur.

> gantiWarna($warnaBaru): Metode untuk mengganti warna mobil.

> tampilWarna(): Metode untuk menampilkan informasi warna mobil.

### 2. Pembuatan Objek:

```
$a = new Mobil();
$b = new Mobil();
```
Dua objek, $a dan $b, dibuat dari class Mobil menggunakan operator new.

### 3. Pemanggilan Metode dan Output:

```
// Memanggil objek $a
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();  // Menampilkan warna mobil pertama (default: Biru)
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");  // Mengubah warna mobil pertama menjadi Merah
$a->tampilWarna();  // Menampilkan warna mobil pertama setelah diubah

// Memanggil objek $b
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");  // Mengubah warna mobil kedua menjadi Hijau
$b->tampilWarna();  // Menampilkan warna mobil kedua setelah diubah
```

## OUTPUT

![image](https://github.com/Aliyahasmarani/Lab10Web/assets/115197672/895db2ed-fd1e-4b37-89d6-d323d1623b8e)
