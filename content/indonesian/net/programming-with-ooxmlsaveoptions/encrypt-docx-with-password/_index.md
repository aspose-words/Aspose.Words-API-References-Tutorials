---
title: Enkripsi Docx Dengan Kata Sandi
linktitle: Enkripsi Docx Dengan Kata Sandi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengenkripsi file DOCX dengan kata sandi menggunakan Aspose.Words untuk .NET. Tutorial lengkap untuk keamanan dokumen.
type: docs
weight: 10
url: /id/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk mengenkripsi file DOCX dengan kata sandi menggunakan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda melindungi dokumen Anda dengan membuatnya hanya dapat diakses dengan kata sandi tertentu.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 Pada langkah ini, kami mengonfigurasi opsi penyimpanan OOXML dengan membuat yang baru`OoxmlSaveOptions` obyek. Kami menentukan kata sandi yang diinginkan untuk mengenkripsi dokumen dengan mengatur`Password` properti ke kata sandi khusus Anda.

## Langkah 4: Mengenkripsi dokumen dengan kata sandi

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 Pada langkah terakhir ini, kita menyimpan dokumen menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.docx` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk mengenkripsi dokumen DOCX Anda dengan kata sandi. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Pastikan untuk menyimpan kata sandi Anda dengan aman, karena kata sandi tersebut diperlukan untuk membuka dokumen terenkripsi.

### Contoh kode sumber untuk Enkripsi Docx Dengan Kata Sandi menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Kesimpulan

Dalam tutorial ini, kami menjelajahi fungsionalitas mengenkripsi file DOCX dengan kata sandi menggunakan Aspose.Words untuk .NET. Kami mempelajari cara melindungi dokumen kami dengan membuatnya hanya dapat diakses dengan kata sandi tertentu.

Enkripsi dokumen adalah langkah keamanan penting untuk melindungi informasi sensitif. Berkat Aspose.Words untuk .NET, kita dapat dengan mudah menambahkan fungsi ini ke aplikasi kita.

Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengintegrasikan enkripsi kata sandi ke proyek Aspose.Words untuk .NET Anda dan memastikan kerahasiaan dokumen Anda.

Jangan ragu untuk bereksperimen dengan fitur lain yang ditawarkan oleh Aspose.Words untuk .NET untuk memperkaya aplikasi Anda dengan fitur manipulasi dokumen tingkat lanjut.
