---
title: Izinkan Hanya Lindungi Bidang Formulir di Dokumen Word
linktitle: Izinkan Hanya Lindungi Bidang Formulir di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan Aspose.Words untuk .NET untuk melindungi dokumen Word dan hanya mengizinkan bidang formulir untuk diedit.
type: docs
weight: 10
url: /id/net/document-protection/allow-only-form-fields-protect/
---
Perlindungan dokumen adalah fitur penting saat Memproses Kata dengan file dalam aplikasi C# Anda. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah melindungi dokumen Anda dan hanya mengizinkan bidang formulir untuk diedit. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber C# untuk hanya memperbolehkan bidang formulir diedit menggunakan fitur Izinkan Hanya Perlindungan Bidang Formulir dari Aspose.Words untuk .NET.

## Langkah 1: Mengatur Direktori Dokumen

Langkah pertama adalah menentukan direktori dokumen Anda. Anda harus menentukan jalur di mana Anda ingin menyimpan dokumen yang dilindungi. Misalnya :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memasukkan Bagian dan Teks

Selanjutnya, Anda perlu memasukkan bagian dan teks ke dalam dokumen Anda. Gunakan kelas DocumentBuilder yang disediakan oleh Aspose.Words untuk membuat konten dokumen Anda. Berikut ini contoh sederhananya:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Dalam contoh ini, kita membuat dokumen kosong baru dan kemudian menggunakan DocumentBuilder untuk menambahkan sebaris teks.

## Langkah 3: Mengaktifkan Perlindungan Dokumen

 Perlindungan dokumen hanya berfungsi bila perlindungan dokumen diaktifkan. Anda dapat mengaktifkan perlindungan dokumen menggunakan`Protect` metode kelas Dokumen. Begini caranya:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Dalam contoh ini, kami mengaktifkan proteksi dokumen dengan menentukan jenis proteksi `

AllowOnlyFormFields` dan mengatur kata sandi.

## Langkah 4: Hanya Mengizinkan Bidang Formulir

Sekarang perlindungan dokumen diaktifkan, kita perlu menentukan bahwa hanya pengeditan bidang formulir yang diperbolehkan. Hal ini memastikan bahwa pengguna hanya dapat mengedit bagian dokumen yang merupakan bidang formulir. Begini caranya:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Pastikan untuk mengganti "kata sandi" dengan kata sandi yang Anda buat sebelumnya.

## Langkah 5: Menyimpan Dokumen yang Dilindungi

 Terakhir, Anda dapat menyimpan dokumen yang diproteksi menggunakan`Save` metode kelas Dokumen. Tentukan jalur file lengkap dan nama file yang diinginkan. Misalnya :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Pastikan untuk mengganti "dataDir" dengan jalur ke direktori dokumen Anda.

### Contoh kode sumber untuk fitur Izinkan Hanya Bidang Formulir Lindungi menggunakan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Sisipkan dua bagian dengan beberapa teks.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Perlindungan dokumen hanya berfungsi ketika perlindungan dokumen diaktifkan dan hanya pengeditan di bidang formulir yang diperbolehkan.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Simpan dokumen yang dilindungi.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Kesimpulan

Dalam panduan ini, kita menjelajahi cara menggunakan pustaka Aspose.Words untuk .NET guna melindungi dokumen dan hanya mengizinkan bidang formulir untuk diedit. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah mengimplementasikan fungsi ini di aplikasi C# Anda. Perlindungan dokumen sangat penting untuk menjamin keamanan dan kerahasiaan dokumen Anda.

### FAQ untuk mengizinkan hanya bidang formulir yang dilindungi dalam dokumen Word

#### T: Apa yang dimaksud dengan perlindungan dokumen di Aspose.Words untuk .NET?

J: Perlindungan dokumen di Aspose.Words untuk .NET adalah fitur yang memungkinkan Anda mengamankan dokumen Anda dengan membatasi tindakan tertentu, seperti pengeditan, pemformatan, atau modifikasi konten. Ini membantu menjaga integritas dan kerahasiaan dokumen Anda dengan mencegah perubahan yang tidak sah.

#### T: Bagaimana cara melindungi dokumen dan hanya mengizinkan bidang formulir untuk diedit menggunakan Aspose.Words untuk .NET?

J: Untuk melindungi dokumen dan hanya mengizinkan bidang formulir untuk diedit menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1. Tentukan jalur direktori untuk dokumen Anda.
2.  Sisipkan bagian dan teks ke dalam dokumen Anda menggunakan`DocumentBuilder` kelas.
3.  Aktifkan perlindungan dokumen menggunakan`Protect` metode`Document` kelas, menentukan jenis perlindungan sebagai`AllowOnlyFormFields` dan memberikan kata sandi.
4.  Simpan dokumen yang diproteksi menggunakan`Save` metode`Document` kelas.

#### T: Bisakah saya menyisipkan kolom formulir ke dalam dokumen yang dilindungi menggunakan Aspose.Words untuk .NET?

J: Ya, Anda dapat menyisipkan kolom formulir ke dalam dokumen yang dilindungi menggunakan Aspose.Words untuk .NET. Perlindungan dokumen dengan`AllowOnlyFormFields` type memungkinkan pengguna untuk mengedit hanya bidang formulir sambil melindungi konten dokumen lainnya. Anda dapat menggunakan`DocumentBuilder` kelas untuk memasukkan bidang formulir ke dalam dokumen sebelum mengaktifkan perlindungan.

#### T: Dapatkah saya menghapus perlindungan dokumen dari dokumen yang dilindungi?

 J: Ya, Anda dapat menghapus proteksi dokumen dari dokumen yang diproteksi menggunakan Aspose.Words untuk .NET. Untuk menghapus perlindungan, Anda dapat menggunakan`Unprotect` metode`Document` kelas dan berikan kata sandi yang benar. Ini akan menghapus perlindungan dan memungkinkan pengeditan dokumen tanpa batasan.

#### T: Apakah mungkin untuk melindungi dokumen dengan beberapa jenis perlindungan?

 J: Tidak, Aspose.Words untuk .NET hanya mengizinkan satu jenis perlindungan untuk diterapkan ke dokumen dalam satu waktu. Namun, itu`AllowOnlyFormFields` jenis perlindungan dapat secara efektif membatasi pengeditan pada bidang formulir sambil mengizinkan jenis perlindungan lainnya, seperti`AllowOnlyComments` atau`AllowOnlyRevisions`untuk dikombinasikan dengan perlindungan bidang formulir.

#### T: Dapatkah saya menetapkan kata sandi berbeda untuk jenis perlindungan berbeda dalam dokumen?

J: Tidak, Aspose.Words untuk .NET memungkinkan Anda mengatur kata sandi tunggal untuk perlindungan dokumen, apa pun jenis perlindungannya. Kata sandi yang sama akan digunakan untuk mengaktifkan dan menonaktifkan perlindungan dokumen.