---
title: Atur Versi Ms Word
linktitle: Atur Versi Ms Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memuat dokumen dengan versi MS Word tertentu menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-loadoptions/set-ms-word-version/
---
Saat Memproses Kata dengan dokumen Word dalam aplikasi C#, mungkin perlu menentukan versi Microsoft Word yang akan digunakan saat memuat dokumen. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah mengatur versi MS Word mana yang akan digunakan menggunakan LoadOptions. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber Aspose.Words untuk .NET C# untuk memuat dokumen dengan versi MS Word tertentu menggunakan opsi pemuatan LoadOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Mengonfigurasi Opsi Pemuatan

Langkah pertama adalah mengkonfigurasi opsi pemuatan untuk dokumen kita. Gunakan kelas LoadOptions untuk menentukan parameter pemuatan. Dalam kasus kita, kita perlu mengatur properti MswVersion ke versi MS Word yang diinginkan. Misalnya kita menggunakan Microsoft Word versi 2010. Inilah cara melakukannya:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Kami membuat objek LoadOptions baru dan mengatur properti MswVersion ke MsWordVersion.Word2010 untuk menentukan versi MS Word 2010.

## Pemuatan dokumen dengan versi MS Word yang ditentukan

Sekarang kita telah mengkonfigurasi opsi pemuatan, kita dapat memuat dokumen menggunakan kelas Dokumen dan menentukan opsi pemuatan. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Dalam contoh ini, kita memuat dokumen "Document.docx" yang terletak di direktori dokumen menggunakan opsi pemuatan yang ditentukan.

### Contoh kode sumber untuk LoadOptions dengan fungsionalitas "Atur Versi MS Word" menggunakan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurasikan opsi pemuatan dengan fitur "Atur Versi MS Word".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Muat dokumen dengan versi MS Word yang ditentukan
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Simpan dokumennya
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Kesimpulan

Dalam panduan ini, kami telah menjelaskan cara mengunggah dokumen yang menentukan versi MS Word tertentu menggunakan perpustakaan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan sumber kode C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Memuat dokumen dengan versi MS Word tertentu memungkinkan Anda memastikan kompatibilitas dan pemrosesan dokumen yang tepat dalam aplikasi Anda.


### FAQ

#### T: Mengapa saya perlu menentukan versi MS Word saat memuat dokumen dalam aplikasi C#?

Menentukan versi MS Word memastikan bahwa dokumen dimuat dan diproses dengan benar, terutama ketika berhadapan dengan format atau fitur tertentu yang mungkin berbeda antar versi.

#### T: Versi MS Word apa yang didukung Aspose.Words?

J: Aspose.Words untuk .NET mendukung berbagai versi MS Word, termasuk Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019, dan banyak lagi.

#### T: Dapatkah saya memuat dokumen dengan versi MS Word yang berbeda dengan yang terinstal di sistem saya?

J: Ya, Aspose.Words memungkinkan Anda menentukan versi MS Word yang berbeda saat memuat dokumen, memastikan kompatibilitas meskipun sistem target memiliki versi MS Word yang berbeda.

#### T: Apa manfaat pengaturan versi MS Word untuk aplikasi C# saya?

J: Mengatur versi MS Word memastikan bahwa dokumen diproses sesuai dengan format dan fitur yang diinginkan dari versi spesifik tersebut, sehingga memberikan keluaran yang konsisten.

#### T: Apakah Aspose.Words terbatas pada penanganan dokumen DOCX saja?

J: Tidak, Aspose.Words mendukung berbagai format dokumen, termasuk DOC, RTF, HTML, PDF, dan banyak lagi, menjadikannya alat serbaguna untuk menangani berbagai jenis dokumen.