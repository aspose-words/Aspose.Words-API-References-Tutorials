---
title: Tetapkan Tingkat Kompresi
linktitle: Tetapkan Tingkat Kompresi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur tingkat kompresi saat menyimpan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk mengatur tingkat kompresi saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengontrol tingkat kompresi dokumen yang dihasilkan.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file DOCX untuk dimuat.

## Langkah 3: Mengonfigurasi opsi pencadangan OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Pada langkah ini, kami mengonfigurasi opsi penyimpanan OOXML menggunakan`OoxmlSaveOptions` kelas. Kami mengatur tingkat kompresi ke`SuperFast` untuk mendapatkan kompresi yang lebih cepat.

## Langkah 4: Simpan dokumen dengan tingkat kompresi yang ditentukan

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Pada langkah terakhir ini, kita menyimpan dokumen menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.docx` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk mengatur tingkat kompresi saat menyimpan dokumen. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Contoh kode sumber untuk Menetapkan Tingkat Kompresi menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fungsionalitas pengaturan tingkat kompresi saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Dengan menentukan tingkat kompresi yang sesuai, Anda dapat mengoptimalkan ukuran dokumen dan kecepatan pembuatan.

 Itu`OoxmlSaveOptions` kelas memberikan fleksibilitas untuk mengontrol tingkat kompresi dengan mengatur`CompressionLevel` properti dengan nilai yang sesuai, seperti`SuperFast`. Hal ini memungkinkan Anda mencapai keseimbangan yang tepat antara ukuran file dan kecepatan pencadangan berdasarkan kebutuhan spesifik Anda.

Penggunaan kompresi dapat bermanfaat ketika Anda perlu mengurangi ukuran file yang dihasilkan, terutama untuk dokumen berukuran besar. Hal ini dapat mempermudah penyimpanan, berbagi, dan mengirimkan dokumen.

Aspose.Words untuk .NET menawarkan serangkaian opsi dan fitur canggih untuk manipulasi dokumen. Dengan menggunakan opsi pencadangan yang sesuai, Anda dapat menyesuaikan proses pembuatan dokumen dan mengoptimalkan kinerja aplikasi Anda.

Jangan ragu untuk menjelajahi lebih banyak fitur Aspose.Words untuk .NET untuk meningkatkan alur kerja pembuatan dokumen Anda.
