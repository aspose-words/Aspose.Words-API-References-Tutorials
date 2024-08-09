---
title: Sesuaikan Label Data Bagan
linktitle: Sesuaikan Label Data Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkustomisasi label data bagan menggunakan Aspose.Words untuk .NET dalam panduan langkah demi langkah. Sempurna untuk pengembang .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/chart-data-label/
---
## Perkenalan

Apakah Anda ingin menyempurnakan aplikasi .NET Anda dengan kemampuan pemrosesan dokumen yang dinamis dan disesuaikan? Aspose.Words untuk .NET mungkin bisa menjadi jawaban Anda! Dalam panduan ini, kita akan mendalami penyesuaian label data bagan menggunakan Aspose.Words untuk .NET, pustaka canggih untuk membuat, memodifikasi, dan mengonversi dokumen Word. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan memandu Anda melalui setiap langkah, memastikan Anda memahami cara menggunakan alat ini secara efektif.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Instal Visual Studio 2019 atau lebih baru.
2. .NET Framework: Pastikan Anda memiliki .NET Framework 4.0 atau lebih baru.
3.  Aspose.Words for .NET: Unduh dan instal Aspose.Words for .NET dari[tautan unduhan](https://releases.aspose.com/words/net/).
4. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# sangat penting.
5.  Lisensi yang Sah: Dapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) atau beli satu dari[tautan beli](https://purchase.aspose.com/buy).

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Langkah ini penting karena memastikan bahwa Anda memiliki akses ke semua kelas dan metode yang disediakan oleh Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

Untuk membuat dan memanipulasi dokumen Word, pertama-tama kita perlu menginisialisasi sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Penjelasan

- Dokumen dokumen: Membuat instance baru dari kelas Dokumen.
- Pembuat DocumentBuilder: DocumentBuilder membantu memasukkan konten ke dalam objek Dokumen.

## Langkah 2: Sisipkan Bagan

 Selanjutnya, kita akan menyisipkan diagram batang ke dalam dokumen menggunakan`DocumentBuilder` obyek.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### Penjelasan

- Bentuk bentuk: Mewakili bagan sebagai bentuk dalam dokumen.
- builder.InsertChart(ChartType.Bar, 432, 252): Menyisipkan diagram batang dengan dimensi tertentu.

## Langkah 3: Akses Seri Bagan

Untuk menyesuaikan label data, pertama-tama kita perlu mengakses rangkaian di bagan.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### Penjelasan

- ChartSeries series0: Mengambil rangkaian grafik pertama, yang akan kita sesuaikan.

## Langkah 4: Sesuaikan Label Data

Label data dapat disesuaikan untuk menampilkan berbagai informasi. Kami akan mengonfigurasi label untuk menampilkan kunci legenda, nama seri, dan nilai, sekaligus menyembunyikan nama kategori dan persentase.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### Penjelasan

- Label ChartDataLabelCollection: Mengakses label data rangkaian.
- labels.ShowLegendKey: Menampilkan kunci legenda.
- labels.ShowLeaderLines: Menampilkan garis pemimpin untuk label data yang diposisikan jauh di luar titik data.
- labels.ShowCategoryName: Menyembunyikan nama kategori.
- labels.ShowPercentage: Menyembunyikan nilai persentase.
- labels.ShowSeriesName: Menampilkan nama seri.
- labels.ShowValue: Menampilkan nilai titik data.
- labels.Separator: Mengatur pemisah untuk label data.

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Penjelasan

- doc.Save: Menyimpan dokumen dengan nama tertentu di direktori yang disediakan.

## Kesimpulan

 Selamat! Anda telah berhasil mengkustomisasi label data bagan menggunakan Aspose.Words untuk .NET. Pustaka ini menawarkan solusi tangguh untuk menangani dokumen Word secara terprogram, sehingga memudahkan pengembang untuk membuat aplikasi pemrosesan dokumen yang canggih dan dinamis. Menyelam ke dalam[dokumentasi](https://reference.aspose.com/words/net/) untuk menjelajahi lebih banyak fitur dan kemampuan.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi dokumen Word secara terprogram.

### Bagaimana cara menginstal Aspose.Words untuk .NET?
 Anda dapat mengunduh dan menginstalnya dari[tautan unduhan](https://releases.aspose.com/words/net/). Ikuti petunjuk instalasi yang disediakan.

### Bisakah saya mencoba Aspose.Words untuk .NET secara gratis?
 Ya, Anda bisa mendapatkan[uji coba gratis](https://releases.aspose.com/) atau a[izin sementara](https://purchase.aspose.com/temporary-license/)untuk mengevaluasi produk.

### Apakah Aspose.Words untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.Words untuk .NET kompatibel dengan .NET Core, .NET Standard, dan .NET Framework.

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Words untuk .NET?
 Anda dapat mengunjungi[forum dukungan](https://forum.aspose.com/c/words/8) atas bantuan dan bantuan dari komunitas Aspose dan para ahli.
