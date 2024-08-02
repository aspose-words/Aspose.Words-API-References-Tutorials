---
title: Tambahkan Bentuk Grup
linktitle: Tambahkan Bentuk Grup
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan bentuk grup ke dokumen Word menggunakan Aspose.Words untuk .NET dengan tutorial langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/programming-with-shapes/add-group-shape/
---
## Perkenalan

Membuat dokumen kompleks dengan elemen visual yang kaya terkadang bisa menjadi tugas yang menakutkan, terutama ketika berhadapan dengan bentuk grup. Tapi jangan takut! Aspose.Words untuk .NET menyederhanakan proses ini, menjadikannya sangat mudah. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menambahkan bentuk grup ke dokumen Word Anda. Siap untuk terjun? Mari kita mulai!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Anda dapat mengunduhnya dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE lain yang kompatibel dengan .NET.
3. Pemahaman Dasar C#: Keakraban dengan pemrograman C# merupakan nilai tambah.

## Impor Namespace

Untuk memulai, kita perlu mengimpor namespace yang diperlukan dalam proyek kita. Namespace ini menyediakan akses ke kelas dan metode yang diperlukan untuk memanipulasi dokumen Word dengan Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Langkah 1: Inisialisasi Dokumen

Hal pertama yang pertama, mari kita inisialisasi dokumen Word baru. Bayangkan ini seperti membuat kanvas kosong dimana kita akan menambahkan bentuk grup kita.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Di Sini,`EnsureMinimum()` menambahkan satu set node minimal yang diperlukan untuk dokumen.

## Langkah 2: Buat Objek GroupShape

 Selanjutnya, kita perlu membuat a`GroupShape`obyek. Objek ini akan berfungsi sebagai wadah untuk bentuk lainnya, sehingga memungkinkan kita mengelompokkannya menjadi satu.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Langkah 3: Tambahkan Bentuk ke GroupShape

 Sekarang, mari tambahkan bentuk individual ke bentuk kita`GroupShape` wadah. Kita akan mulai dengan bentuk batas aksen dan kemudian menambahkan bentuk tombol tindakan.

### Menambahkan Bentuk Batas Aksen

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Cuplikan kode ini membuat bentuk batas aksen dengan lebar dan tinggi 100 satuan dan menambahkannya ke`GroupShape`.

### Menambahkan Bentuk Tombol Tindakan

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Di sini, kita membuat bentuk tombol tindakan, memposisikannya, dan menambahkannya ke bentuk tombol tindakan`GroupShape`.

## Langkah 4: Tentukan Dimensi GroupShape

 Untuk memastikan bentuk kita cocok dengan kelompoknya, kita perlu mengatur dimensinya`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Ini mendefinisikan lebar dan tinggi`GroupShape` sebagai 200 unit dan mengatur ukuran koordinat yang sesuai.

## Langkah 5: Masukkan GroupShape ke dalam Dokumen

 Sekarang, mari masukkan milik kita`GroupShape` ke dalam dokumen menggunakan`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` menyediakan cara mudah untuk menambahkan node, termasuk bentuk, ke dokumen.

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang Anda tentukan.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Dan itu dia! Dokumen Anda dengan bentuk grup sudah siap.

## Kesimpulan

Menambahkan bentuk grup ke dokumen Word Anda tidak harus menjadi proses yang rumit. Dengan Aspose.Words untuk .NET, Anda dapat membuat dan memanipulasi bentuk dengan mudah, menjadikan dokumen Anda lebih menarik secara visual dan fungsional. Ikuti langkah-langkah yang diuraikan dalam tutorial ini, dan Anda akan menjadi profesional dalam waktu singkat!

## FAQ

### Bisakah saya menambahkan lebih dari dua bentuk ke GroupShape?
 Ya, Anda dapat menambahkan bentuk sebanyak yang Anda perlukan ke a`GroupShape` . Gunakan saja`AppendChild` metode untuk setiap bentuk.

### Apakah mungkin untuk menata bentuk dalam GroupShape?
 Sangat! Setiap bentuk dapat ditata secara individual menggunakan properti yang tersedia di`Shape` kelas.

### Bagaimana cara memposisikan GroupShape di dalam dokumen?
 Anda dapat memposisikannya`GroupShape` dengan mengaturnya`Left`Dan`Top` properti.

### Bisakah saya menambahkan teks ke bentuk di dalam GroupShape?
 Ya, Anda dapat menambahkan teks ke bentuk menggunakan`AppendChild` metode untuk menambahkan a`Paragraph` mengandung`Run` node dengan teks.

### Apakah mungkin mengelompokkan bentuk secara dinamis berdasarkan masukan pengguna?
Ya, Anda dapat secara dinamis membuat dan mengelompokkan bentuk berdasarkan masukan pengguna dengan menyesuaikan properti dan metode.