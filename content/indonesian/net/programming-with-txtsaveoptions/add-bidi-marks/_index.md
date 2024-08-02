---
title: Tambahkan Tanda Bidi di Dokumen Word
linktitle: Tambahkan Tanda Bidi di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan tanda dua arah (Bidi) di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan ini. Pastikan arah teks yang tepat untuk konten multi-bahasa.
type: docs
weight: 10
url: /id/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Perkenalan

Dalam dunia pemrosesan dokumen, teks dua arah (Bidi) seringkali agak rumit untuk dikelola. Hal ini terutama berlaku ketika berhadapan dengan bahasa yang memiliki arah teks berbeda, seperti bahasa Arab atau Ibrani. Untungnya, Aspose.Words untuk .NET memudahkan penanganan skenario seperti itu. Dalam tutorial ini, kita akan mempelajari cara menambahkan tanda Bidi ke dokumen Word menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Anda dapat mengunduhnya dari[Asumsikan halaman Unduhan](https://releases.aspose.com/words/net/).
2. .NET Framework atau .NET Core: Pastikan Anda memiliki lingkungan .NET yang kompatibel untuk menjalankan contoh.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan pengoperasian dasar di .NET.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan. Inilah cara Anda dapat memasukkannya ke dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Mari kita uraikan proses penambahan tanda Bidi di dokumen Word menjadi langkah-langkah yang jelas. Setiap langkah akan memandu Anda memahami kode dan tujuannya.

## Langkah 1: Siapkan Dokumen Anda

 Mulailah dengan membuat instance baru dari`Document` kelas dan a`DocumentBuilder` untuk menambahkan konten ke dokumen.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan tambahkan konten
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Pada langkah ini, Anda menginisialisasi dokumen Word baru dan menyiapkan a`DocumentBuilder` untuk memfasilitasi penyisipan konten.

## Langkah 2: Tambahkan Konten ke Dokumen Anda

Selanjutnya, tambahkan beberapa teks ke dokumen Anda. Di sini, kami akan menambahkan teks dalam berbagai bahasa untuk mengilustrasikan penanganan teks Bidi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Di sini, pertama-tama kami menambahkan frasa bahasa Inggris standar. Kemudian, kami mengaktifkan pemformatan teks Bidi untuk teks berikutnya, yang ditulis dalam bahasa Ibrani dan Arab. Ini menunjukkan bagaimana menggabungkan teks dua arah.

## Langkah 3: Konfigurasikan Opsi Penyimpanan untuk Tanda Bidi

 Untuk memastikan bahwa tanda Bidi disimpan dengan benar dalam dokumen, Anda perlu mengkonfigurasi`TxtSaveOptions` dan aktifkan`AddBidiMarks` pilihan.

```csharp
// Tambahkan tanda Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 Pada langkah ini, kita membuat sebuah instance dari`TxtSaveOptions` dan atur`AddBidiMarks`properti ke`true`. Hal ini memastikan bahwa tanda Bidi disertakan saat menyimpan dokumen sebagai file teks.

## Kesimpulan

Menambahkan tanda Bidi ke dokumen Word Anda bisa menjadi langkah penting ketika berhadapan dengan konten multibahasa yang mencakup bahasa dengan arah teks berbeda. Dengan Aspose.Words untuk .NET, proses ini mudah dan efisien. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memastikan bahwa dokumen Anda mewakili teks Bidi dengan benar, sehingga meningkatkan keterbacaan dan akurasi.

## FAQ

### Apa itu tanda Bidi dan mengapa itu penting?
Tanda Bidi adalah karakter khusus yang digunakan untuk mengontrol arah teks dalam dokumen. Mereka penting untuk menampilkan bahasa yang dibaca dari kanan ke kiri dengan benar, seperti Arab dan Ibrani.

### Bisakah saya menggunakan Aspose.Words untuk .NET untuk menangani jenis masalah arah teks lainnya?
Ya, Aspose.Words untuk .NET menyediakan dukungan komprehensif untuk berbagai kebutuhan arah dan pemformatan teks, termasuk bahasa kanan ke kiri dan kiri ke kanan.

### Apakah mungkin menerapkan pemformatan Bidi hanya pada bagian tertentu dari dokumen?
Ya, Anda dapat menerapkan pemformatan Bidi ke paragraf atau bagian tertentu dari dokumen Anda sesuai kebutuhan.

### Dalam format apa saya dapat menyimpan dokumen dengan tanda Bidi?
Dalam contoh yang diberikan, dokumen disimpan sebagai file teks. Namun, Aspose.Words juga mendukung penyimpanan dokumen dalam berbagai format dengan tetap mempertahankan tanda Bidi.

### Di mana saya dapat menemukan informasi selengkapnya tentang Aspose.Words untuk .NET?
 Anda dapat menjelajahi lebih lanjut tentang Aspose.Words untuk .NET melalui[Asumsikan Dokumentasi](https://reference.aspose.com/words/net/) dan mengakses[Forum Dukungan](https://forum.aspose.com/c/words/8) untuk bantuan tambahan.