---
title: Tentukan Font Default Saat Rendering
linktitle: Tentukan Font Default Saat Rendering
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menentukan font default saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/specify-default-font-when-rendering/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk menentukan font default saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menentukan font default yang akan digunakan saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang akan dirender
 Selanjutnya, Anda perlu memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Tetapkan font default
 Sekarang Anda dapat menentukan font default yang akan digunakan saat rendering dengan membuat sebuah instance dari`FontSettings` kelas dan pengaturan`DefaultFontName` properti dari`DefaultFontSubstitution` keberatan dengan`DefaultFontSubstitution` obyek`SubstitutionSettings` dari`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Langkah 4: Simpan dokumen yang dirender
 Terakhir, Anda dapat menyimpan dokumen yang dirender ke file menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Contoh kode sumber untuk Tentukan Font Default Saat Rendering menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Jika font default yang ditentukan di sini tidak dapat ditemukan selama rendering, maka
// font terdekat pada mesin digunakan sebagai gantinya.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menentukan font default saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengatur font default untuk digunakan saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan rendering dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara menentukan font default saat mengonversi ke PDF di Aspose.Words?

 A: Untuk menentukan font default saat mengonversi ke PDF di Aspose.Words, Anda dapat menggunakan`PdfOptions` kelas dan atur`DefaultFontName`properti ke nama font yang diinginkan.

#### Q: Bagaimana jika font default tidak tersedia saat mengkonversi ke PDF?

A: Jika font default yang ditentukan tidak tersedia saat mengonversi ke PDF, Aspose.Words akan menggunakan font pengganti untuk menampilkan teks dalam dokumen yang dikonversi. Hal ini mungkin menyebabkan sedikit perbedaan tampilan dengan font aslinya.

#### T: Dapatkah saya menentukan font default untuk format output lain, seperti DOCX atau HTML?

J: Ya, Anda dapat menentukan font default untuk format output lain seperti DOCX atau HTML dengan menggunakan opsi konversi yang sesuai dan mengatur properti yang sesuai untuk setiap format.

#### T: Bagaimana cara memeriksa font default yang ditentukan di Aspose.Words?

 A: Untuk memeriksa font default yang ditentukan di Aspose.Words, Anda dapat menggunakan`DefaultFontName` properti dari`PdfOptions` kelas dan mengambil nama font yang dikonfigurasi.

#### T: Apakah mungkin untuk menentukan font default yang berbeda untuk setiap bagian dokumen?

J: Ya, dimungkinkan untuk menentukan font default yang berbeda untuk setiap bagian dokumen menggunakan opsi pemformatan khusus untuk setiap bagian. Namun, hal ini memerlukan manipulasi dokumen yang lebih canggih menggunakan fitur Aspose.Words.