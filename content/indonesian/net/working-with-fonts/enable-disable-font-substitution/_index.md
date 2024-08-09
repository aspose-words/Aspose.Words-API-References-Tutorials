---
title: Aktifkan Nonaktifkan Substitusi Font
linktitle: Aktifkan Nonaktifkan Substitusi Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengaktifkan atau menonaktifkan substitusi font di dokumen Word menggunakan Aspose.Words untuk .NET. Pastikan dokumen Anda terlihat konsisten di semua platform.
type: docs
weight: 10
url: /id/net/working-with-fonts/enable-disable-font-substitution/
---
## Perkenalan

Pernahkah Anda menemukan diri Anda dalam situasi di mana font yang Anda pilih dengan cermat di dokumen Word diganti saat dilihat di komputer lain? Mengganggu, bukan? Hal ini terjadi karena substitusi font, suatu proses dimana sistem mengganti font yang hilang dengan font yang tersedia. Tapi jangan khawatir! Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengelola dan mengontrol substitusi font. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengaktifkan atau menonaktifkan substitusi font di dokumen Word Anda, memastikan dokumen Anda selalu terlihat sesuai keinginan Anda.

## Prasyarat

Sebelum mendalami langkah-langkahnya, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words untuk .NET: Unduh versi terbaru[Di Sini](https://releases.aspose.com/words/net/).
- Visual Studio: Versi apa pun yang mendukung .NET.
- Pengetahuan dasar C#: Ini akan membantu Anda mengikuti contoh pengkodean.

## Impor Namespace

Untuk memulai, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda. Tambahkan ini di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dilakukan.

## Langkah 1: Siapkan Proyek Anda

Pertama, siapkan proyek baru di Visual Studio dan tambahkan referensi ke perpustakaan Aspose.Words untuk .NET. Jika Anda belum melakukannya, unduh dari[Asumsikan situs web](https://releases.aspose.com/words/net/).

## Langkah 2: Muat Dokumen Anda

Selanjutnya, muat dokumen yang ingin Anda kerjakan. Inilah cara Anda melakukannya:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Kode ini memuat dokumen ke dalam memori sehingga Anda dapat memanipulasinya.

## Langkah 3: Konfigurasikan Pengaturan Font

 Sekarang, mari kita buat a`FontSettings` objek untuk mengelola pengaturan substitusi font:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Langkah 4: Tetapkan Substitusi Font Default

Atur substitusi font default ke font pilihan Anda. Font ini akan digunakan jika font asli tidak tersedia:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

Dalam contoh ini, kami menggunakan Arial sebagai font default.

## Langkah 5: Nonaktifkan Substitusi Info Font

Untuk menonaktifkan substitusi info font, yang menghentikan sistem mengganti font yang hilang dengan font yang tersedia, gunakan kode berikut:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Langkah 6: Terapkan Pengaturan Font ke Dokumen

Sekarang, terapkan pengaturan ini ke dokumen Anda:

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 7: Simpan Dokumen Anda

Terakhir, simpan dokumen Anda yang telah dimodifikasi. Anda dapat menyimpannya dalam format apa pun yang Anda suka. Untuk tutorial ini, kami akan menyimpannya sebagai PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengontrol substitusi font di dokumen Word Anda menggunakan Aspose.Words untuk .NET. Hal ini memastikan dokumen Anda mempertahankan tampilan dan nuansa yang diinginkan, di mana pun dokumen tersebut dilihat.

## FAQ

### Bisakah saya menggunakan font selain Arial untuk substitusi?

 Sangat! Anda dapat menentukan font apa pun yang tersedia di sistem Anda dengan mengubah nama font di`DefaultFontName` milik.

### Apa yang terjadi jika font default yang ditentukan tidak tersedia?

Jika font default tidak tersedia, Aspose.Words akan menggunakan mekanisme fallback sistem untuk menemukan pengganti yang sesuai.

### Bisakah saya mengaktifkan substitusi font lagi setelah menonaktifkannya?

 Ya, Anda dapat mengaktifkannya`Enabled` milik`FontInfoSubstitution` kembali ke`true` jika Anda ingin mengaktifkan substitusi font lagi.

### Apakah ada cara untuk memeriksa font mana yang diganti?

Ya, Aspose.Words menyediakan metode untuk mencatat dan melacak substitusi font, memungkinkan Anda melihat font mana yang diganti.

### Bisakah saya menggunakan metode ini untuk format dokumen lain selain DOCX?

Tentu saja! Aspose.Words mendukung berbagai format, dan Anda dapat menerapkan pengaturan font ini ke format apa pun yang didukung.