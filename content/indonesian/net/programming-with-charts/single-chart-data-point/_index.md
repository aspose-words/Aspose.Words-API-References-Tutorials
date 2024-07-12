---
title: Sesuaikan Titik Data Bagan Tunggal Dalam Bagan
linktitle: Sesuaikan Titik Data Bagan Tunggal Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkustomisasi titik data bagan tunggal menggunakan Aspose.Words untuk .NET dalam panduan langkah demi langkah yang mendetail. Sempurnakan bagan Anda dengan penanda dan ukuran unik.
type: docs
weight: 10
url: /id/net/programming-with-charts/single-chart-data-point/
---
## Perkenalan

Pernah bertanya-tanya bagaimana Anda bisa membuat bagan Anda menonjol dengan titik data yang unik? Baiklah, hari ini adalah hari keberuntungan kamu! Kami sedang mendalami penyesuaian satu titik data bagan menggunakan Aspose.Words untuk .NET. Bersiaplah untuk mengikuti tutorial langkah demi langkah yang tidak hanya informatif tetapi juga menyenangkan dan mudah diikuti.

## Prasyarat

Sebelum kita mulai, pastikan Anda sudah menyiapkan semua hal penting:

-  Aspose.Words untuk .NET Library: Pastikan Anda memiliki versi terbaru.[Unduh di sini](https://releases.aspose.com/words/net/).
- .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
- Pemahaman Dasar C#: Pemahaman dasar pemrograman C# akan sangat membantu.
- Lingkungan Pengembangan Terpadu (IDE): Visual Studio direkomendasikan.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan untuk memulai:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

Baiklah, mari kita mulai dengan menginisialisasi dokumen baru dan DocumentBuilder. Ini akan menjadi kanvas untuk bagan kita.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di Sini,`dataDir` adalah jalur direktori tempat Anda menyimpan dokumen Anda. Itu`DocumentBuilder` kelas membantu dalam membangun dokumen.

## Langkah 2: Sisipkan Bagan

Selanjutnya, mari masukkan diagram garis ke dalam dokumen. Ini akan menjadi tempat bermain kami untuk menyesuaikan titik data.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 Itu`InsertChart` metode mengambil jenis bagan, lebar, dan tinggi sebagai parameter. Dalam hal ini, kita menyisipkan diagram garis dengan lebar 432 dan tinggi 252.

## Langkah 3: Akses Seri Bagan

Sekarang, saatnya mengakses rangkaian dalam bagan kita. Bagan dapat memiliki beberapa rangkaian, dan setiap rangkaian berisi titik data.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

Di sini, kami mengakses dua seri pertama di bagan kami. 

## Langkah 4: Sesuaikan Titik Data

Di sinilah keajaiban terjadi! Mari sesuaikan titik data tertentu dalam rangkaian kita.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

Kami mengambil titik data dari seri pertama. Sekarang, mari kita sesuaikan poin-poin ini.

### Sesuaikan Titik Data 00

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 Untuk`dataPoint00`, kita menyetel ledakan (berguna untuk diagram lingkaran), mengubah simbol penanda menjadi lingkaran, dan menyetel ukuran penanda menjadi 15.

### Sesuaikan Titik Data 01

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 Untuk`dataPoint01`, kami mengubah simbol penanda menjadi berlian dan mengatur ukuran penanda menjadi 20.

### Sesuaikan Titik Data di Seri 1

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 Untuk titik data ketiga masuk`series1`, kami menyetelnya menjadi terbalik jika nilainya negatif, mengubah simbol penanda menjadi bintang, dan menyetel ukuran penanda menjadi 20.

## Langkah 5: Simpan Dokumen

Terakhir, mari simpan dokumen kita dengan semua penyesuaiannya.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 Baris ini menyimpan dokumen di direktori yang Anda tentukan dengan nama`WorkingWithCharts.SingleChartDataPoint.docx`.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengkustomisasi titik data individual dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengubah beberapa properti, Anda dapat membuat bagan Anda lebih informatif dan menarik secara visual. Jadi, silakan bereksperimen dengan berbagai penanda dan ukuran untuk melihat mana yang terbaik untuk data Anda.

## FAQ

### Bisakah saya mengkustomisasi titik data di jenis bagan lainnya?

Sangat! Anda dapat menyesuaikan titik data dalam berbagai jenis bagan, termasuk diagram batang, diagram lingkaran, dan lainnya. Prosesnya serupa di berbagai jenis bagan.

### Apakah mungkin menambahkan label khusus ke titik data?

 Ya, Anda dapat menambahkan label khusus ke titik data menggunakan`ChartDataPoint.Label` Properti. Hal ini memungkinkan Anda memberikan lebih banyak konteks untuk setiap titik data.

### Bagaimana cara menghapus titik data dari suatu rangkaian?

 Anda dapat menghapus titik data dengan mengatur visibilitasnya ke false menggunakan`dataPoint.IsVisible = false`.

### Bisakah saya menggunakan gambar sebagai penanda titik data?

Meskipun Aspose.Words tidak mendukung penggunaan gambar secara langsung sebagai penanda, Anda dapat membuat bentuk khusus dan menggunakannya sebagai penanda.

### Apakah mungkin untuk menganimasikan titik data pada bagan?

Aspose.Words untuk .NET tidak mendukung animasi untuk titik data bagan. Namun, Anda dapat membuat bagan animasi menggunakan alat lain dan menyematkannya ke dalam dokumen Word Anda.