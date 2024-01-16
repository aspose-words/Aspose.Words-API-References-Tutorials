---
title: Bersihkan Gaya dan Daftar yang Tidak Digunakan
linktitle: Bersihkan Gaya dan Daftar yang Tidak Digunakan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk membersihkan gaya dan daftar yang tidak digunakan dalam dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk membersihkan gaya dan daftar yang tidak digunakan dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menghapus gaya dan daftar yang tidak digunakan dalam dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang berisi gaya dan daftar yang tidak terpakai yang ingin kita bersihkan. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Hitung gaya dan daftar sebelum dibersihkan

Sebelum membersihkan, kami akan menghitung jumlah gaya dan daftar yang ada di dokumen. Gunakan kode berikut untuk menampilkan penghitung:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Petunjuk ini menunjukkan jumlah gaya dan daftar yang ada dalam dokumen sebelum dibersihkan.

## Langkah 4: Bersihkan gaya dan daftar yang tidak digunakan

Sekarang mari kita bersihkan gaya dan daftar yang tidak digunakan dari dokumen. Gunakan kode berikut untuk melakukan pembersihan:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Kode ini membersihkan gaya dan daftar yang tidak digunakan dari dokumen menggunakan opsi yang ditentukan. Dalam contoh ini, kami mengaktifkan`UnusedStyles` opsi untuk menghapus gaya yang tidak digunakan dan menonaktifkannya`UnusedLists` pilihan untuk menyimpan daftar meskipun tidak digunakan.

## Langkah 5: Hitung gaya dan daftar setelah dibersihkan

Setelah melakukan pembersihan, kami akan menghitung lagi gaya dan daftar untuk memeriksa apakah sudah diciutkan. Gunakan kode berikut untuk menampilkan penghitung baru:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Petunjuk ini menunjukkan jumlah gaya dan daftar yang tersisa setelah pembersihan.

### Contoh kode sumber untuk Membersihkan Gaya dan Daftar yang Tidak Digunakan menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Dikombinasikan dengan gaya bawaan, dokumen kini memiliki delapan gaya.
	// Gaya khusus ditandai sebagai "bekas" saat ada teks apa pun di dalam dokumen
	// diformat dalam gaya itu. Artinya 4 gaya yang kami tambahkan saat ini tidak digunakan.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Membersihkan gaya dan daftar yang tidak digunakan dari dokumen bergantung pada CleanupOptions yang diberikan.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara membersihkan gaya dan daftar yang tidak digunakan dari dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menerapkan fitur ini ke dokumen Anda sendiri.

