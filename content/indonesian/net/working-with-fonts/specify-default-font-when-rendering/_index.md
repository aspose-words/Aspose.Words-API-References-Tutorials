---
title: Tentukan Font Default Saat Rendering
linktitle: Tentukan Font Default Saat Rendering
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan font default saat merender dokumen Word menggunakan Aspose.Words untuk .NET. Pastikan tampilan dokumen konsisten di seluruh platform.
type: docs
weight: 10
url: /id/net/working-with-fonts/specify-default-font-when-rendering/
---
## Perkenalan

Memastikan dokumen Word Anda ditampilkan dengan benar di berbagai platform dapat menjadi sebuah tantangan, terutama ketika berhadapan dengan kompatibilitas font. Salah satu cara untuk menjaga konsistensi tampilan adalah dengan menentukan font default saat merender dokumen Anda ke PDF atau format lainnya. Dalam tutorial ini, kita akan mempelajari cara mengatur font default menggunakan Aspose.Words untuk .NET, sehingga dokumen Anda terlihat bagus di mana pun dokumen tersebut dilihat.

## Prasyarat

Sebelum mendalami kodenya, mari kita bahas apa yang perlu Anda ikuti bersama dengan tutorial ini:

- Aspose.Words untuk .NET: Pastikan Anda menginstal versi terbaru. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan .NET lainnya.
- Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda merasa nyaman dengan pemrograman C#.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan. Ini akan memungkinkan Anda untuk mengakses kelas dan metode yang diperlukan untuk bekerja dengan Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Sekarang, mari kita uraikan proses menentukan font default menjadi langkah-langkah yang mudah diikuti.

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, tentukan jalur ke direktori dokumen Anda. Di sinilah file input dan output Anda akan disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Anda

Selanjutnya, muat dokumen yang ingin Anda render. Dalam contoh ini, kita akan menggunakan file bernama "Rendering.docx".

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan Pengaturan Font

 Buat sebuah contoh dari`FontSettings` dan tentukan font default. Jika font yang ditentukan tidak dapat ditemukan selama rendering, Aspose.Words akan menggunakan font terdekat yang tersedia di mesin.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
```

## Langkah 4: Terapkan Pengaturan Font ke Dokumen

Tetapkan pengaturan font yang dikonfigurasi ke dokumen Anda.

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen dalam format yang diinginkan. Dalam hal ini, kami akan menyimpannya sebagai PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen Word Anda dirender dengan font default tertentu, menjaga konsistensi di berbagai platform. Hal ini khususnya berguna untuk dokumen yang dibagikan secara luas atau dilihat pada sistem dengan ketersediaan font yang bervariasi.


## FAQ

### Mengapa menentukan font default di Aspose.Words?
Menentukan font default memastikan dokumen Anda tampak konsisten di berbagai platform, meskipun font asli tidak tersedia.

### Apa yang terjadi jika font default tidak ditemukan saat rendering?
Aspose.Words akan menggunakan font terdekat yang tersedia di mesin untuk menjaga tampilan dokumen sedekat mungkin.

### Bisakah saya menentukan beberapa font default?
 Tidak, Anda hanya dapat menentukan satu font default. Namun, Anda dapat menangani penggantian font untuk kasus tertentu menggunakan`FontSettings` kelas.

### Apakah Aspose.Words for .NET kompatibel dengan semua versi dokumen Word?
Ya, Aspose.Words untuk .NET mendukung berbagai format dokumen Word, termasuk DOC, DOCX, RTF, dan banyak lagi.

### Di mana saya bisa mendapatkan dukungan jika saya mengalami masalah?
 Anda bisa mendapatkan dukungan dari komunitas dan pengembang Aspose di[Forum Dukungan Aspose.Words](https://forum.aspose.com/c/words/8).