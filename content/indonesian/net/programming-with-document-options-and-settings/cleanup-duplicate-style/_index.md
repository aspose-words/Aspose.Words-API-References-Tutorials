---
title: Gaya Duplikat Pembersihan
linktitle: Gaya Duplikat Pembersihan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk membersihkan gaya duplikat dalam dokumen menggunakan Aspose.Words untuk .NET. Kode sumber lengkap disertakan.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah demi langkah kode sumber C# untuk membersihkan gaya duplikat dengan Aspose.Words untuk .NET. Fitur ini membantu menghapus gaya duplikat dari dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita bersihkan. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Hitung gaya sebelum dibersihkan

Sebelum melanjutkan pembersihan, kami akan menghitung jumlah gaya yang ada dalam dokumen. Gunakan kode berikut untuk menampilkan jumlah gaya:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Pernyataan ini menampilkan jumlah gaya yang ada dalam dokumen.

## Langkah 4: Bersihkan gaya duplikat

Sekarang mari kita bersihkan gaya duplikat dari dokumen. Gunakan kode berikut untuk melakukan pembersihan:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Kode ini membersihkan gaya duplikat dari dokumen menggunakan opsi yang ditentukan. Dalam contoh ini, kami mengaktifkan`DuplicateStyle` opsi untuk membersihkan gaya duplikat.

## Langkah 5: Hitung gaya setelah dibersihkan

Setelah melakukan pembersihan, kami akan menghitung kembali jumlah gaya untuk memeriksa apakah sudah berkurang. Gunakan kode berikut untuk menampilkan jumlah gaya baru:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Pernyataan ini menampilkan jumlah gaya yang tersisa setelah pembersihan.

### Contoh kode sumber untuk Membersihkan Gaya Duplikat menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Hitungan gaya sebelum Pembersihan.
	Console.WriteLine(doc.Styles.Count);

	// Membersihkan gaya duplikat dari dokumen.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Jumlah gaya setelah Pembersihan dikurangi.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```