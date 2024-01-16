---
title: Kata-kata Bahasa Dengan Tanda Hubung
linktitle: Kata-kata Bahasa Dengan Tanda Hubung
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memberi tanda hubung pada kata dalam berbagai bahasa di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara memberi tanda hubung pada kata-kata dalam berbagai bahasa di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari situs resminya.

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document` objek dengan menentukan jalur ke dokumen sumber Anda yang berisi teks dalam berbagai bahasa:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Langkah 2: Menyimpan Kamus Tanda Hubung

Selanjutnya, simpan kamus tanda hubung untuk berbagai bahasa yang ingin Anda proses. Dalam contoh ini, kami mendaftarkan kamus untuk Bahasa Inggris Amerika dan Bahasa Jerman Swiss:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Pastikan Anda memiliki file kamus yang sesuai di direktori data Anda.

## Langkah 3: Memproses kata dengan tanda hubung

 Sekarang Anda dapat menggunakan fitur tanda hubung untuk memproses kata dalam berbagai bahasa. Anda dapat menggunakan metode yang berbeda`Document` atau`DocumentBuilder` tergantung pada kebutuhan spesifik Anda.

```csharp
// Contoh: Menggunakan metode Hyphenate dari DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Langkah 4: Simpan dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Jadi ! Anda telah berhasil memproses kata dengan memberi tanda hubung dalam bahasa berbeda di dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk tanda hubung kata menggunakan Aspose.Words untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya agar sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara menyusun suku kata sebuah kata dalam bahasa tertentu dengan Aspose.Words?

 A: Untuk menyusun suku kata sebuah kata dalam bahasa tertentu dengan Aspose.Words, Anda dapat menggunakan`Hyphenation` kelas dan`Hyphenate()` metode. Buat sebuah instance dari`Hyphenation` kelas menentukan bahasa yang diinginkan, lalu memanggil`Hyphenate()`metode meneruskan kata ke suku kata sebagai argumen. Ini akan memberi Anda suku kata dari kata tersebut dalam bahasa yang ditentukan.

#### T: Kode bahasa apa yang harus saya gunakan untuk menentukan bahasa silabisasi di Aspose.Words?

A: Untuk menentukan suku kata bahasa di Aspose.Words, Anda harus menggunakan kode bahasa yang sesuai. Misalnya, Anda dapat menggunakan "en" untuk bahasa Inggris, "fr" untuk bahasa Prancis, "es" untuk bahasa Spanyol, "de" untuk bahasa Jerman, dll. Lihat dokumentasi Aspose.Words untuk daftar lengkap kode bahasa yang didukung.

#### T: Apakah silabisasi berfungsi untuk semua bahasa di Aspose.Words?

J: Pembuatan suku kata di Aspose.Words bergantung pada aturan suku kata khusus bahasa. Meskipun Aspose.Words mendukung berbagai bahasa, beberapa bahasa mungkin tidak didukung atau silabisasi mungkin tidak tersedia untuk bahasa tersebut. Periksa dokumentasi Aspose.Words untuk mengetahui bahasa mana yang didukung untuk penyusunan suku kata.