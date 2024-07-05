---
title: Hapus Perlindungan Dokumen Di Dokumen Word
linktitle: Hapus Perlindungan Dokumen Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus perlindungan di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-protection/remove-document-protection/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur buka proteksi dokumen Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menghapus perlindungan di dokumen Word agar dapat diakses untuk pengeditan lebih lanjut. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Menambahkan Konten

Mulailah dengan membuat instance kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tambahkan konten ke dokumen

Gunakan objek DocumentBuilder untuk menambahkan konten ke dokumen:

```csharp
builder.Writeln("Text added to a document.");
```

## Langkah 3: Buka Proteksi Dokumen

Untuk membuka proteksi dokumen, Anda dapat menggunakan metode Unprotect() pada objek Dokumen. Anda dapat memilih untuk menghapus perlindungan tanpa kata sandi atau dengan kata sandi yang benar. Menghapus perlindungan tanpa kata sandi:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Pastikan untuk mengganti "Kata Sandi Baru" dengan kata sandi dokumen yang benar.

## Langkah 4: Simpan dokumen tanpa perlindungan

Terakhir, simpan dokumen tanpa proteksi menggunakan metode Save() pada objek Dokumen:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen tanpa perlindungan.

### Contoh kode sumber untuk Hapus Perlindungan Dokumen menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk membuka proteksi dokumen menggunakan Aspose.Words for .NET:

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// Dokumen dapat dihapus perlindungannya tanpa kata sandi, atau dengan kata sandi yang benar.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menghapus perlindungan dari dokumen Word dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara menghapus proteksi dokumen di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah membuka proteksi dokumen dan membuatnya dapat diakses untuk pengeditan lebih lanjut. Aspose.Words untuk .NET menyediakan API canggih yang memungkinkan Anda memanipulasi pengaturan perlindungan dokumen dan menyesuaikan tingkat keamanan untuk dokumen Word Anda. Menghapus perlindungan dokumen memberi Anda fleksibilitas untuk mengubah konten dan format dokumen sesuai kebutuhan.

### FAQ untuk menghapus perlindungan dokumen di dokumen Word

#### T: Apa yang dimaksud dengan perlindungan dokumen di Aspose.Words untuk .NET?

J: Perlindungan dokumen di Aspose.Words untuk .NET mengacu pada fitur yang memungkinkan Anda menerapkan tindakan keamanan pada dokumen Word untuk membatasi pengeditan, pemformatan, dan modifikasi konten. Ini membantu memastikan integritas dan kerahasiaan dokumen.

#### T: Bagaimana cara menghapus perlindungan dokumen menggunakan Aspose.Words untuk .NET?

J: Untuk menghapus proteksi dokumen menggunakan Aspose.Words for .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Menggunakan`DocumentBuilder` untuk menambahkan konten ke dokumen.
3.  Hubungi`Unprotect` metode`Document` keberatan untuk menghapus perlindungan yang ada dari dokumen. Hal ini dapat dilakukan tanpa kata sandi atau dengan memberikan kata sandi yang benar.
4.  Simpan dokumen yang tidak dilindungi menggunakan`Save` metode`Document` obyek.

#### T: Dapatkah saya menghapus perlindungan dari dokumen Word tanpa kata sandi?

 J: Ya, Anda dapat menghapus perlindungan dari dokumen Word tanpa kata sandi menggunakan Aspose.Words untuk .NET. Dengan menelepon`Unprotect` metode`Document`objek tanpa memberikan kata sandi, Anda dapat menghapus perlindungan dari dokumen jika sebelumnya dilindungi tanpa kata sandi.

#### T: Bagaimana cara menghapus perlindungan dari dokumen Word dengan kata sandi?

 J: Untuk menghapus perlindungan dari dokumen Word yang dilindungi dengan kata sandi, Anda perlu memberikan kata sandi yang benar saat memanggil`Unprotect` metode`Document` obyek. Hal ini memastikan bahwa hanya pengguna dengan kata sandi yang benar yang dapat menghapus perlindungan dan mengakses dokumen untuk diedit.

#### T: Bisakah saya menghapus tipe perlindungan tertentu dari dokumen Word?

 J: Ya, menggunakan Aspose.Words untuk .NET, Anda dapat secara selektif menghapus jenis perlindungan tertentu dari dokumen Word. Dengan menelepon`Unprotect` metode`Document` objek, Anda dapat menghapus jenis proteksi yang diinginkan, seperti proteksi read-only atau proteksi formulir, sambil membiarkan jenis proteksi lainnya tetap utuh.