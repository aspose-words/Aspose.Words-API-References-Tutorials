---
title: Sisipkan Bidang Gabungan Menggunakan DOM
linktitle: Sisipkan Bidang Gabungan Menggunakan DOM
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dan mengonfigurasi bidang gabungan di dokumen Word menggunakan Aspose.Words untuk .NET dengan tutorial langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-merge-field-using-dom/
---
## Perkenalan

Jika Anda bekerja dengan pemrosesan dokumen di .NET, Anda mungkin menemukan Aspose.Words. Pustaka canggih ini menawarkan beragam fitur untuk memanipulasi dokumen Word secara terprogram. Dalam tutorial ini, kita akan fokus pada satu fitur spesifik: menyisipkan bidang gabungan menggunakan Model Objek Dokumen (DOM) di Aspose.Words untuk .NET. Panduan ini akan memandu Anda melalui setiap langkah, mulai dari menyiapkan lingkungan hingga menyisipkan dan memperbarui bidang gabungan di dokumen Word.

## Prasyarat

Sebelum mendalami kodenya, pastikan Anda memiliki semua yang diperlukan untuk mengikuti tutorial ini.

1. Pengetahuan Dasar C#: Anda harus terbiasa dengan pemrograman C#.
2. Visual Studio Terinstal: Pastikan Anda memiliki Visual Studio atau C# IDE lainnya yang terinstal di mesin Anda.
3.  Aspose.Words for .NET: Unduh dan instal versi terbaru Aspose.Words for .NET dari[Rilis](https://releases.aspose.com/words/net/).
4.  Lisensi yang Valid: Jika Anda tidak memiliki lisensi, Anda bisa mendapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk evaluasi.

## Langkah 1: Siapkan Proyek Anda

Hal pertama yang pertama, mari kita siapkan proyek baru di Visual Studio.

1. Buka Visual Studio.
2. Buat Proyek Baru: Buka File > Baru > Proyek. Pilih Aplikasi Konsol C#.
3. Beri Nama Proyek Anda: Berikan nama yang bermakna pada proyek Anda dan klik Buat.

## Langkah 2: Instal Aspose.Words

Untuk menggunakan Aspose.Words, Anda perlu menambahkannya ke proyek Anda. Ini dapat dilakukan melalui Manajer Paket NuGet.

1. Buka NuGet Package Manager: Klik kanan proyek Anda di Solution Explorer, lalu pilih Manage NuGet Packages.
2. Cari Aspose.Words: Di NuGet Package Manager, cari "Aspose.Words".
3. Instal Paket: Klik Instal untuk menambahkan Aspose.Words ke proyek Anda.

## Langkah 3: Impor Namespace

Untuk mulai menggunakan Aspose.Words, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Inilah cara Anda melakukannya:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Langkah 4: Inisialisasi Dokumen Anda

Sekarang semuanya sudah diatur, mari buat dokumen Word baru dan inisialisasi DocumentBuilder.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 5: Pindahkan Kursor ke Paragraf Tertentu

Selanjutnya, kita perlu memindahkan kursor ke paragraf tertentu di dokumen tempat kita ingin menyisipkan bidang gabungan.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## Langkah 6: Masukkan Bidang Gabungan

 Memasukkan bidang gabungan sangatlah mudah. Kami akan menggunakan`InsertField` metode`DocumentBuilder` kelas.

```csharp
// Sisipkan bidang gabungan bidang.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Langkah 7: Konfigurasikan Bidang Penggabungan

Setelah memasukkan bidang gabungan, Anda dapat mengatur berbagai properti untuk mengonfigurasinya sesuai kebutuhan Anda.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Langkah 8: Perbarui dan Simpan Dokumen

Terakhir, perbarui bidang untuk memastikan semua pengaturan diterapkan dan simpan dokumen.

```csharp
// Perbarui bidangnya.
field.Update();

// Simpan dokumennya.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menyisipkan dan mengonfigurasi bidang gabungan dalam dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini mencakup langkah-langkah penting mulai dari menyiapkan lingkungan Anda hingga menyimpan dokumen akhir. Dengan Aspose.Words, Anda dapat mengotomatiskan tugas pemrosesan dokumen yang kompleks, menjadikan aplikasi .NET Anda lebih kuat dan efisien.

## FAQ

###  Apa itu bidang gabungan?
Bidang gabungan adalah tempat penampung dalam dokumen yang bisa diganti secara dinamis dengan data dari sumber data, seperti database atau file CSV.

###  Bisakah saya menggunakan Aspose.Words secara gratis?
 Aspose.Words menawarkan uji coba gratis yang dapat Anda unduh[Di Sini](https://releases.aspose.com/). Untuk penggunaan jangka panjang, Anda perlu membeli lisensi.

###  Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words?
 Anda dapat memperoleh lisensi sementara dari situs Aspose[Di Sini](https://purchase.aspose.com/temporary-license/).

### Versi .NET apa yang didukung oleh Aspose.Words?
Aspose.Words mendukung beberapa versi .NET, termasuk .NET Framework, .NET Core, dan .NET Standard.

###  Di mana saya dapat menemukan dokumentasi API untuk Aspose.Words?
 Dokumentasi API tersedia[Di Sini](https://reference.aspose.com/words/net/).