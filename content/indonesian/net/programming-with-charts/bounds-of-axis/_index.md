---
title: Batasan Sumbu Dalam Bagan
linktitle: Batasan Sumbu Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur batas sumbu dalam bagan menggunakan Aspose.Words untuk .NET yang mengontrol rentang nilai yang ditampilkan pada sumbu.
type: docs
weight: 10
url: /id/net/programming-with-charts/bounds-of-axis/
---

Tutorial ini menjelaskan cara mengatur batas sumbu dalam bagan menggunakan Aspose.Words untuk .NET. Dengan menyisipkan bagan, menambahkan data seri, dan mengonfigurasi penskalaan sumbu, Anda dapat menentukan nilai minimum dan maksimum untuk sumbu tersebut.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder`keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan dan Konfigurasikan Bagan
 Sisipkan bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder` obyek. Tetapkan jenis dan dimensi bagan yang diinginkan.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 4: Tambahkan Data Seri
Hapus semua rangkaian yang ada di diagram dan tambahkan data rangkaian baru. Dalam contoh ini, kami menambahkan rangkaian dengan label "Item 1" ke "Item 5" dan nilai yang sesuai.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Langkah 5: Tetapkan Batas Sumbu
 Konfigurasikan penskalaan sumbu Y dengan mengatur nilai minimum dan maksimum menggunakan`Scaling.Minimum` Dan`Scaling.Maximum` sifat-sifat sumbu.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Langkah 6: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Contoh kode sumber untuk Bounds Of Axis menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Itu dia! Anda telah berhasil menetapkan batas sumbu dalam bagan menggunakan Aspose.Words untuk .NET.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara mengatur batas sumbu dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat menyisipkan dan mengonfigurasi bagan, menambahkan data seri, dan menentukan nilai minimum dan maksimum untuk penskalaan sumbu. Aspose.Words for .NET menyediakan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan dokumen Word, memungkinkan Anda membuat bagan yang dinamis dan menarik secara visual dengan mudah.


### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang memungkinkan pengembang bekerja dengan dokumen Word secara terprogram. Ini menyediakan berbagai fitur dan fungsi untuk membuat, memanipulasi, dan menyimpan dokumen Word.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Untuk menginstal Aspose.Words untuk .NET, Anda dapat menggunakan manajer paket NuGet di Visual Studio. Cukup cari "Aspose.Words" di manajer paket NuGet dan instal ke proyek Anda.

#### Q3. Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa pemrograman lain?
Tidak, Aspose.Words untuk .NET dirancang khusus untuk aplikasi .NET. Ia bekerja dengan bahasa pemrograman seperti C# dan VB.NET.

#### Q4. Apakah ada prasyarat lain untuk menggunakan Aspose.Words untuk .NET?
Selain menginstal perpustakaan Aspose.Words untuk .NET, Anda harus memiliki pengetahuan dasar tentang pemrograman C# dan Pemrosesan Kata dengan dokumen Word. Keakraban dengan kerangka .NET juga akan membantu.
