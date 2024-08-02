---
title: Sisipkan Bentuk
linktitle: Sisipkan Bentuk
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dan memanipulasi bentuk di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/programming-with-shapes/insert-shape/
---
## Perkenalan

Saat membuat dokumen Word yang menarik secara visual dan terstruktur dengan baik, bentuk dapat memainkan peran penting. Baik Anda menambahkan panah, kotak, atau bahkan bentuk khusus yang rumit, kemampuan untuk memanipulasi elemen ini secara terprogram menawarkan fleksibilitas yang tak tertandingi. Dalam tutorial ini, kita akan menjelajahi cara menyisipkan dan memanipulasi bentuk di dokumen Word menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Words untuk .NET: Unduh dan instal versi terbaru dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Lingkungan pengembangan .NET yang sesuai seperti Visual Studio.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan konsep dasar.

## Impor Namespace

Untuk memulai, Anda harus mengimpor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Langkah 1: Siapkan Proyek Anda

Sebelum Anda bisa mulai menyisipkan bentuk, Anda perlu menyiapkan proyek Anda dan menambahkan pustaka Aspose.Words untuk .NET.

1. Buat Proyek Baru: Buka Visual Studio dan buat proyek Aplikasi Konsol C# baru.
2. Tambahkan Aspose.Words untuk .NET: Instal perpustakaan Aspose.Words untuk .NET melalui NuGet Package Manager.

```bash
Install-Package Aspose.Words
```

## Langkah 2: Inisialisasi Dokumen

Pertama, Anda perlu menginisialisasi dokumen baru dan pembuat dokumen, yang akan membantu dalam menyusun dokumen.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inisialisasi dokumen baru
Document doc = new Document();

// Inisialisasi DocumentBuilder untuk membantu membuat dokumen
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan Bentuk

Sekarang, mari masukkan bentuk ke dalam dokumen. Kita akan mulai dengan menambahkan kotak teks sederhana.

```csharp
// Sisipkan bentuk kotak teks ke dalam dokumen
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Putar bentuknya
shape.Rotation = 30.0;
```

Pada contoh ini, kita menyisipkan kotak teks pada posisi (100, 100) dengan lebar dan tinggi masing-masing 50 satuan. Kami juga memutar bentuknya sebesar 30 derajat.

## Langkah 4: Tambahkan Bentuk Lain

Mari tambahkan bentuk lain ke dokumen, kali ini tanpa menentukan posisinya.

```csharp
// Tambahkan bentuk kotak teks lainnya
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Putar bentuknya
secondShape.Rotation = 30.0;
```

Cuplikan kode ini menyisipkan kotak teks lain dengan dimensi dan rotasi yang sama seperti yang pertama tetapi tanpa menentukan posisinya.

## Langkah 5: Simpan Dokumen

 Setelah menambahkan bentuk, langkah terakhir adalah menyimpan dokumen. Kami akan menggunakan`OoxmlSaveOptions` untuk menentukan format penyimpanan.

```csharp
// Tentukan opsi penyimpanan dengan kepatuhan
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Simpan dokumennya
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil menyisipkan dan memanipulasi bentuk dalam dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini membahas dasar-dasarnya, namun Aspose.Words menawarkan lebih banyak fitur lanjutan untuk bekerja dengan bentuk, seperti gaya kustom, konektor, dan bentuk grup.

 Untuk informasi lebih lengkap, kunjungi[Aspose.Words untuk dokumentasi .NET](https://reference.aspose.com/words/net/).

## FAQ

### Bagaimana cara menyisipkan berbagai jenis bentuk?
Anda dapat mengubah`ShapeType` dalam`InsertShape` metode untuk menyisipkan berbagai jenis bentuk seperti lingkaran, persegi panjang, dan panah.

### Bisakah saya menambahkan teks di dalam bentuk?
 Ya, Anda dapat menggunakan`builder.Write` metode untuk menambahkan teks di dalam bentuk setelah memasukkannya.

### Apakah mungkin untuk menata bentuknya?
 Ya, Anda dapat mengatur gaya bentuk dengan mengatur properti seperti`FillColor`, `StrokeColor` , Dan`StrokeWeight`.

### Bagaimana cara memposisikan bentuk relatif terhadap elemen lainnya?
 Menggunakan`RelativeHorizontalPosition`Dan`RelativeVerticalPosition` properti untuk memposisikan bentuk relatif terhadap elemen lain dalam dokumen.

### Bisakah saya mengelompokkan beberapa bentuk menjadi satu?
 Ya, Aspose.Words untuk .NET memungkinkan Anda mengelompokkan bentuk menggunakan`GroupShape` kelas.