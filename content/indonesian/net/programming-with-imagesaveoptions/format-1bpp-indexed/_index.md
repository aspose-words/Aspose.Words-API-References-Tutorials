---
title: Format 1Bpp Terindeks
linktitle: Format 1Bpp Terindeks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memformat gambar dalam 1 bpp yang diindeks dengan Aspose.Words untuk .NET. Tutorial lengkap untuk gambar dengan kedalaman warna rendah.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk fungsionalitas "Format 1Bpp Indexed" dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda memformat gambar dalam dokumen dalam format PNG dengan kedalaman warna 1 bit per piksel (1 bpp) dan mode warna terindeks.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file DOCX untuk dimuat.

## Langkah 3: Konfigurasikan opsi cadangan gambar

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Pada langkah ini, kami mengonfigurasi opsi cadangan untuk gambar. Kami membuat yang baru`ImageSaveOptions`objek menentukan format penyimpanan yang diinginkan, di sini "Png" untuk format PNG. Kami juga menentukan halaman yang akan disertakan dalam gambar, mode warna hitam putih dan format piksel 1 bpp yang diindeks.

## Langkah 4: Mencadangkan gambar

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Pada langkah terakhir ini, kita menyimpan gambar dokumen dalam format PNG menggunakan`Save` metode dan meneruskan jalur ke file keluaran, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk memformat gambar dokumen dalam format PNG dengan kedalaman warna terindeks 1 bpp. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Contoh kode sumber untuk Format 1Bpp Terindeks menggunakan Aspose.Words untuk .NET

```csharp 
 
			 // Jalur ke direktori dokumen Anda
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur format Terindeks 1Bpp dengan Aspose.Words untuk .NET. Kami mempelajari cara memformat gambar dalam dokumen dalam format PNG dengan kedalaman warna 1 bit per piksel (1 bpp) dan mode warna terindeks.

Fitur ini berguna ketika Anda ingin mendapatkan gambar dengan kedalaman warna rendah dan ukuran file kecil. Format Terindeks 1Bpp memungkinkan gambar direpresentasikan menggunakan palet warna yang diindeks, yang dapat bermanfaat untuk beberapa aplikasi tertentu.

Aspose.Words untuk .NET menawarkan berbagai fitur canggih untuk manipulasi dan pembuatan dokumen. Format Terindeks 1Bpp adalah salah satu dari banyak alat canggih yang dapat Anda gunakan.