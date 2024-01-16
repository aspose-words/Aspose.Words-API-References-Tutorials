---
title: Buat Tautan Di Word
linktitle: Buat Tautan Di Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tautan di Word antara TextBox di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-textboxes/create-a-link/
---
Panduan langkah demi langkah ini menjelaskan cara membuat tautan di Word antara dua kotak teks di dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Anda akan mempelajari cara mengonfigurasi dokumen, membuat bentuk kotak teks, mengakses kotak teks, memeriksa validitas target tautan, dan terakhir membuat tautan itu sendiri.

## Langkah 1: Menyiapkan dokumen dan membuat bentuk TextBox

 Untuk memulai, kita perlu menyiapkan dokumen dan membuat dua bentuk TextBox. Kode berikut menginisialisasi instance baru dari`Document` kelas dan membuat dua bentuk kotak teks:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Langkah 2: Membuat link antar TextBox

Sekarang kita akan membuat link antara dua TextBox menggunakan`IsValidLinkTarget()` metode dan`Next` milik TextBox pertama.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 Itu`IsValidLinkTarget()` metode memeriksa apakah TextBox kedua dapat menjadi target yang valid untuk link TextBox pertama. Jika validasi berhasil,`Next` Properti TextBox pertama diatur ke TextBox kedua, menciptakan link antara keduanya.

### Contoh kode sumber untuk ditautkan dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
## Kesimpulan

Selamat! Anda sekarang telah mempelajari cara membuat tautan antara dua kotak teks di dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Dengan menggunakan panduan langkah demi langkah ini, Anda dapat menyiapkan dokumen, membuat bentuk kotak teks, mengakses kotak teks, memeriksa validitas target tautan, dan terakhir membuat tautan itu sendiri.

### FAQ untuk membuat tautan di Word

#### T: Pustaka apa yang digunakan untuk menautkan kotak teks di Word menggunakan Aspose.Words untuk .NET?

A: Untuk menghubungkan kotak teks di Word menggunakan Aspose.Words for .NET, perpustakaan yang digunakan adalah Aspose.Words for .NET.

#### T: Bagaimana cara memeriksa apakah target tautan valid sebelum membuat tautan?

 A: Sebelum membuat tautan antar kotak teks, Anda dapat menggunakan`IsValidLinkTarget()` metode untuk memeriksa apakah target tautan valid. Metode ini memvalidasi apakah kotak teks kedua dapat menjadi target yang valid untuk link dari kotak teks pertama.

#### T: Bagaimana cara membuat tautan antara dua kotak teks?

 J: Untuk membuat tautan antara dua kotak teks, Anda perlu mengaturnya`Next` properti kotak teks pertama ke kotak teks kedua. Pastikan Anda telah memeriksa validitas target link terlebih dahulu menggunakan`IsValidLinkTarget()` metode.

#### T: Apakah mungkin membuat tautan antar elemen selain kotak teks?

J: Ya, dengan menggunakan perpustakaan Aspose.Words untuk .NET, dimungkinkan untuk membuat tautan antara berbagai elemen seperti paragraf, tabel, gambar, dll. Prosesnya akan bervariasi tergantung pada item spesifik yang ingin Anda tautkan.

#### T: Fungsi lain apa yang dapat ditambahkan ke kotak teks di Word menggunakan Aspose.Words untuk .NET?

J: Dengan Aspose.Words for .NET, Anda dapat menambahkan banyak fitur lain ke kotak teks, seperti pemformatan teks, menambahkan gambar, mengubah gaya, dll. Anda dapat menjelajahi dokumentasi Aspose.Words for .NET untuk mengetahui semua fitur tersedia.