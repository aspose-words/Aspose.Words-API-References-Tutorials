---
title: Atur Folder Gambar
linktitle: Atur Folder Gambar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder gambar saat mengekspor ke Markdown dengan Aspose.Words untuk .NET. Sesuaikan penempatan gambar untuk pengorganisasian dan integrasi yang lebih baik.
type: docs
weight: 10
url: /id/net/programming-with-markdownsaveoptions/set-images-folder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut yang membantu mengatur folder gambar untuk opsi ekspor penurunan harga menggunakan perpustakaan Aspose.Words untuk .NET. Pastikan Anda telah menyertakan perpustakaan Aspose.Words di proyek Anda sebelum menggunakan kode ini.

## Langkah 1: Tetapkan jalur direktori dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda tempat dokumen yang berisi gambar berada.

## Langkah 2: Muat dokumen yang berisi gambar

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Kami memuat dokumen tertentu yang berisi gambar yang ingin kami ekspor dengan opsi penurunan harga.

## Langkah 3: Atur folder gambar untuk opsi ekspor penurunan harga

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Kami membuat sebuah instance dari`MarkdownSaveOptions` dan atur jalur ke folder gambar menggunakan`ImagesFolder` Properti. Pastikan untuk menentukan jalur yang benar ke folder tempat Anda ingin menyimpan gambar yang diekspor.

## Langkah 4: Simpan dokumen dengan opsi ekspor penurunan harga

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Kami menyimpan dokumen ke aliran memori menggunakan opsi ekspor penurunan harga yang ditentukan. Anda kemudian dapat menggunakan alur untuk melakukan operasi lain, seperti menyimpan konten penurunan harga ke file.

### Contoh kode sumber untuk mengatur folder gambar untuk MarkdownSaveOptions dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Kode sumber ini menunjukkan cara memuat dokumen yang berisi gambar dan kemudian mengatur folder gambar untuk opsi ekspor penurunan harga. Dengan menggunakan opsi yang ditentukan, dokumen tersebut kemudian disimpan ke aliran memori. Ini memungkinkan Anda untuk menyesuaikan lokasi folder gambar saat mengekspor konten penurunan harga.