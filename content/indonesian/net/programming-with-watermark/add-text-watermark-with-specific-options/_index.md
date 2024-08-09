---
title: Tambahkan Tanda Air Teks Dengan Opsi Tertentu
linktitle: Tambahkan Tanda Air Teks Dengan Opsi Tertentu
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan tanda air teks dengan opsi spesifik ke dokumen Word Anda menggunakan Aspose.Words untuk .NET. Sesuaikan font, ukuran, warna, dan tata letak dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## Perkenalan

Tanda air dapat menjadi tambahan gaya dan fungsional pada dokumen Word Anda, yang berfungsi mulai dari menandai dokumen sebagai rahasia hingga menambahkan sentuhan pribadi. Dalam tutorial ini, kita akan mempelajari cara menambahkan tanda air teks ke dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mendalami opsi spesifik yang dapat Anda konfigurasi, seperti jenis font, ukuran font, warna, dan tata letak. Pada akhirnya, Anda akan dapat menyesuaikan tanda air dokumen agar sesuai dengan kebutuhan Anda. Jadi, ambil editor kode Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET Library: Anda perlu menginstal perpustakaan Aspose.Words. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Tautan Unduhan Aspose.Words](https://releases.aspose.com/words/net/).
2. Pemahaman Dasar C#: Tutorial ini akan menggunakan C# sebagai bahasa pemrogramannya. Pemahaman mendasar tentang sintaksis C# akan sangat membantu.
3. Lingkungan Pengembangan .NET: Pastikan Anda telah menyiapkan lingkungan pengembangan (seperti Visual Studio) tempat Anda dapat membuat dan menjalankan aplikasi .NET.

## Impor Namespace

Untuk bekerja dengan Aspose.Words, Anda harus menyertakan namespace yang diperlukan dalam proyek Anda. Inilah yang perlu Anda impor:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Langkah 1: Siapkan Dokumen Anda

 Pertama, Anda perlu memuat dokumen yang ingin Anda kerjakan. Untuk tutorial ini, kita akan menggunakan contoh dokumen bernama`Document.docx`. Pastikan dokumen ini ada di direktori yang Anda tentukan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Pada langkah ini, Anda menentukan direktori tempat dokumen Anda berada dan memuatnya ke dalam instance`Document` kelas.

## Langkah 2: Konfigurasikan Opsi Tanda Air

Selanjutnya, konfigurasikan opsi untuk tanda air teks Anda. Anda dapat menyesuaikan berbagai aspek, seperti jenis font, ukuran font, warna, dan tata letak. Mari siapkan opsi ini.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Inilah yang dilakukan setiap opsi:
- `FontFamily`: Menentukan font teks tanda air.
- `FontSize`: Menyetel ukuran teks tanda air.
- `Color`: Mendefinisikan warna teks tanda air.
- `Layout`Menentukan orientasi watermark (horizontal atau diagonal).
- `IsSemitrasparent`: Menyetel apakah tanda air bersifat semi-transparan.

## Langkah 3: Tambahkan Teks Tanda Air

Sekarang, terapkan tanda air ke dokumen Anda menggunakan opsi yang telah dikonfigurasi sebelumnya. Pada langkah ini, Anda akan menyetel teks tanda air ke "Tes" dan menerapkan opsi yang Anda tentukan.

```csharp
doc.Watermark.SetText("Test", options);
```

Baris kode ini menambahkan tanda air dengan teks "Tes" ke dokumen, menerapkan opsi yang ditentukan.

## Langkah 4: Simpan Dokumen

Terakhir, simpan dokumen dengan tanda air baru yang diterapkan. Anda dapat menyimpannya dengan nama baru untuk menghindari penimpaan dokumen asli.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Cuplikan kode ini menyimpan dokumen yang dimodifikasi di direktori yang sama dengan nama file baru.

## Kesimpulan

Menambahkan tanda air teks ke dokumen Word Anda menggunakan Aspose.Words untuk .NET adalah proses yang mudah saat Anda membaginya menjadi beberapa langkah yang dapat dikelola. Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengonfigurasi berbagai opsi tanda air, termasuk font, ukuran, warna, tata letak, dan transparansi. Dengan keterampilan ini, kini Anda dapat menyesuaikan dokumen agar lebih memenuhi kebutuhan Anda atau untuk menyertakan informasi penting seperti kerahasiaan atau branding.

 Jika Anda memiliki pertanyaan atau memerlukan bantuan lebih lanjut, silakan lihat[Dokumentasi Aspose.Words](https://reference.aspose.com/words/net/) atau kunjungi[Asumsikan Forum Dukungan](https://forum.aspose.com/c/words/8) untuk bantuan lebih lanjut.

## FAQ

### Bisakah saya menggunakan font berbeda untuk tanda air?

 Ya, Anda dapat memilih font apa pun yang diinstal pada sistem Anda dengan menentukan`FontFamily` properti di`TextWatermarkOptions`.

### Bagaimana cara mengubah warna tanda air?

 Anda dapat mengubah warna tanda air dengan mengatur`Color` properti di`TextWatermarkOptions` untuk siapa pun`System.Drawing.Color` nilai.

### Apakah mungkin menambahkan banyak tanda air ke dokumen?

Aspose.Words mendukung penambahan satu tanda air dalam satu waktu. Untuk menambahkan beberapa tanda air, Anda perlu membuat dan menerapkannya secara berurutan.

### Bisakah saya mengatur posisi tanda air?

 Itu`WatermarkLayout`properti menentukan orientasi, namun penyesuaian posisi yang tepat tidak didukung secara langsung. Anda mungkin perlu menggunakan teknik lain untuk penempatan yang tepat.

### Bagaimana jika saya memerlukan tanda air semi transparan?

 Atur`IsSemitrasparent`properti ke`true` untuk membuat tanda air Anda semi-transparan.