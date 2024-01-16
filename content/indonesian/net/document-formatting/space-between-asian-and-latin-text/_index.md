---
title: Spasi Antara Teks Asia dan Latin Dalam Dokumen Word
linktitle: Spasi Antara Teks Asia dan Latin Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyesuaikan spasi antara teks Asia dan Latin secara otomatis di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-formatting/space-between-asian-and-latin-text/
---
Dalam tutorial ini, kami akan menunjukkan cara menggunakan fitur Spasi antara teks Asia dan Latin di fitur dokumen Word dengan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan.

## Langkah 1: Membuat dan mengonfigurasi dokumen

Untuk memulai, buat dokumen baru dan objek DocumentBuilder terkait. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Menyiapkan spasi antara teks Asia dan Latin

Sekarang kita akan mengonfigurasi spasi antara teks Asia dan Latin menggunakan properti objek ParagraphFormat. Begini caranya:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Langkah 3: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Contoh kode sumber Spasi Antara Teks Asia dan Latin menggunakan Aspose.Words untuk .NET

Berikut source code lengkap fitur Space Between Asian and Latin Text dengan Aspose.Words for .NET:


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Dengan kode ini Anda akan dapat secara otomatis menyesuaikan spasi antara teks Asia dan Latin di dokumen Anda menggunakan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi proses penggunaan fitur Spasi untuk menyesuaikan spasi antara teks Asia dan Latin dalam dokumen Word dengan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat memastikan spasi dan kesejajaran yang tepat, terutama berguna ketika menangani konten campuran Asia dan Latin.

### FAQ

#### Q: Apa yang dimaksud dengan fitur Spasi antara teks Asia dan Latin di dokumen Word?

J: Fitur Spasi antara teks Asia dan Latin dalam dokumen Word mengacu pada kemampuan untuk secara otomatis menyesuaikan spasi antara teks yang ditulis dalam skrip berbeda, seperti Asia (misalnya, Cina, Jepang) dan Latin (misalnya, Inggris).

#### Q: Mengapa penyesuaian spasi antara teks Asia dan Latin penting?

J: Menyesuaikan jarak antara teks Asia dan Latin sangat penting untuk memastikan bahwa skrip yang berbeda berpadu secara harmonis dalam dokumen. Spasi yang tepat meningkatkan keterbacaan dan tampilan visual secara keseluruhan, mencegah teks tampak terlalu sempit atau menyebar.

#### T: Dapatkah saya menyesuaikan penyesuaian ruang antar skrip yang berbeda?

 J: Ya, Anda dapat menyesuaikan penyesuaian ruang antar skrip yang berbeda menggunakan`AddSpaceBetweenFarEastAndAlpha` Dan`AddSpaceBetweenFarEastAndDigit` properti. Dengan mengaktifkan atau menonaktifkan properti ini, Anda dapat mengontrol spasi antara teks Asia dan Latin, serta antara teks dan angka Asia.

#### T: Apakah Aspose.Words untuk .NET mendukung fitur pemformatan dokumen lainnya?

J: Ya, Aspose.Words untuk .NET menawarkan dukungan ekstensif untuk berbagai fitur pemformatan dokumen. Ini mencakup fungsionalitas untuk gaya font, paragraf, tabel, gambar, dan banyak lagi. Anda dapat secara efektif memanipulasi dan memformat dokumen Word Anda secara terprogram.

#### T: Di mana saya dapat menemukan sumber daya dan dokumentasi tambahan untuk Aspose.Words untuk .NET?

 J: Untuk sumber daya dan dokumentasi komprehensif tentang penggunaan Aspose.Words untuk .NET, kunjungi[Referensi API Aspose.Words](https://reference.aspose.com/words/net/). Di sana, Anda akan menemukan panduan mendetail, tutorial, contoh kode, dan referensi API untuk membantu Anda memanfaatkan fitur canggih Aspose.Words untuk .NET secara efektif.