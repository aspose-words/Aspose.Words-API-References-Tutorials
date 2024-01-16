---
title: Fitur Tipe Terbuka
linktitle: Fitur Tipe Terbuka
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengaktifkan dan menggunakan fitur Tipe Terbuka di Aspose.Words untuk .NET
type: docs
weight: 10
url: /id/net/enable-opentype-features/open-type-features/
---

Dalam tutorial komprehensif ini, Anda akan mempelajari cara mengaktifkan dan memanfaatkan fitur Open Type di Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat bekerja dengan fitur Open Type di dokumen Word Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Muat Dokumen
Untuk memulai, muat dokumen menggunakan kelas Dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Langkah 2: Aktifkan Fitur Tipe Terbuka
Untuk mengaktifkan fitur Open Type, atur properti TextShaperFactory dari kelas LayoutOptions ke instance pabrik pembentuk teks yang diinginkan. Dalam contoh ini, kami menggunakan HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Langkah 3: Simpan Dokumen
Setelah mengaktifkan fitur Open Type, simpan dokumen dalam format output yang diinginkan, seperti PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Contoh Kode Sumber untuk Fitur Tipe Terbuka menggunakan Aspose.Words untuk .NET
Berikut source code lengkap penggunaan fitur Open Type di Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengaktifkan dan memanfaatkan fitur Open Type di Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat bekerja dengan fitur Tipe Terbuka di dokumen Word Anda.

Fitur Tipe Terbuka menawarkan kemampuan tipografi dan pembentukan teks yang ditingkatkan, memungkinkan Anda membuat dokumen yang menarik secara visual dan terlihat profesional. Bereksperimenlah dengan pabrik pembentuk teks yang berbeda dan jelajahi kemungkinan fitur Tipe Terbuka di proyek Anda.

### FAQ

#### T: Bagaimana cara mengaktifkan fitur OpenType di Aspose.Words untuk .NET?

J: Untuk mengaktifkan fitur OpenType di Aspose.Words untuk .NET, Anda perlu mengikuti langkah-langkah yang disebutkan dalam tutorial.

#### T: Fitur OpenType apa yang didukung di Aspose.Words untuk .NET?

J: Aspose.Words untuk .NET mendukung beberapa fitur OpenType, seperti pengikat, variasi mesin terbang, substitusi kontekstual, dan banyak lagi.

#### T: Bagaimana cara memeriksa apakah fitur OpenType didukung pada font tertentu?

J: Anda dapat memeriksa apakah fitur OpenType didukung dalam font tertentu menggunakan`Font.OpenTypeFeatures` metode di Aspose.Words untuk .NET.

#### T: Apa saja fitur pemformatan teks lain yang didukung Aspose.Words for .NET?

J: Selain fitur OpenType, Aspose.Words for .NET juga mendukung fitur pemformatan teks lainnya seperti memformat paragraf, membuat tabel, menambahkan gambar, dll.

#### T: Bisakah saya menggunakan fitur OpenType di semua versi Aspose.Words untuk .NET?

J: Fitur OpenType didukung di versi Aspose.Words for .NET yang lebih baru. Pastikan Anda menggunakan versi yang kompatibel untuk memanfaatkan fitur ini.