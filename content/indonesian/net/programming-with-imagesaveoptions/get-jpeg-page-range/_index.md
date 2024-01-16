---
title: Dapatkan Rentang Halaman JPEG
linktitle: Dapatkan Rentang Halaman JPEG
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendapatkan berbagai halaman JPEG dengan Aspose.Words untuk .NET. Tutorial lengkap untuk mengekstrak gambar khusus.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk fitur "Dapatkan Rentang Halaman JPEG" dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengonversi rentang halaman tertentu dari suatu dokumen menjadi gambar dalam format JPEG.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Pada langkah ini, kami mengonfigurasi opsi cadangan untuk gambar. Kami membuat yang baru`ImageSaveOptions` objek menentukan format penyimpanan yang diinginkan, di sini "Jpeg" untuk format JPEG. Kami juga mengatur rentang halaman yang akan dikonversi menggunakan`PageSet`obyek. Terakhir, kami mengatur kecerahan dan kontras gambar menggunakan`ImageBrightness` Dan`ImageContrast` properti, masing-masing. Kami juga mengubah resolusi horizontal menggunakan`HorizontalResolution` Properti.

## Langkah 4: Mencadangkan gambar

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Pada langkah terakhir ini, kami menyimpan gambar dari rentang halaman yang ditentukan dalam format JPEG menggunakan`Save` metode dan meneruskan jalur ke file keluaran, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk mengonversi rentang halaman tertentu di dokumen Anda menjadi gambar JPEG. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Contoh kode sumber untuk Mendapatkan Jpeg Page Range menggunakan Aspose.Words For .NET

```csharp 
 // Jalur ke direktori dokumen Anda
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Setel "PageSet" ke "0" untuk mengonversi hanya halaman pertama dokumen.
options.PageSet = new PageSet(0);

// Ubah kecerahan dan kontras gambar.
// Keduanya berada pada skala 0-1 dan 0,5 secara default.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Ubah resolusi horizontal.
// Nilai default untuk properti ini adalah 96,0, untuk resolusi 96dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Kesimpulan

Dalam tutorial ini, kami menjelajahi fungsionalitas mendapatkan rentang halaman JPEG dengan Aspose.Words untuk .NET. Kami mempelajari cara mengonversi rentang halaman tertentu dalam dokumen menjadi gambar dalam format JPEG, sambil menyesuaikan opsi penyimpanan.

Fitur ini berguna ketika Anda ingin mengekstrak halaman tertentu dari dokumen dan menyimpannya sebagai gambar JPEG. Anda juga dapat menyesuaikan kecerahan, kontras, dan resolusi horizontal gambar untuk mendapatkan hasil yang dipersonalisasi.

Aspose.Words untuk .NET menawarkan beragam fitur canggih untuk manipulasi dan pembuatan dokumen. Mendapatkan rentang halaman JPEG adalah salah satu dari banyak alat canggih yang dapat Anda gunakan.

Jangan ragu untuk mengintegrasikan fitur ini ke proyek Aspose.Words for .NET Anda untuk mendapatkan gambar JPEG berkualitas tinggi dari dokumen Anda.