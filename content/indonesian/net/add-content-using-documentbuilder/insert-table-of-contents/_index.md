---
title: Sisipkan Daftar Isi Dalam Dokumen Word
linktitle: Sisipkan Daftar Isi Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan Daftar Isi di Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk navigasi dokumen yang lancar.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## Perkenalan
Dalam tutorial ini, Anda akan mempelajari cara menambahkan Daftar Isi (TOC) secara efisien ke dokumen Word Anda menggunakan Aspose.Words untuk .NET. Fitur ini penting untuk mengatur dan menavigasi dokumen yang panjang, meningkatkan keterbacaan, dan memberikan gambaran singkat tentang bagian-bagian dokumen.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pemahaman dasar tentang kerangka C# dan .NET.
- Visual Studio diinstal pada mesin Anda.
-  Aspose.Words untuk perpustakaan .NET. Jika Anda belum menginstalnya, Anda dapat mendownloadnya dari[Di Sini](https://releases.aspose.com/words/net/).

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang jelas:

## Langkah 1: Inisialisasi Dokumen Aspose.Words dan DocumentBuilder

 Pertama, inisialisasi Aspose.Words baru`Document` objek dan a`DocumentBuilder` bekerja dengan:

```csharp
// Inisialisasi Dokumen dan DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Masukkan Daftar Isi

 Sekarang, masukkan Daftar Isi menggunakan`InsertTableOfContents` metode:

```csharp
// Sisipkan Daftar Isi
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Langkah 3: Mulai Konten Dokumen di Halaman Baru

Untuk memastikan pemformatan yang tepat, mulai konten dokumen sebenarnya di halaman baru:

```csharp
// Sisipkan hentian halaman
builder.InsertBreak(BreakType.PageBreak);
```

## Langkah 4: Susun Dokumen Anda dengan Judul

Atur konten dokumen Anda menggunakan gaya judul yang sesuai:

```csharp
// Tetapkan gaya judul
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Langkah 5: Perbarui dan Isi Daftar Isi

Perbarui Daftar Isi untuk mencerminkan struktur dokumen:

```csharp
// Perbarui bidang Daftar Isi
doc.UpdateFields();
```

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen Anda ke direktori tertentu:

```csharp
// Simpan dokumennya
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## Kesimpulan

Menambahkan Daftar Isi menggunakan Aspose.Words untuk .NET sangatlah mudah dan meningkatkan kegunaan dokumen Anda secara signifikan. Dengan mengikuti langkah-langkah ini, Anda dapat mengatur dan menavigasi dokumen yang kompleks secara efisien.

## FAQ

### Bisakah saya menyesuaikan tampilan Daftar Isi?
Ya, Anda dapat menyesuaikan tampilan dan perilaku Daftar Isi menggunakan Aspose.Words untuk .NET API.

### Apakah Aspose.Words mendukung pembaruan bidang secara otomatis?
Ya, Aspose.Words memungkinkan Anda memperbarui bidang seperti Daftar Isi secara dinamis berdasarkan perubahan dokumen.

### Bisakah saya membuat beberapa Daftar Isi dalam satu dokumen?
Aspose.Words mendukung pembuatan beberapa Daftar Isi dengan pengaturan berbeda dalam satu dokumen.

### Apakah Aspose.Words kompatibel dengan versi Microsoft Word yang berbeda?
Ya, Aspose.Words memastikan kompatibilitas dengan berbagai versi format Microsoft Word.

### Di mana saya dapat menemukan lebih banyak bantuan dan dukungan untuk Aspose.Words?
Untuk bantuan lebih lanjut, kunjungi[Aspose.Forum Kata-kata](https://forum.aspose.com/c/words/8) atau periksa[dokumentasi resmi](https://reference.aspose.com/words/net/).