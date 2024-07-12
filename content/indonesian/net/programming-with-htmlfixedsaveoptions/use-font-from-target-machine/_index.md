---
title: Gunakan Font Dari Mesin Target
linktitle: Gunakan Font Dari Mesin Target
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word menjadi HTML tetap menggunakan font mesin target dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Saat mengonversi dokumen Word ke HTML tetap dalam aplikasi C#, Anda mungkin ingin menggunakan font mesin target untuk memastikan bahwa HTML yang dirender mempertahankan tampilan dan gaya asli dokumen. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah menentukan fungsionalitas ini menggunakan opsi penyimpanan HtmlFixedSaveOptions. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber C# Aspose.Words untuk .NET untuk mengonversi dokumen Word menjadi HTML tetap menggunakan font mesin target menggunakan HtmlFixedSaveOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Memuat dokumen Word

Langkah pertama adalah memuat dokumen Word yang ingin Anda konversi ke HTML tetap. Gunakan kelas Dokumen untuk memuat dokumen dari file sumber. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Dalam contoh ini, kita memuat dokumen "Poin-poin dengan font.docx alternatif" yang terletak di direktori dokumen.

## Mengonfigurasi opsi cadangan

Langkah selanjutnya adalah mengonfigurasi opsi penyimpanan untuk mengonversi ke HTML tetap. Gunakan kelas HtmlFixedSaveOptions dan atur properti UseTargetMachineFonts ke true untuk memberi tahu Aspose.Words agar menggunakan font dari mesin target. Berikut cara melakukannya:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Kami membuat objek HtmlFixedSaveOptions baru dan menyetel properti UseTargetMachineFonts ke true untuk menggunakan font mesin target saat mengonversi.

## Memperbaiki konversi dokumen HTML

Sekarang kita telah mengonfigurasi opsi penyimpanan, kita dapat melanjutkan untuk mengonversi dokumen menjadi HTML tetap. Gunakan metode Simpan dari kelas Dokumen untuk menyimpan dokumen yang dikonversi dalam format HTML tetap dengan menentukan opsi penyimpanan. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Dalam contoh ini, kami menyimpan dokumen yang dikonversi sebagai "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" menggunakan opsi penyimpanan yang ditentukan.

### Contoh kode sumber untuk HtmlFixedSaveOptions dengan fitur "Gunakan font dari mesin target" menggunakan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Konfigurasikan opsi pencadangan dengan fitur "Gunakan font dari mesin target".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Ubah dokumen menjadi HTML tetap
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami telah menjelaskan cara mengonversi dokumen Word menjadi HTML tetap menggunakan font mesin target dengan pustaka Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Konversi ke HTML tetap dengan font mesin target menjamin rendering dokumen yang setia dan konsisten dalam format HTML.
