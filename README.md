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

## Class Library
Class library merupakan pustaka kode program yang dapat digunakan bersama pada beberapa
file yang berbeda (konsep modularisasi). Class library menyimpan fungsi-fungsi atau class
object komponen untuk memudahkan dalam proses development aplikasi.

# Contoh class library untuk membuat form.
# Buat file baru dengan nama form.php

```
<?php

/**
 * Nama Class: Form
 * Deskripsi: CLass untuk membuat form inputan text sederhan
 **/
class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Form";
    private $jumField = 0;
    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }
    public function displayForm()
    {
        echo "<form action='" . $this->action . "' method='POST'>";
        echo '<table width="100%" border="0">';
        for ($j = 0; $j < count($this->fields); $j++) {
            echo "<tr><td
align='right'>" . $this->fields[$j]['label'] . "</td>";
            echo "<td><input type='text'
name='" . $this->fields[$j]['name'] . "'></td></tr>";
        }
        echo "<tr><td colspan='2'>";
        echo "<input type='submit' value='" . $this->submit . "'></td></tr>";
        echo "</table>";
    }
    public function addField($name, $label)
    {
        $this->fields[$this->jumField]['name'] = $name;
        $this->fields[$this->jumField]['label'] = $label;
        $this->jumField++;
    }
}
```

## PENJELASAN

