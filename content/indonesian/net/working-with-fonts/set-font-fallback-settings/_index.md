---
title: Atur Pengaturan Penggantian Font
linktitle: Atur Pengaturan Penggantian Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur Pengaturan Penggantian Font di Aspose.Words untuk .NET. Panduan komprehensif ini memastikan semua karakter dalam dokumen Anda ditampilkan dengan benar.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-font-fallback-settings/
---
## Perkenalan

Saat bekerja dengan dokumen yang berisi beragam elemen teks, seperti bahasa berbeda atau karakter khusus, penting untuk memastikan bahwa elemen tersebut ditampilkan dengan benar. Aspose.Words untuk .NET menawarkan fitur canggih yang disebut Pengaturan Penggantian Font, yang membantu dalam menentukan aturan untuk mengganti font ketika font asli tidak mendukung karakter tertentu. Dalam panduan ini, kita akan mempelajari cara menyiapkan Pengaturan Penggantian Font menggunakan Aspose.Words untuk .NET dalam tutorial langkah demi langkah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan kerangka .NET.
-  Aspose.Words untuk .NET: Unduh dan instal dari[tautan unduhan](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Pengaturan seperti Visual Studio untuk menulis dan menjalankan kode Anda.
-  Contoh Dokumen: Miliki contoh dokumen (misalnya,`Rendering.docx`) siap untuk pengujian.
- XML Aturan Penggantian Font: Siapkan file XML yang mendefinisikan aturan penggantian font.

## Impor Namespace

Untuk menggunakan Aspose.Words, Anda perlu mengimpor namespace yang diperlukan. Hal ini memungkinkan akses ke berbagai kelas dan metode yang diperlukan untuk pemrosesan dokumen.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Langkah 1: Tentukan Direktori Dokumen

Pertama, tentukan direktori tempat dokumen Anda disimpan. Ini penting untuk menemukan dan memproses dokumen Anda.

```csharp
// Jalur ke direktori dokumen
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen

 Muat dokumen Anda ke dalam Aspose.Words`Document` obyek. Langkah ini memungkinkan Anda bekerja dengan dokumen secara terprogram.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan Pengaturan Font

 Buat yang baru`FontSettings` objek dan memuat pengaturan fallback font dari file XML. File XML ini berisi aturan untuk penggantian font.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Langkah 4: Terapkan Pengaturan Font ke Dokumen

 Tetapkan yang dikonfigurasi`FontSettings`ke dokumen. Hal ini memastikan bahwa aturan penggantian font diterapkan saat merender dokumen.

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen tersebut. Pengaturan penggantian font akan digunakan selama operasi penyimpanan untuk memastikan penggantian font yang tepat.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## File XML: Aturan Penggantian Font

Berikut adalah contoh tampilan file XML Anda yang menentukan aturan penggantian font:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif menyiapkan dan menggunakan Pengaturan Penggantian Font di Aspose.Words untuk .NET. Hal ini memastikan dokumen Anda menampilkan semua karakter dengan benar, meskipun font asli tidak mendukung karakter tertentu. Menerapkan pengaturan ini akan sangat meningkatkan kualitas dan keterbacaan dokumen Anda.

## FAQ

### Q1: Apa itu Penggantian Font?

Font Fallback adalah fitur yang memungkinkan penggantian font ketika font asli tidak mendukung karakter tertentu, memastikan tampilan semua elemen teks dengan benar.

### Q2: Dapatkah saya menentukan beberapa font cadangan?

Ya, Anda dapat menentukan beberapa font cadangan dalam aturan XML. Aspose.Words akan memeriksa setiap font sesuai urutan yang ditentukan hingga menemukan font yang mendukung karakter tersebut.

### Q3: Di mana saya dapat mengunduh Aspose.Words untuk .NET?

 Anda dapat mengunduhnya dari[Asumsikan halaman unduh](https://releases.aspose.com/words/net/).

### Q4: Bagaimana cara membuat file XML untuk aturan penggantian font?

File XML dapat dibuat menggunakan editor teks apa pun. Itu harus mengikuti struktur yang ditunjukkan pada contoh yang diberikan dalam tutorial ini.

### Q5: Apakah tersedia dukungan untuk Aspose.Words?

 Ya, Anda dapat menemukan dukungan di[Forum dukungan Aspose.Words](https://forum.aspose.com/c/words/8).