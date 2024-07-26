---
title: Format 1Bpp Terindeks
linktitle: Format 1Bpp Terindeks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word menjadi gambar terindeks 1Bpp menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk konversi yang mudah.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Perkenalan

Pernah bertanya-tanya bagaimana cara menyimpan dokumen Word sebagai gambar hitam putih hanya dengan beberapa baris kode? Nah, Anda beruntung! Hari ini, kita akan mempelajari trik kecil yang menarik menggunakan Aspose.Words untuk .NET yang memungkinkan Anda mengonversi dokumen Anda menjadi gambar yang diindeks 1Bpp. Format ini cocok untuk jenis pengarsipan digital tertentu, pencetakan, atau saat Anda perlu menghemat ruang. Kami akan menguraikan setiap langkah untuk membuatnya semudah pie. Siap untuk memulai? Ayo selami!

## Prasyarat

Sebelum kita mengotori tangan kita, ada beberapa hal yang perlu Anda siapkan:

-  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan. Kamu bisa[Unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan .NET: Visual Studio adalah pilihan yang bagus, tetapi Anda dapat menggunakan lingkungan apa pun yang Anda sukai.
- Pengetahuan Dasar tentang C#: Jangan khawatir, kami akan membuatnya tetap sederhana, namun sedikit pemahaman tentang C# akan membantu.
- Dokumen Word: Siapkan contoh dokumen Word untuk dikonversi.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan. Ini penting karena memungkinkan kita mengakses kelas dan metode yang kita perlukan dari Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Anda harus menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda disimpan dan gambar yang dikonversi akan disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Word

 Sekarang, mari kita memuat dokumen Word ke dalam Aspose.Words`Document` obyek. Objek ini mewakili file Word Anda dan memungkinkan Anda memanipulasinya.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan Gambar

 Selanjutnya, kita perlu menyiapkan`ImageSaveOptions`Ini adalah dimana keajaiban terjadi. Kami akan mengkonfigurasinya untuk menyimpan gambar dalam format PNG dengan mode warna terindeks 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Ini menentukan bahwa kita ingin menyimpan dokumen sebagai gambar PNG.
- PageSet(1): Ini menunjukkan kita hanya mengonversi halaman pertama.
- ImageColorMode.BlackAndWhite: Ini mengatur gambar menjadi hitam putih.
- ImagePixelFormat.Format1bppIndexed: Ini mengatur format gambar ke indeks 1Bpp.

## Langkah 4: Simpan Dokumen sebagai Gambar

 Terakhir, kami menyimpan dokumen sebagai gambar menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda telah mengubah dokumen Word Anda menjadi gambar terindeks 1Bpp menggunakan Aspose.Words untuk .NET. Metode ini sangat berguna untuk membuat gambar dengan kontras tinggi dan hemat ruang dari dokumen Anda. Sekarang, Anda dapat dengan mudah mengintegrasikannya ke dalam proyek dan alur kerja Anda. Selamat membuat kode!

## FAQ

### Apa itu gambar yang diindeks 1Bpp?
Gambar berindeks 1Bpp (1 Bit Per Piksel) adalah format gambar hitam putih yang setiap pikselnya diwakili oleh satu bit, baik 0 atau 1. Format ini sangat hemat ruang.

### Bisakah saya mengonversi beberapa halaman dokumen Word sekaligus?
 Ya kamu bisa. Ubah`PageSet` properti di`ImageSaveOptions` untuk menyertakan beberapa halaman atau seluruh dokumen.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?
 Ya, Aspose.Words untuk .NET memerlukan lisensi untuk fungsionalitas penuh. Anda bisa mendapatkan[izin sementara di sini](https://purchase.aspose.com/temporary-license/).

### Format gambar apa lagi yang dapat saya konversi ke dokumen Word saya?
 Aspose.Words mendukung berbagai format gambar termasuk JPEG, BMP, dan TIFF. Cukup ubah`SaveFormat` dalam`ImageSaveOptions`.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi terperinci di[Halaman dokumentasi Aspose.Words untuk .NET](https://reference.aspose.com/words/net/).
