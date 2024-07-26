---
title: Panggilan Balik Penghematan Halaman
linktitle: Panggilan Balik Penghematan Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyimpan setiap halaman dokumen Word sebagai gambar PNG terpisah menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami yang terperinci.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/page-saving-callback/
---
## Perkenalan

Hai! Pernah merasa perlu menyimpan setiap halaman dokumen Word sebagai gambar terpisah? Mungkin Anda ingin memecah laporan besar menjadi visual yang mudah dicerna, atau mungkin Anda perlu membuat thumbnail untuk pratinjau. Apa pun alasan Anda, menggunakan Aspose.Words untuk .NET membuat tugas ini menjadi mudah. Dalam panduan ini, kami akan memandu Anda melalui proses menyiapkan panggilan balik penyimpanan halaman untuk menyimpan setiap halaman dokumen sebagai gambar PNG individual. Mari selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduh dan instal dari[Di Sini](https://releases.aspose.com/words/net/).
2. Visual Studio: Versi apa pun akan berfungsi, tetapi saya akan menggunakan Visual Studio 2019 untuk panduan ini.
3. Pengetahuan Dasar tentang C#: Anda memerlukan pemahaman dasar tentang C# untuk mengikutinya.

## Impor Namespace

Pertama, kita perlu mengimpor namespace yang diperlukan. Ini membantu kita mengakses kelas dan metode yang diperlukan tanpa harus mengetikkan namespace lengkap setiap saat.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Baiklah, mari kita mulai dengan menentukan jalur ke direktori dokumen Anda. Di sinilah letak dokumen Word masukan Anda dan tempat gambar keluaran akan disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Anda

Selanjutnya, kami akan memuat dokumen yang ingin Anda proses. Pastikan dokumen Anda ("Rendering.docx") berada di direktori yang ditentukan.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan Gambar

Kita perlu mengkonfigurasi opsi untuk menyimpan gambar. Dalam hal ini, kami menyimpan halaman sebagai file PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Di Sini,`PageSet` menentukan rentang halaman yang akan disimpan, dan`PageSavingCallback` menunjuk ke kelas panggilan balik khusus kami.

## Langkah 4: Terapkan Panggilan Balik Penyimpanan Halaman

Sekarang, mari kita terapkan kelas callback yang menangani cara setiap halaman disimpan.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Kelas ini mengimplementasikan`IPageSavingCallback` antarmuka, dan di dalam`PageSaving` metode, kami menentukan pola penamaan untuk setiap halaman yang disimpan.

## Langkah 5: Simpan Dokumen sebagai Gambar

Terakhir, kami menyimpan dokumen menggunakan opsi yang dikonfigurasi.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil menyiapkan panggilan balik penyimpanan halaman untuk menyimpan setiap halaman dokumen Word sebagai gambar PNG terpisah menggunakan Aspose.Words untuk .NET. Teknik ini sangat berguna untuk berbagai aplikasi, mulai dari membuat pratinjau halaman hingga menghasilkan gambar halaman individual untuk laporan. 

Selamat membuat kode!

## FAQ

### Bisakah saya menyimpan halaman dalam format selain PNG?  
 Ya, Anda dapat menyimpan halaman dalam format berbeda seperti JPEG, BMP, dan TIFF dengan mengubah`SaveFormat` di dalam`ImageSaveOptions`.

### Bagaimana jika saya hanya ingin menyimpan halaman tertentu?  
 Anda dapat menentukan halaman yang ingin Anda simpan dengan menyesuaikan`PageSet` parameter di`ImageSaveOptions`.

### Apakah mungkin untuk menyesuaikan kualitas gambar?  
 Sangat! Anda dapat mengatur properti seperti`ImageSaveOptions.JpegQuality` untuk mengontrol kualitas gambar keluaran.

### Bagaimana cara menangani dokumen berukuran besar secara efisien?  
Untuk dokumen berukuran besar, pertimbangkan untuk memproses halaman secara batch untuk mengelola penggunaan memori secara efektif.

### Di mana saya dapat menemukan informasi selengkapnya tentang Aspose.Words untuk .NET?  
 Lihat[dokumentasi](https://reference.aspose.com/words/net/) untuk panduan dan contoh yang komprehensif.