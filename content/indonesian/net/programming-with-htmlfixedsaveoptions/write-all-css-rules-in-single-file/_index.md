---
title: Tulis Semua Aturan Css Dalam Satu File
linktitle: Tulis Semua Aturan Css Dalam Satu File
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word menjadi HTML tetap dengan menulis semua aturan CSS dalam satu file dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Saat mengonversi dokumen Word menjadi HTML tetap dalam aplikasi C#, Anda mungkin ingin menggabungkan semua aturan CSS ke dalam satu file untuk organisasi dan portabilitas yang lebih baik. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah menentukan fungsionalitas ini menggunakan opsi penyimpanan HtmlFixedSaveOptions. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber Aspose.Words untuk .NET C# untuk mengonversi dokumen Word menjadi HTML tetap dengan menulis semua aturan CSS dalam satu file menggunakan opsi penyimpanan HtmlFixedSaveOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami pustaka Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Memuat dokumen Word

Langkah pertama adalah memuat dokumen Word yang ingin Anda konversi ke HTML tetap. Gunakan kelas Dokumen untuk memuat dokumen dari file sumber. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Dalam contoh ini, kita memuat dokumen "Document.docx" yang terletak di direktori dokumen.

## Mengonfigurasi opsi cadangan

Langkah selanjutnya adalah mengonfigurasi opsi penyimpanan untuk mengonversi ke HTML tetap. Gunakan kelas HtmlFixedSaveOptions dan atur properti SaveFontFaceCssSeparately ke false untuk menulis semua aturan CSS dalam satu file. Berikut cara melakukannya:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Kami membuat objek HtmlFixedSaveOptions baru dan mengatur properti SaveFontFaceCssSeparately ke false untuk menulis semua aturan CSS dalam satu file.

## Memperbaiki konversi dokumen HTML

Sekarang kita telah mengonfigurasi opsi penyimpanan, kita dapat melanjutkan untuk mengonversi dokumen menjadi HTML tetap. Gunakan metode Simpan dari kelas Dokumen untuk menyimpan dokumen yang dikonversi dalam format HTML tetap dengan menentukan opsi penyimpanan. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Dalam contoh ini, kami menyimpan dokumen yang dikonversi sebagai "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" menggunakan opsi penyimpanan yang ditentukan.

### Contoh kode sumber untuk HtmlFixedSaveOptions dengan fitur "Tulis semua aturan CSS dalam satu file" menggunakan Aspose.Words untuk .NET

```csharp
// Jalur akses ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen Word
Document doc = new Document(dataDir + "Document.docx");

// Konfigurasikan opsi pencadangan dengan fitur "Tulis semua aturan CSS dalam satu file".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Ubah dokumen menjadi HTML tetap
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami telah membahas cara mengonversi dokumen Word menjadi HTML tetap dengan menulis semua aturan CSS dalam satu file menggunakan HtmlFixedSaveOptions dengan pustaka Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Menulis semua aturan CSS dalam satu file memudahkan pengorganisasian dan pengelolaan kode HTML yang dihasilkan selama konversi dokumen.