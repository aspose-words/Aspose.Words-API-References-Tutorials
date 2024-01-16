---
title: Dapatkan Jenis Perlindungan di Dokumen Word
linktitle: Dapatkan Jenis Perlindungan di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan fungsi Dapatkan Jenis Perlindungan di dokumen Word Aspose.Words untuk .NET untuk menentukan jenis perlindungan dokumen.
type: docs
weight: 10
url: /id/net/document-protection/get-protection-type/
---
Selamat datang di panduan langkah demi langkah yang menjelaskan kode sumber C# untuk fitur Dapatkan Jenis Perlindungan Aspose.Words untuk .NET. Pada artikel ini, kami akan menunjukkan cara menggunakan fitur canggih ini untuk menentukan jenis perlindungan dokumen. Perlindungan dokumen sangat penting untuk memastikan kerahasiaan dan integritas file Anda. Kami akan memandu Anda melalui langkah-langkah yang diperlukan untuk mengintegrasikan Aspose.Words untuk .NET dan menggunakan fitur Dapatkan Jenis Perlindungan.

## Langkah 1: Memuat Dokumen

Langkah pertama dalam menggunakan fitur Get Protection Type adalah dengan mengunggah dokumen yang ingin Anda kerjakan. Anda dapat melakukan ini menggunakan kelas Dokumen yang disediakan oleh Aspose.Words untuk .NET. Berikut ini contoh kode untuk memuat dokumen dari file:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Pastikan untuk menentukan jalur yang benar ke file dokumen Anda.

## Langkah 2: Mengambil Jenis Perlindungan

Setelah dokumen diunggah, Anda dapat menggunakan properti ProtectionType dari objek Dokumen untuk mengambil jenis perlindungan yang diterapkan pada dokumen. Inilah cara Anda melakukannya:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Contoh Kode Sumber untuk Dapatkan Jenis Perlindungan menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fungsi Get Protection Type menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Kesimpulan

Dalam artikel ini, kami menjelaskan cara menggunakan fungsi Dapatkan Jenis Perlindungan dari Aspose.Words untuk .NET untuk menentukan jenis perlindungan dokumen. Dengan mengikuti langkah-langkah yang dijelaskan, Anda akan dapat dengan mudah mengintegrasikan fungsi ini ke dalam proyek C# Anda sendiri dan memanipulasi dokumen yang dilindungi secara efisien. Aspose.Words untuk .NET menawarkan fleksibilitas yang luar biasa

### FAQ

#### T: Apa yang dimaksud dengan properti ProtectionType di Aspose.Words untuk .NET?

 J: Itu`ProtectionType` properti di Aspose.Words untuk .NET adalah fitur yang memungkinkan Anda menentukan jenis perlindungan yang diterapkan pada dokumen Word. Ini memberikan informasi tentang tingkat perlindungan dokumen, seperti apakah dokumen dilindungi dari komentar, revisi, formulir, atau jenis pembatasan lainnya.

#### T: Bagaimana cara mengambil jenis perlindungan dokumen menggunakan Aspose.Words untuk .NET?

J: Untuk mengambil jenis proteksi dokumen menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Muat dokumen menggunakan`Document` kelas.
2.  Akses`ProtectionType` properti dari`Document`objek untuk mengambil jenis perlindungan.

#### T: Dapatkah saya menentukan apakah suatu dokumen dilindungi untuk formulir atau bidang formulir menggunakan properti ProtectionType?

 J: Ya, Anda bisa menentukan apakah dokumen dilindungi untuk formulir atau bidang formulir menggunakan`ProtectionType` properti di Aspose.Words untuk .NET. Jika jenis perlindungan diatur ke`AllowOnlyFormFields`, ini menunjukkan bahwa dokumen dilindungi, dan hanya bidang formulir yang dapat diedit.

#### T: Jenis perlindungan lain apa yang dapat dikembalikan oleh properti ProtectionType?

 J: Itu`ProtectionType` properti di Aspose.Words untuk .NET dapat mengembalikan berbagai jenis perlindungan, termasuk:
- `NoProtection`: Dokumen tidak dilindungi.
- `AllowOnlyRevisions`: Dokumen dilindungi, dan hanya revisi yang dapat dilakukan.
- `AllowOnlyComments`: Dokumen dilindungi, dan hanya komentar yang dapat ditambahkan.
- `AllowOnlyFormFields`: Dokumen dilindungi, dan hanya kolom formulir yang dapat diedit.
- `ReadOnly`: Dokumen dilindungi dan ditetapkan sebagai hanya-baca.

#### T: Dapatkah saya mengubah jenis perlindungan dokumen menggunakan properti ProtectionType?

 J: Tidak, itu`ProtectionType`properti di Aspose.Words untuk .NET adalah properti hanya-baca. Ini memungkinkan Anda untuk mengambil jenis perlindungan dokumen saat ini tetapi tidak menyediakan cara langsung untuk mengubah jenis perlindungan. Untuk mengubah jenis perlindungan, Anda perlu menggunakan metode dan properti lain yang tersedia di`Document` kelas, seperti`Protect` atau`Unprotect`.

#### T: Apakah mungkin untuk melindungi dokumen dengan beberapa jenis perlindungan secara bersamaan?

J: Tidak, Aspose.Words untuk .NET hanya mengizinkan satu jenis perlindungan untuk diterapkan ke dokumen dalam satu waktu. Namun, Anda dapat menggabungkan berbagai jenis perlindungan dengan mengaktifkan perlindungan, mengatur satu jenis, menonaktifkan perlindungan, lalu mengaktifkannya kembali dengan jenis lainnya.

