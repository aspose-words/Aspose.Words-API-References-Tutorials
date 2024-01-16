---
title: Dapatkan Rentang Halaman Tiff
linktitle: Dapatkan Rentang Halaman Tiff
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekstrak berbagai halaman TIFF dengan Aspose.Words untuk .NET. Tutorial lengkap untuk file TIFF khusus.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk mendapatkan berbagai halaman TIFF dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengekstrak rentang halaman tertentu dari dokumen dan menyimpannya sebagai file TIFF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file DOCX untuk dimuat.

## Langkah 3: Menyimpan dokumen lengkap di TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

Pada langkah ini, kami menyimpan seluruh dokumen dalam format TIFF menggunakan`Save` metode dan menentukan jalur ke file keluaran dengan ekstensi`.tiff`.

## Langkah 4: Konfigurasikan opsi cadangan untuk rentang halaman

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Pada langkah ini, kami mengonfigurasi opsi cadangan untuk rentang halaman tertentu. Kami membuat yang baru`ImageSaveOptions` objek yang menentukan format penyimpanan yang diinginkan, di sini "Tiff" untuk format TIFF. Kita gunakan`PageSet` untuk menentukan rentang halaman yang ingin kita ekstrak, disini dari halaman 0 sampai halaman 1 (inklusif). Kami juga mengatur kompresi TIFF ke`Ccitt4` dan resolusi hingga 160 dpi.

## Langkah 5: Menyimpan rentang halaman ke TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Pada langkah terakhir ini, kami menyimpan rentang halaman yang ditentukan dalam format TIFF menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.tiff` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk mendapatkan rentang halaman tertentu dari dokumen Anda dan menyimpannya sebagai file TIFF. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithImageSaveOptions.MultipageTiff.tiff" untuk dokumen lengkap dan "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" untuk rentang halaman yang ditentukan.

### Contoh kode sumber Dapatkan Rentang Halaman Tiff menggunakan Aspose.Words untuk .NET

```csharp 

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fungsionalitas mendapatkan berbagai halaman TIFF dengan Aspose.Words untuk .NET. Kami mempelajari cara mengekstrak rentang halaman tertentu dari dokumen dan menyimpannya sebagai file TIFF.

Fitur ini berguna ketika Anda hanya ingin mengekstrak halaman tertentu dari suatu dokumen dan menyimpannya dalam format gambar standar seperti TIFF. Anda juga dapat menyesuaikan opsi kompresi dan resolusi untuk mendapatkan file TIFF kualitas terbaik.

Aspose.Words untuk .NET menawarkan beragam fitur canggih untuk manipulasi dan pembuatan dokumen. Mendapatkan rentang halaman TIFF adalah salah satu dari banyak alat canggih yang dapat Anda gunakan.

Jangan ragu untuk mengintegrasikan fungsi ini ke dalam proyek Aspose.Words for .NET Anda untuk mengekstrak dan menyimpan rentang halaman tertentu dari dokumen Anda dalam format TIFF.