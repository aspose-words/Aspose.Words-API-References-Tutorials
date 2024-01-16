---
title: Hapus Informasi Pribadi
linktitle: Hapus Informasi Pribadi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menghapus informasi pribadi dari dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/remove-personal-information/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menghapus informasi pribadi dari dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menghapus informasi pribadi sensitif dari dokumen, seperti data identifikasi penulis.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kami akan mengunggah dokumen Word yang informasi pribadinya ingin kami hapus. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Hapus informasi pribadi

 Sekarang kami akan mengaktifkan penghapusan informasi pribadi dengan mengatur`RemovePersonalInformation`properti ke`true`. Gunakan kode berikut:

```csharp
doc.RemovePersonalInformation = true;
```

Kode ini mengaktifkan penghapusan informasi pribadi dalam dokumen.

## Langkah 4: Menyimpan dokumen

Terakhir, kami akan menyimpan dokumen dengan informasi pribadi yang dihapus. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Kode ini menyimpan dokumen dengan informasi pribadi yang dihapus ke file baru.

### Contoh kode sumber untuk Menghapus Informasi Pribadi menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara menghapus informasi pribadi dari dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menghapus informasi sensitif dari dokumen Anda sendiri.