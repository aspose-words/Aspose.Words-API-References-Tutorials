---
title: Tambahkan Nilai Tanggal Waktu Ke Sumbu Bagan
linktitle: Tambahkan Nilai Tanggal Waktu Ke Sumbu Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan nilai tanggal dan waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET dalam panduan langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/programming-with-charts/date-time-values-to-axis/
---
## Perkenalan

Membuat bagan dalam dokumen bisa menjadi cara ampuh untuk memvisualisasikan data. Saat menangani data deret waktu, menambahkan nilai tanggal dan waktu ke sumbu bagan sangat penting untuk kejelasan. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan nilai tanggal dan waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini akan membantu Anda menyiapkan lingkungan, menulis kode, dan memahami setiap bagian proses. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio atau .NET IDE apa pun: Anda memerlukan lingkungan pengembangan untuk menulis dan menjalankan kode .NET Anda.
2.  Aspose.Words untuk .NET: Anda harus menginstal perpustakaan Aspose.Words untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
3. Pengetahuan dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.
4.  Lisensi Aspose yang valid: Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).

## Impor Namespace

Untuk memulai, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda. Langkah ini penting untuk mengakses kelas dan metode Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, Anda perlu menentukan direktori tempat dokumen Anda akan disimpan. Ini penting untuk mengatur file Anda dan memastikan kode Anda berjalan dengan benar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder

 Selanjutnya, buat instance baru dari`Document` kelas dan a`DocumentBuilder` obyek. Objek-objek ini akan membantu Anda membangun dan memanipulasi dokumen Anda.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Masukkan Bagan ke dalam Dokumen

 Sekarang, masukkan bagan ke dalam dokumen Anda menggunakan`DocumentBuilder` obyek. Dalam contoh ini, kami menggunakan bagan kolom, namun Anda juga dapat memilih tipe lainnya.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 4: Hapus Seri yang Ada

Hapus semua rangkaian yang ada di bagan untuk memastikan Anda memulai dengan lembaran kosong. Langkah ini penting untuk data khusus.

```csharp
chart.Series.Clear();
```

## Langkah 5: Tambahkan Nilai Tanggal dan Waktu ke Seri

Tambahkan nilai tanggal dan waktu Anda ke rangkaian bagan. Langkah ini melibatkan pembuatan array untuk tanggal dan nilai terkait.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Langkah 6: Konfigurasikan Sumbu X

Atur skala dan tanda centang untuk sumbu X. Ini memastikan tanggal Anda ditampilkan dengan benar dan pada interval yang sesuai.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Langkah 7: Simpan Dokumen

Terakhir, simpan dokumen Anda ke direktori yang ditentukan. Langkah ini mengakhiri prosesnya, dan dokumen Anda sekarang harus berisi bagan dengan nilai tanggal dan waktu pada sumbu X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Kesimpulan

Menambahkan nilai tanggal dan waktu ke sumbu bagan dalam dokumen adalah proses yang mudah dengan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat membuat bagan yang jelas dan informatif yang secara efektif memvisualisasikan data deret waktu. Baik Anda menyiapkan laporan, presentasi, atau dokumen apa pun yang memerlukan representasi data terperinci, Aspose.Words menyediakan alat yang Anda butuhkan untuk berhasil.

## FAQ

### Bisakah saya menggunakan tipe bagan lain dengan Aspose.Words untuk .NET?

Ya, Aspose.Words mendukung berbagai jenis bagan, termasuk garis, batang, pai, dan lainnya.

### Bagaimana cara menyesuaikan tampilan bagan saya?

Anda dapat menyesuaikan tampilan dengan mengakses properti bagan dan mengatur gaya, warna, dan lainnya.

### Apakah mungkin menambahkan beberapa rangkaian ke bagan?

 Sangat! Anda dapat menambahkan beberapa rangkaian ke bagan Anda dengan memanggil`Series.Add` metode beberapa kali dengan data yang berbeda.

### Bagaimana jika saya perlu memperbarui data grafik secara dinamis?

Anda dapat memperbarui data bagan secara dinamis dengan memanipulasi properti seri dan sumbu secara terprogram berdasarkan kebutuhan Anda.

### Di mana saya dapat menemukan dokumentasi lebih rinci untuk Aspose.Words untuk .NET?

 Anda dapat menemukan dokumentasi yang lebih detail[Di Sini](https://reference.aspose.com/words/net/).