---
title: Dapatkan Rentang Halaman JPEG
linktitle: Dapatkan Rentang Halaman JPEG
second_title: API Pemrosesan Dokumen Aspose.Words
description: Konversikan halaman tertentu dokumen Word ke JPEG dengan pengaturan khusus menggunakan Aspose.Words untuk .NET. Pelajari cara menyesuaikan kecerahan, kontras, dan resolusi langkah demi langkah.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## Perkenalan

Mengonversi dokumen Word menjadi gambar bisa sangat berguna, baik Anda membuat thumbnail, melihat pratinjau dokumen secara online, atau berbagi konten dalam format yang lebih mudah diakses. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengonversi halaman tertentu dokumen Word Anda ke format JPEG sambil menyesuaikan berbagai pengaturan seperti kecerahan, kontras, dan resolusi. Mari selami cara mencapainya selangkah demi selangkah!

## Prasyarat

Sebelum kita mulai, Anda memerlukan beberapa hal:

-  Aspose.Words for .NET: Pastikan Anda telah menginstal Aspose.Words for .NET. Kamu bisa[Unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Lingkungan pengembangan AC# seperti Visual Studio.
- Contoh Dokumen: Dokumen Word untuk dikerjakan. Anda dapat menggunakan file .docx apa pun untuk tutorial ini.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C#.

Setelah Anda menyiapkannya, mari kita mulai!

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET, Anda harus mengimpor namespace yang diperlukan di awal kode Anda. Hal ini memastikan Anda memiliki akses ke semua kelas dan metode yang diperlukan untuk manipulasi dokumen.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Muat Dokumen Anda

Pertama, kita perlu memuat dokumen Word yang ingin kita konversi. Anggaplah dokumen kita diberi nama`Rendering.docx` dan terletak di direktori yang ditentukan oleh placeholder`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Kode ini menginisialisasi jalur ke dokumen Anda dan memuatnya ke dalam Aspose.Words`Document` obyek.

## Langkah 2: Siapkan ImageSaveOptions

 Selanjutnya, kita akan menyiapkan`ImageSaveOptions` untuk menentukan bagaimana kita ingin JPEG kita dihasilkan. Ini termasuk mengatur rentang halaman, kecerahan gambar, kontras, dan resolusi.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // Konversi hanya halaman pertama
options.ImageBrightness = 0.3f;   // Atur kecerahan
options.ImageContrast = 0.7f;     // Tetapkan kontras
options.HorizontalResolution = 72f; // Tetapkan resolusi
```

## Langkah 3: Simpan Dokumen sebagai JPEG

Terakhir, kami menyimpan dokumen sebagai file JPEG menggunakan pengaturan yang telah kami tentukan.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Kode ini menyimpan halaman pertama`Rendering.docx` sebagai gambar JPEG dengan pengaturan kecerahan, kontras, dan resolusi yang ditentukan.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengonversi halaman tertentu dari dokumen Word menjadi gambar JPEG dengan pengaturan yang disesuaikan menggunakan Aspose.Words untuk .NET. Proses ini dapat disesuaikan untuk memenuhi berbagai kebutuhan, baik Anda menyiapkan gambar untuk situs web, membuat pratinjau dokumen, atau lainnya.

## FAQ

### Bisakah saya mengonversi beberapa halaman sekaligus?
 Ya, Anda dapat menentukan rentang halaman menggunakan`PageSet` properti di`ImageSaveOptions`.

### Bagaimana cara menyesuaikan kualitas gambar?
 Anda dapat mengatur kualitas JPEG dengan menggunakan`JpegQuality` properti di`ImageSaveOptions`.

### Bisakah saya menyimpan dalam format gambar lain?
 Ya, Aspose.Words mendukung berbagai format gambar seperti PNG, BMP, dan TIFF. Mengubah`SaveFormat` di dalam`ImageSaveOptions` demikian.

### Apakah ada cara untuk melihat pratinjau gambar sebelum menyimpannya?
Anda perlu menerapkan mekanisme pratinjau secara terpisah, karena Aspose.Words tidak menyediakan fitur pratinjau bawaan.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words?
 Anda dapat meminta a[izin sementara di sini](https://purchase.aspose.com/temporary-license/).