---
title: Setel Instans Default Folder Font
linktitle: Setel Instans Default Folder Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur folder font default saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-default-instance/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur folder font default saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mengatur folder font default untuk digunakan saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Tetapkan folder font default
 Kemudian Anda dapat mengatur folder font default menggunakan`FontSettings.DefaultInstance` kelas dan`SetFontsFolder()`metode. Tentukan jalur ke folder font yang ingin Anda gunakan sebagai folder default.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Langkah 3: Muat dokumen yang akan dirender
 Sekarang Anda dapat memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 4: Simpan dokumen yang dirender
 Terakhir, Anda dapat menyimpan dokumen yang dirender ke file menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Contoh kode sumber untuk Mengatur Instans Default Folder Font menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur folder font default saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menentukan folder font mana yang akan digunakan sebagai folder default saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan sumber font yang digunakan saat merender dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mengatur folder font default di Aspose.Words?

 A: Untuk mengatur folder font default di Aspose.Words, Anda harus menggunakan`Fonts` kelas dan`SetFontsFolders` metode untuk menentukan lokasi folder font khusus.

#### T: Apakah pengaturan folder font default memengaruhi semua dokumen Word yang diproses dengan Aspose.Words?

J: Ya, pengaturan folder font default mempengaruhi semua dokumen Word yang diproses dengan Aspose.Words. Setelah Anda mengatur folder font default, Aspose.Words akan menggunakan lokasi ini untuk mencari font di semua dokumen.

#### T: Bisakah saya mengatur beberapa folder font default di Aspose.Words?

 A: Ya, Anda dapat mengatur beberapa folder font default di Aspose.Words. Anda hanya perlu menentukan lokasi folder font khusus menggunakan`SetFontsFolders` metode`Fonts` kelas.

#### T: Bagaimana cara memeriksa folder font default yang saat ini diatur di Aspose.Words?

 J: Untuk memeriksa folder font default yang saat ini ditentukan di Aspose.Words, Anda dapat menggunakan`GetFolders` metode`Fonts` kelas untuk mendapatkan lokasi folder font yang dikonfigurasi.

#### T: Apakah pengaturan folder font default memungkinkan saya menggunakan font khusus di dokumen Word saya?

J: Ya, dengan mengatur folder font default, Anda dapat menggunakan font khusus di dokumen Word Anda. Anda hanya perlu menempatkan font di folder yang ditentukan dan Aspose.Words akan menggunakannya saat membuat atau memanipulasi dokumen.