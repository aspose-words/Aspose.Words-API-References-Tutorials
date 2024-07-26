---
title: Satuan ukur
linktitle: Satuan ukur
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonfigurasi fitur unit pengukuran di Aspose.Words untuk .NET untuk mempertahankan format dokumen selama konversi ODT.
type: docs
weight: 10
url: /id/net/programming-with-odtsaveoptions/measure-unit/
---
## Perkenalan

Pernahkah Anda harus mengonversi dokumen Word ke format berbeda tetapi memerlukan unit pengukuran khusus untuk tata letak Anda? Baik Anda berurusan dengan inci, sentimeter, atau titik, memastikan dokumen Anda menjaga integritasnya selama proses konversi sangatlah penting. Dalam tutorial ini, kita akan mempelajari cara mengonfigurasi fitur satuan pengukuran di Aspose.Words untuk .NET. Fitur canggih ini memastikan bahwa format dokumen Anda dipertahankan persis seperti yang Anda perlukan saat mengonversi ke format ODT (Open Document Text).

## Prasyarat

Sebelum mendalami kodenya, ada beberapa hal yang Anda perlukan untuk memulai:

1. Aspose.Words for .NET: Pastikan Anda menginstal Aspose.Words for .NET versi terbaru. Jika Anda belum memilikinya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: IDE seperti Visual Studio untuk menulis dan mengeksekusi kode C# Anda.
3. Pengetahuan Dasar C#: Memahami dasar-dasar C# akan membantu Anda mengikuti tutorial.
4. Dokumen Word: Siapkan contoh dokumen Word yang dapat Anda gunakan untuk konversi.

## Impor Namespace

Sebelum kita memulai pengkodean, pastikan kita telah mengimpor namespace yang diperlukan. Tambahkan ini menggunakan arahan di bagian atas file kode Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda berada dan tempat file yang dikonversi akan disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke direktori Anda. Ini memastikan kode Anda mengetahui di mana menemukan dokumen Word Anda.

## Langkah 2: Muat Dokumen Word

 Selanjutnya, Anda perlu memuat dokumen Word yang ingin Anda konversi. Ini dilakukan dengan menggunakan`Document` kelas dari Aspose.Words.

```csharp
// Muat dokumen Word
Document doc = new Document(dataDir + "Document.docx");
```

Pastikan dokumen Word Anda, bernama "Document.docx", ada di direktori yang ditentukan.

## Langkah 3: Konfigurasikan Satuan Pengukuran

 Sekarang, mari konfigurasikan unit pengukuran untuk konversi ODT. Ini adalah dimana keajaiban terjadi. Kami akan menyiapkannya`OdtSaveOptions` menggunakan inci sebagai satuan pengukuran.

```csharp
// Konfigurasi opsi cadangan dengan fitur "Unit pengukuran".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 Dalam contoh ini, kami menyetel satuan pengukuran ke inci. Anda juga dapat memilih unit lain seperti`OdtSaveMeasureUnit.Centimeters` atau`OdtSaveMeasureUnit.Points` tergantung pada kebutuhan Anda.

## Langkah 4: Konversikan Dokumen ke ODT

 Terakhir, kami akan mengonversi dokumen Word ke format ODT menggunakan konfigurasi`OdtSaveOptions`.

```csharp
// Ubah dokumen menjadi ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Baris kode ini menyimpan dokumen yang dikonversi di direktori tertentu dengan unit pengukuran baru yang diterapkan.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengonfigurasi fitur unit pengukuran di Aspose.Words untuk .NET untuk memastikan tata letak dokumen Anda dipertahankan selama konversi. Baik Anda bekerja dengan inci, sentimeter, atau titik, tutorial ini telah menunjukkan kepada Anda cara mengontrol pemformatan dokumen Anda dengan mudah.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang kuat untuk bekerja dengan dokumen Word secara terprogram. Hal ini memungkinkan pengembang untuk membuat, memodifikasi, mengkonversi, dan memproses dokumen Word tanpa memerlukan Microsoft Word.

### Bisakah saya menggunakan satuan pengukuran lain selain inci?
 Ya, Aspose.Words untuk .NET mendukung satuan pengukuran lain seperti sentimeter dan titik. Anda dapat menentukan unit yang diinginkan menggunakan`OdtSaveMeasureUnit` pencacahan.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis Aspose.Words untuk .NET dari[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi Aspose.Words untuk .NET?
 Anda dapat mengakses dokumentasi komprehensif untuk Aspose.Words untuk .NET di[Link ini](https://reference.aspose.com/words/net/).

### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Words untuk .NET?
 Untuk dukungan, Anda dapat mengunjungi forum Aspose.Words di[Link ini](https://forum.aspose.com/c/words/8).
