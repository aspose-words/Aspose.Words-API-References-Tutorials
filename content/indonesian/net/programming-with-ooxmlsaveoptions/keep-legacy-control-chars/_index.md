---
title: Pertahankan Karakter Kontrol Lama
linktitle: Pertahankan Karakter Kontrol Lama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mempertahankan karakter kontrol lama saat menyimpan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk mempertahankan karakter kontrol lama saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mempertahankan karakter kontrol khusus saat mengonversi atau menyimpan dokumen.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file yang berisi karakter kontrol yang diwarisi.

## Langkah 3: Mengonfigurasi opsi pencadangan OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 Pada langkah ini, kami mengonfigurasi opsi penyimpanan OOXML dengan membuat yang baru`OoxmlSaveOptions` obyek. Kami menentukan format penyimpanan yang diinginkan (di sini,`FlatOpc` ) dan aktifkan`KeepLegacyControlChars` opsi untuk mempertahankan karakter kontrol lama.

## Langkah 4: Menyimpan dokumen dengan karakter kontrol lama

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Pada langkah terakhir ini, kita menyimpan dokumen menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.docx` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk mempertahankan karakter kontrol lama saat menyimpan dokumen. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Contoh kode sumber untuk Pertahankan Karakter Kontrol Lama menggunakan Aspose.Words untuk .NET 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fungsionalitas mempertahankan karakter kontrol lama saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Kita telah mempelajari cara mempertahankan karakter khusus yang mungkin penting untuk pemformatan atau tampilan dokumen yang benar.

 Mempertahankan karakter kontrol warisan sangat berguna ketika Pemrosesan Kata dengan dokumen yang menggunakan fitur yang lebih lama atau spesifik, seperti karakter kontrol khusus. Dengan mengaktifkan`KeepLegacyControlChars` pilihan saat menyimpan dokumen, Anda memastikan bahwa karakter ini dipertahankan.

Aspose.Words for .NET menawarkan serangkaian opsi pencadangan yang fleksibel dan kuat untuk memenuhi kebutuhan manipulasi dokumen Anda. Dengan menggunakan opsi yang sesuai, Anda dapat menyesuaikan proses pencadangan untuk mempertahankan karakteristik spesifik dokumen Anda.

Jangan ragu untuk menggabungkan fungsi ini ke dalam proyek Aspose.Words for .NET Anda untuk memastikan integritas dan pelestarian karakter kontrol lama dalam dokumen Anda.