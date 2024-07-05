---
title: Satuan ukur
linktitle: Satuan ukur
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan satuan ukuran saat mengonversi dokumen Word ke ODT dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-odtsaveoptions/measure-unit/
---

Saat Anda mengonversi dokumen Word ke format OpenDocument Text (ODT) dalam aplikasi C#, Anda mungkin ingin menentukan unit pengukuran yang digunakan untuk pemformatan terukur dan properti konten. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah menentukan fungsionalitas ini menggunakan opsi penyimpanan OdtSaveOptions. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber Aspose.Words untuk .NET C# untuk mengonversi dokumen Word ke ODT dengan menentukan satuan ukuran menggunakan OdtSaveOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Memuat dokumen Word

Langkah pertama adalah memuat dokumen Word yang ingin Anda konversi ke ODT. Gunakan kelas Dokumen untuk memuat dokumen dari file sumber. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Dalam contoh ini, kita memuat dokumen "Document.docx" yang terletak di direktori dokumen.

## Mengonfigurasi opsi cadangan

Langkah selanjutnya adalah mengkonfigurasi opsi cadangan untuk mengkonversi ke ODT. Gunakan kelas OdtSaveOptions dan atur properti MeasureUnit ke nilai yang diinginkan. Misalnya, jika Anda ingin menggunakan inci sebagai satuan pengukuran, atur MeasureUnit ke OdtSaveMeasureUnit.Inches. Berikut cara melakukannya:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Kami membuat objek OdtSaveOptions baru dan mengatur properti MeasureUnit ke nilai yang diinginkan, dalam kasus kami, OdtSaveMeasureUnit.Inches untuk menggunakan inci sebagai satuan pengukuran.

## Ubah dokumen menjadi ODT

Sekarang kita telah mengkonfigurasi opsi penyimpanan, kita dapat melanjutkan untuk mengkonversi dokumen ke ODT. Gunakan metode Simpan dari kelas Dokumen untuk menyimpan dokumen yang dikonversi dalam format ODT dengan menentukan opsi penyimpanan. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Dalam contoh ini, kami menyimpan dokumen yang dikonversi sebagai "WorkingWithOdtSaveOptions.MeasureUnit.odt" menggunakan opsi penyimpanan yang ditentukan.

### Contoh kode sumber untuk OdtSaveOptions dengan fungsionalitas "Satuan ukuran" menggunakan Aspose.Words untuk .NET



```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen Word
Document doc = new Document(dataDir + "Document.docx");

// Konfigurasi opsi cadangan dengan fitur "Unit pengukuran".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Ubah dokumen menjadi ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami telah menjelaskan cara mengonversi dokumen Word ke ODT dengan menentukan satuan pengukuran menggunakan opsi penyimpanan OdtSaveOptions dengan pustaka Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Menentukan satuan pengukuran saat mengonversi ke ODT memungkinkan Anda mengontrol format dan dimensi dokumen yang dihasilkan sesuai dengan kebutuhan spesifik Anda.