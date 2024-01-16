---
title: Perlindungan Hanya Baca Dalam Dokumen Word
linktitle: Perlindungan Hanya Baca Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara melindungi dokumen Word hanya-baca dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-protection/read-only-protection/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur perlindungan baca-saja Aspose.Words untuk .NET. Fitur ini memungkinkan Anda membuat dokumen Word hanya-baca untuk mencegah modifikasi yang tidak sah. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Menerapkan Perlindungan

Mulailah dengan membuat instance kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tulis konten ke dokumen
Gunakan objek DocumentBuilder untuk menulis konten ke dokumen:

```csharp
builder.Write("Open document as read-only");
```

## Langkah 3: Tetapkan kata sandi dan jadikan dokumen hanya-baca

Tetapkan kata sandi untuk dokumen menggunakan properti SetPassword() dari objek WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Pastikan untuk mengganti "Kata Sandi Saya" dengan kata sandi sebenarnya yang ingin Anda gunakan.

## Langkah 4: Terapkan dokumen read-only

Jadikan dokumen hanya-baca dengan menyetel properti ReadOnlyRecommended ke true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Langkah 5: Terapkan perlindungan read-only dan simpan dokumen

Terakhir, terapkan perlindungan read-only menggunakan metode Protect() pada objek Dokumen:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen yang dilindungi.

### Contoh kode sumber untuk Perlindungan Hanya Baca menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk proteksi read-only menggunakan Aspose.Words for .NET:

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Masukkan kata sandi yang panjangnya maksimal 15 karakter.
doc.WriteProtection.SetPassword("MyPassword");

// Jadikan dokumen sebagai hanya-baca.
doc.WriteProtection.ReadOnlyRecommended = true;

// Terapkan perlindungan tulis sebagai hanya-baca.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah melindungi dokumen Anda

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur perlindungan baca-saja dari Aspose.Words untuk .NET, yang memungkinkan Anda menjadikan dokumen Word hanya-baca untuk mencegah modifikasi yang tidak sah. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat dengan mudah menerapkan perlindungan hanya-baca pada dokumen Anda dan meningkatkan keamanannya. Perlindungan hanya baca membantu memastikan integritas dan keakuratan konten dokumen Anda dengan membatasi kemampuan pengeditan. Aspose.Words for .NET menyediakan API yang kuat dan fleksibel untuk menangani perlindungan dokumen dan mendukung berbagai fitur lain untuk menyesuaikan dan mengamankan dokumen Word Anda.

### FAQ untuk perlindungan hanya baca di dokumen Word

#### T: Apa yang dimaksud dengan perlindungan baca-saja di Aspose.Words untuk .NET?

J: Perlindungan baca-saja di Aspose.Words untuk .NET adalah fitur yang memungkinkan Anda membuat dokumen Word hanya-baca, mencegah modifikasi yang tidak sah. Ketika dokumen diatur ke baca-saja, pengguna dapat membuka dan melihat dokumen, namun mereka tidak dapat membuat perubahan apa pun pada kontennya.

#### T: Bagaimana cara menerapkan perlindungan baca-saja pada dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk menerapkan perlindungan baca-saja pada dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Menggunakan`DocumentBuilder` untuk menulis konten ke dokumen.
3.  Tetapkan kata sandi untuk dokumen menggunakan`SetPassword` metode`WriteProtection` obyek.
4.  Mengatur`ReadOnlyRecommended` properti dari`WriteProtection` objek untuk`true` untuk merekomendasikan membuka dokumen sebagai hanya-baca.
5.  Terapkan perlindungan hanya-baca menggunakan`Protect` metode`Document` objek, menentukan`ProtectionType` sebagai`ReadOnly`.
6.  Simpan dokumen yang diproteksi menggunakan`Save` metode`Document` obyek.

#### T: Dapatkah saya menghapus perlindungan baca-saja dari dokumen Word menggunakan Aspose.Words untuk .NET?

J: Ya, Anda dapat menghapus perlindungan baca-saja dari dokumen Word menggunakan Aspose.Words untuk .NET. Untuk melakukan ini, Anda dapat menggunakan`Unprotect` metode`Document` kelas, yang menghilangkan perlindungan yang ada dari dokumen.

#### T: Dapatkah saya menetapkan kata sandi berbeda untuk perlindungan baca-saja di dokumen Word?

 J: Tidak, perlindungan baca-saja di Aspose.Words untuk .NET tidak mengizinkan Anda menyetel kata sandi terpisah khusus untuk perlindungan baca-saja. Kata sandi diatur menggunakan`SetPassword` metode`WriteProtection` objek berlaku untuk perlindungan dokumen secara keseluruhan, termasuk perlindungan baca-saja dan baca-tulis.

#### T: Dapatkah pengguna mengabaikan perlindungan baca-saja di dokumen Word?

J: Perlindungan baca-saja di dokumen Word dimaksudkan untuk mencegah dan mencegah modifikasi yang tidak disengaja atau tidak sah. Meskipun memberikan tingkat perlindungan, ini dapat dilewati oleh pengguna yang memiliki pengetahuan teknis atau izin pengeditan yang memadai. Namun, perlindungan read-only berfungsi sebagai pencegah dan membantu menjaga integritas dokumen.