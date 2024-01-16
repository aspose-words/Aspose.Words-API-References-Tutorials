---
title: Aktifkan Nonaktifkan Substitusi Font
linktitle: Aktifkan Nonaktifkan Substitusi Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mengaktifkan atau menonaktifkan substitusi font di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/enable-disable-font-substitution/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara mengaktifkan atau menonaktifkan substitusi font di dokumen Word saat merendernya menggunakan pustaka Aspose.Words untuk .NET. Mengaktifkan atau menonaktifkan substitusi font memungkinkan Anda mengontrol apakah font yang hilang secara otomatis diganti dengan font default. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda
- Dokumen Word yang ingin Anda render dengan atau tanpa substitusi font

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Unggah dokumen dan konfigurasikan pengaturan font
 Selanjutnya, kita akan memuat dokumen Word yang ingin Anda render dan membuat sebuah instance darinya`FontSettings` kelas untuk menangani pengaturan font. Kami akan mengatur penggantian font default dengan menentukan nama font di dalamnya`DefaultFontName` dan nonaktifkan penggantian informasi font dengan`Enabled` mulai`false`.

```csharp
// Muat dokumen
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurasikan pengaturan font
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Terapkan pengaturan font ke dokumen
doc.FontSettings = fontSettings;
```

## Langkah 3: Simpan dokumen yang dirender
Terakhir, kita akan menyimpan dokumen yang dirender, yang akan mengikuti pengaturan penggantian font yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Contoh kode sumber untuk Aktifkan Nonaktifkan Substitusi Font menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mengaktifkan atau menonaktifkan substitusi font di dokumen Word saat merendernya dengan Aspose.Words untuk .NET. Dengan mengontrol substitusi font, Anda dapat memengaruhi cara penanganan font yang hilang dalam dokumen yang dirender. Jangan ragu untuk menggunakan fitur ini untuk menyesuaikan pengelolaan font di dokumen Word Anda.

### FAQ

#### T: Bagaimana cara mengaktifkan substitusi font di dokumen Word dengan Aspose.Words?

J: Untuk mengaktifkan substitusi font di dokumen Word dengan Aspose.Words, Anda dapat menggunakan API untuk menentukan font substitusi yang akan digunakan ketika font yang diperlukan tidak tersedia. Ini akan memastikan visualisasi teks yang konsisten, bahkan tanpa font aslinya.

#### T: Apakah mungkin untuk menonaktifkan substitusi font di dokumen Word dengan Aspose.Words?

J: Ya, dengan Aspose.Words Anda dapat menonaktifkan substitusi font di dokumen Word. Dengan menggunakan API, Anda dapat mencegah Word mengganti font yang diperlukan dengan font lain, sehingga mempertahankan tampilan asli teks.

#### T: Apa yang terjadi jika font yang diperlukan hilang saat substitusi di dokumen Word?

J: Ketika font yang diperlukan hilang selama penggantian di dokumen Word, Aspose.Words dapat mendeteksi masalah ini dan memberi Anda opsi untuk memperbaikinya. Anda dapat memilih untuk mengganti font yang hilang dengan font alternatif atau menyertakan font yang hilang dalam dokumen, memastikan tampilan yang benar.

#### T: Bagaimana cara menangani font yang hilang saat mengganti dokumen Word dengan Aspose.Words?

J: Untuk menangani font yang hilang saat mengganti dokumen Word dengan Aspose.Words, Anda dapat menggunakan API untuk mendeteksi font yang hilang dan memberikan opsi resolusi. Anda dapat memilih untuk mengganti font yang hilang dengan font alternatif atau menyertakan font yang hilang dalam dokumen, tergantung kebutuhan Anda.

#### T: Apakah penting mengontrol substitusi font di dokumen Word?

J: Ya, penting untuk mengontrol substitusi font di dokumen Word untuk menjaga integritas visual teks. Dengan menggunakan Aspose.Words untuk mengaktifkan atau menonaktifkan substitusi font, Anda dapat memastikan bahwa font yang diperlukan digunakan dan menghindari masalah dengan font yang hilang atau diganti.