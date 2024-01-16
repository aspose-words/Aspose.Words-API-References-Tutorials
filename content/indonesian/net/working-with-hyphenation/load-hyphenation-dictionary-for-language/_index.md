---
title: Muat Kamus Tanda Hubung Untuk Bahasa
linktitle: Muat Kamus Tanda Hubung Untuk Bahasa
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memuat kamus tanda hubung untuk bahasa tertentu di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Dalam tutorial langkah demi langkah ini, kami akan menunjukkan cara memuat kamus tanda hubung untuk bahasa tertentu ke Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Memuat dokumen

Pertama, muat dokumen Anda dari direktori yang ditentukan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Langkah 2: Memuat kamus tanda hubung

Selanjutnya, buka aliran ke file kamus tanda hubung dan simpan untuk bahasa yang diinginkan. Dalam contoh ini, kami memuat kamus untuk bahasa Jerman Swiss (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Pastikan Anda memiliki file kamus yang sesuai di direktori data Anda.

## Langkah 3: Simpan dokumen yang dimodifikasi

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Jadi ! Anda telah berhasil memuat kamus tanda hubung untuk bahasa tertentu di Aspose.Words untuk .NET.

### Contoh kode sumber untuk kamus tanda hubung yang memuat suatu bahasa menggunakan Aspose.Words untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya agar sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara memuat kamus suku kata untuk bahasa tertentu di Aspose.Words?

 A: Untuk memuat kamus suku kata untuk bahasa tertentu di Aspose.Words, Anda dapat menggunakan`Hyphenation` kelas dan`LoadDictionary()` metode. Buat sebuah instance dari`Hyphenation` kelas dan menelepon`LoadDictionary()` metode yang menentukan jalur ke file kamus suku kata untuk bahasa yang diinginkan. Ini akan memuat kamus suku kata ke Aspose.Words.

#### T: Di mana saya dapat menemukan file kamus suku kata untuk berbagai bahasa?

J: Anda dapat menemukan file kamus suku kata untuk berbagai bahasa di berbagai sumber online. File-file ini biasanya dalam format XML atau TEX. Anda dapat menemukan kamus silabisasi sumber terbuka untuk berbagai bahasa di situs web yang didedikasikan untuk proyek linguistik atau repositori kode sumber.

#### T: Bagaimana cara menerapkan kamus suku kata yang dimuat ke dokumen di Aspose.Words?

 J: Untuk menerapkan kamus suku kata yang dimuat ke dokumen di Aspose.Words, Anda perlu mengulangi kata-kata dalam dokumen dan menggunakan`Hyphenate()` metode`Hyphenation`kelas untuk mendapatkan suku kata dari kata-kata tersebut. Anda kemudian dapat memformat kata-kata yang diberi suku kata sesuai kebutuhan, misalnya dengan menambahkan tanda hubung di antara suku kata.

#### T: Bahasa apa saja yang didukung untuk penyusunan suku kata di Aspose.Words?

J: Aspose.Words mendukung silabisasi untuk berbagai bahasa termasuk Inggris, Prancis, Spanyol, Jerman, Italia, Belanda, Rusia, Portugis, Swedia, Norwegia, Denmark, Finlandia, Polandia, Ceko, dan banyak lagi. Periksa dokumentasi Aspose.Words untuk daftar lengkap bahasa yang didukung untuk silabisasi.