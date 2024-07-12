---
title: Format Angka Untuk Sumbu Dalam Bagan
linktitle: Format Angka Untuk Sumbu Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memformat nomor sumbu bagan menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Tingkatkan keterbacaan dan profesionalisme dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-charts/number-format-for-axis/
---
## Perkenalan

Hai! Pernahkah Anda bekerja dengan bagan di dokumen Anda dan berharap dapat memformat angka pada sumbu Anda agar terlihat lebih profesional? Nah, Anda beruntung! Dalam tutorial ini, kita akan mendalami bagaimana Anda dapat mencapai hal tersebut menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memungkinkan Anda menangani dokumen Word dengan cara yang sangat mudah. Dan hari ini, kami berfokus untuk memberikan perubahan pada sumbu grafik tersebut dengan format angka khusus.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda butuhkan. Berikut daftar periksa singkatnya:

-  Aspose.Words untuk .NET: Pastikan Anda telah menginstalnya. Jika tidak, Anda bisa[Unduh di sini](https://releases.aspose.com/words/net/).
- .NET Framework: Pastikan Anda telah menginstal kerangka .NET yang kompatibel.
- Lingkungan Pengembangan: IDE seperti Visual Studio akan bekerja dengan sempurna.
- Pengetahuan Dasar C#: Ini akan membantu Anda mengikuti contoh pengkodean.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Ini seperti meletakkan pondasi sebelum membangun sebuah rumah. Tambahkan arahan penggunaan berikut di bagian atas file kode Anda:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah diikuti.

## Langkah 1: Menyiapkan Dokumen

Judul: Inisialisasi Dokumen Anda

Pertama, Anda perlu membuat dokumen baru dan pembuat dokumen. Anggaplah langkah ini sebagai menyiapkan kanvas dan kuas sebelum memulai karya Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di Sini,`dataDir` adalah jalur ke direktori dokumen tempat Anda akan menyimpan file akhir.`Document`Dan`DocumentBuilder` adalah kelas dari Aspose.Words yang membantu Anda membuat dan memanipulasi dokumen Word.

## Langkah 2: Memasukkan Bagan

Judul: Tambahkan Bagan ke Dokumen Anda

Selanjutnya, mari tambahkan bagan ke dokumen Anda. Di sinilah keajaiban dimulai. Kita akan menyisipkan bagan kolom yang akan bertindak sebagai kanvas kosong.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 Itu`InsertChart` metode menyisipkan bagan dengan tipe tertentu (Kolom dalam hal ini) dan dimensi ke dalam dokumen.

## Langkah 3: Menyesuaikan Seri Bagan

Judul: Isi Bagan Anda dengan Data

Sekarang, kita perlu menambahkan beberapa data ke grafik kita. Langkah ini mirip dengan mengisi bagan Anda dengan informasi yang bermakna.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 Di sini, kami menambahkan seri baru yang disebut "Aspose Series 1" dengan lima titik data. Itu`Series.Clear` metode ini memastikan semua data yang sudah ada sebelumnya dihapus sebelum menambahkan seri baru kami.

## Langkah 4: Memformat Nomor Sumbu

Judul: Mempercantik Angka Sumbu Anda

Terakhir, mari kita format angka pada sumbu Y agar lebih mudah dibaca. Ini seperti memberikan sentuhan akhir pada karya seni Anda.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

 Itu`FormatCode` properti memungkinkan Anda mengatur format khusus untuk angka-angka pada sumbu. Dalam contoh ini,`#,##0`memastikan bahwa angka besar ditampilkan dengan koma untuk ribuan.

## Langkah 5: Menyimpan Dokumen

Judul: Simpan Karya Anda

Sekarang semuanya sudah siap, saatnya menyimpan dokumen Anda. Langkah ini adalah pengungkapan besar karya Anda.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 Di sini, itu`Save` metode menyimpan dokumen ke jalur yang ditentukan dengan nama file`WorkingWithCharts.NumberFormatForAxis.docx`.

## Kesimpulan

Dan itu dia! Anda telah berhasil memformat angka pada sumbu Y bagan Anda menggunakan Aspose.Words untuk .NET. Hal ini tidak hanya membuat grafik Anda terlihat lebih profesional tetapi juga meningkatkan keterbacaan. Aspose.Words menawarkan banyak fitur yang dapat membantu Anda membuat dokumen Word yang menakjubkan secara terprogram. Jadi mengapa tidak menjelajah lebih jauh dan melihat apa lagi yang bisa Anda lakukan?

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi dokumen Word secara terprogram.

### Bisakah saya memformat aspek lain pada bagan selain nomor sumbu?
Sangat! Aspose.Words untuk .NET memungkinkan Anda memformat judul, label, dan bahkan menyesuaikan tampilan bagan.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda bisa mendapatkan[uji coba gratis di sini](https://releases.aspose.com/).

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa .NET lain selain C#?
Ya, Aspose.Words untuk .NET kompatibel dengan bahasa .NET apa pun, termasuk VB.NET dan F#.

### Di mana saya dapat menemukan dokumentasi yang lebih detail?
 Dokumentasi terperinci tersedia di[Halaman dokumentasi Aspose.Words untuk .NET](https://reference.aspose.com/words/net/).
