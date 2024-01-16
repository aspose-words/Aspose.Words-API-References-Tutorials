---
title: Dapatkan Nama Bidang Gabungan Surat
linktitle: Dapatkan Nama Bidang Gabungan Surat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendapatkan nama bidang gabungan surat di dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/get-mail-merge-field-names/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Dapatkan Penggabungan Nama Bidang" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Memuat dokumen

Langkah pertama adalah memuat dokumen tempat Anda ingin mendapatkan nama bidang gabungan.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Pastikan untuk mengganti "FILE DOKUMEN ANDA" dengan nama file Anda sendiri.

## Langkah 3: Dapatkan nama bidang gabungan

 Kami menggunakan`GetFieldNames()` metode untuk mendapatkan array yang berisi nama bidang gabungan yang ada dalam dokumen.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 Itu`fieldNames` variabel sekarang berisi nama bidang gabungan.

### Contoh Kode Sumber untuk Dapatkan Gabungkan Nama Bidang dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Dapatkan nama bidang gabungan.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Menampilkan jumlah bidang gabungan.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Dalam contoh ini, kami memuat dokumen, mendapatkan nama bidang gabungan menggunakan`GetFieldNames()` metode, dan menampilkan jumlah bidang gabungan yang ada dalam dokumen.

Ini menyimpulkan panduan kami tentang penggunaan fitur "Dapatkan Gabungkan Nama Bidang" dengan Aspose.Words untuk .NET.

### FAQ

#### Q1: Apa itu gabungan surat di Aspose.Words?

Penggabungan surat di Aspose.Words adalah proses menggabungkan data dari sumber eksternal (misalnya spreadsheet atau database Excel) dengan templat dokumen Word untuk membuat dokumen yang dipersonalisasi. Hal ini memfasilitasi pembuatan surat, laporan, dan dokumen serupa lainnya secara otomatis.

#### Q2: Bagaimana cara mendapatkan daftar bidang gabungan surat yang tersedia di dokumen Word?

Untuk mendapatkan daftar bidang gabungan surat yang tersedia di dokumen Word, Anda bisa mengikuti langkah-langkah berikut:

1. Impor kelas Document dan MailMergeFieldNames dari namespace Aspose.Words.
2. Buat instance Dokumen dengan memuat dokumen Word Anda.
3. Gunakan metode GetMailMergeFieldNames objek Dokumen untuk mendapatkan daftar bidang gabungan surat yang tersedia.

Berikut ini contoh kode untuk mengilustrasikan prosesnya:

```csharp
// Impor namespace yang diperlukan
using Aspose.Words;
using Aspose.Words.MailMerging;

// Muat dokumen yang ada
Document document = new Document("FilePath");

// Dapatkan daftar bidang gabungan surat
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Telusuri bidang gabungan surat yang tersedia
foreach (string fieldName in fieldNames)
{
     // Lakukan sesuatu dengan nama bidang
     Console.WriteLine(fieldName);
}
```
### FAQ

#### T: Apa itu gabungan surat di Aspose.Words?

A: Penggabungan surat di Aspose.Words adalah proses menggabungkan data dari sumber eksternal (misalnya spreadsheet atau database Excel) dengan templat dokumen Word untuk membuat dokumen yang dipersonalisasi. Hal ini memfasilitasi pembuatan surat, laporan, dan dokumen serupa lainnya secara otomatis.

#### T: Bagaimana cara mendapatkan daftar bidang gabungan surat yang tersedia di dokumen Word?

J: Untuk mendapatkan daftar bidang gabungan surat yang tersedia di dokumen Word, Anda bisa mengikuti langkah-langkah berikut:

1. Impor kelas Document dan MailMergeFieldNames dari namespace Aspose.Words.
2. Buat instance Dokumen dengan memuat dokumen Word Anda.
3. Gunakan metode GetMailMergeFieldNames objek Dokumen untuk mendapatkan daftar bidang gabungan surat yang tersedia.

#### T: Bisakah saya mendapatkan kolom gabungan surat dari sumber data eksternal seperti spreadsheet Excel?

J: Ya, Anda bisa mendapatkan kolom gabungan surat dari sumber data eksternal seperti spreadsheet Excel. Untuk ini, Anda dapat menggunakan fitur pengikatan data Aspose.Words untuk membuat koneksi dengan sumber data dan mendapatkan nama bidang yang tersedia.

#### T: Apakah mungkin memfilter bidang gabungan surat berdasarkan kriteria tertentu?

J: Ya, dimungkinkan untuk memfilter bidang gabungan surat berdasarkan kriteria tertentu. Anda bisa menggunakan ekspresi reguler atau ketentuan khusus untuk memfilter bidang gabungan surat dan hanya mendapatkan bidang yang memenuhi kriteria spesifik Anda.

#### T: Bagaimana cara memanipulasi bidang gabungan surat di Aspose.Words?

J: Untuk memanipulasi bidang gabungan surat di Aspose.Words, Anda bisa menggunakan metode dan properti yang disediakan oleh objek Dokumen dan MailMergeField. Anda dapat menambah, menghapus, atau memperbarui bidang gabungan surat, serta mengambil dan mengedit nilai yang terkait dengan bidang.