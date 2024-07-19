---
title: Sisipkan Bagan Sebar di Dokumen Word
linktitle: Sisipkan Bagan Sebar di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan diagram sebar di Word dengan Aspose.Words untuk .NET. Langkah mudah untuk mengintegrasikan representasi data visual ke dalam dokumen Anda.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-scatter-chart/
---
## Perkenalan

Dalam tutorial ini, Anda akan mempelajari cara memanfaatkan Aspose.Words untuk .NET untuk menyisipkan diagram sebar ke dalam dokumen Word Anda. Bagan sebar adalah alat visual canggih yang dapat secara efektif menampilkan titik data berdasarkan dua variabel, menjadikan dokumen Anda lebih menarik dan informatif.

## Prasyarat

Sebelum kita mendalami pembuatan diagram sebar dengan Aspose.Words untuk .NET, pastikan Anda memiliki prasyarat berikut:

1.  Instalasi Aspose.Words for .NET: Unduh dan instal Aspose.Words for .NET dari[Di Sini](https://releases.aspose.com/words/net/).
   
2. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan kerangka .NET akan bermanfaat.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

Sekarang, mari kita uraikan proses memasukkan diagram sebar ke dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET:

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

 Pertama, inisialisasi instance baru dari`Document` kelas dan`DocumentBuilder` kelas untuk mulai membuat dokumen Anda.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Masukkan Bagan Sebar

 Menggunakan`InsertChart` metode`DocumentBuilder` kelas untuk menyisipkan diagram sebar ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan Seri Data ke Bagan

Sekarang, tambahkan seri data ke diagram sebar Anda. Contoh ini menunjukkan penambahan rangkaian dengan titik data tertentu.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Langkah 4: Simpan Dokumen

 Terakhir, simpan dokumen yang dimodifikasi ke lokasi yang Anda inginkan menggunakan`Save` metode`Document` kelas.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyisipkan diagram sebar ke dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET. Bagan sebar adalah alat luar biasa untuk memvisualisasikan hubungan data, dan dengan Aspose.Words, Anda dapat dengan mudah mengintegrasikannya ke dalam dokumen Anda untuk meningkatkan kejelasan dan pemahaman.

## FAQ

### Bisakah saya mengkustomisasi tampilan diagram sebar menggunakan Aspose.Words?
Ya, Aspose.Words memungkinkan penyesuaian ekstensif properti bagan seperti warna, sumbu, dan label.

### Apakah Aspose.Words kompatibel dengan versi Microsoft Word yang berbeda?
Aspose.Words mendukung berbagai versi Microsoft Word, memastikan kompatibilitas lintas platform.

### Apakah Aspose.Words menyediakan dukungan untuk jenis bagan lainnya?
Ya, Aspose.Words mendukung berbagai jenis bagan termasuk diagram batang, diagram garis, dan diagram lingkaran.

### Bisakah saya memperbarui data di diagram sebar secara dinamis secara terprogram?
Tentu saja, Anda dapat memperbarui data bagan secara dinamis menggunakan panggilan API Aspose.Words.

### Di mana saya bisa mendapatkan bantuan atau dukungan lebih lanjut untuk Aspose.Words?
 Untuk bantuan lebih lanjut, kunjungi[Forum dukungan Aspose.Words](https://forum.aspose.com/c/words/8).