---
title: Tambahkan Nilai Tanggal Waktu Ke Sumbu Bagan
linktitle: Tambahkan Nilai Tanggal Waktu Ke Sumbu Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan nilai tanggal waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/date-time-values-to-axis/
---

Tutorial ini menjelaskan cara menambahkan nilai tanggal waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET.

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
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan dan Konfigurasikan Bentuk Bagan
 Sisipkan bentuk bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder` obyek. Tetapkan jenis dan dimensi bagan yang diinginkan.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Langkah 4: Tambahkan Data ke Bagan
Tambahkan data ke rangkaian bagan, termasuk nilai tanggal dan waktu.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Langkah 5: Konfigurasikan Sumbu
Konfigurasikan sumbu X pada bagan untuk menampilkan nilai tanggal dan waktu.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Langkah 6: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Contoh kode sumber untuk Nilai Tanggal Waktu Ke Sumbu menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Tetapkan satuan besar menjadi satu minggu dan satuan kecil menjadi satu hari.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Kode contoh ini membuat dokumen Word baru, menyisipkan bagan kolom dengan nilai tanggal waktu pada sumbu X, dan menyimpan dokumen ke direktori yang ditentukan.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara menambahkan nilai tanggal waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat bagan, menambahkan nilai tanggal waktu ke rangkaian, dan mengonfigurasi sumbu untuk menampilkan nilai tanggal waktu secara akurat. Aspose.Words untuk .NET menyediakan serangkaian fitur canggih untuk Pemrosesan Kata dengan bagan di dokumen Word, memungkinkan Anda mewakili dan memvisualisasikan data dengan nilai tanggal dan waktu secara efektif.

### FAQ

#### Q1. Bisakah saya menambahkan nilai tanggal waktu ke sumbu bagan menggunakan Aspose.Words untuk .NET?
Ya, dengan Aspose.Words untuk .NET, Anda dapat menambahkan dan menampilkan nilai tanggal waktu pada sumbu bagan di dokumen Word. Aspose.Words menyediakan API dan fungsionalitas untuk bekerja dengan berbagai tipe bagan dan menyesuaikan tampilannya, termasuk menangani nilai tanggal dan waktu pada sumbu.

#### Q2. Bagaimana cara menambahkan nilai tanggal waktu ke rangkaian bagan?
 Untuk menambahkan nilai tanggal waktu ke rangkaian bagan, Anda dapat menggunakan`Add`metode rangkaian grafik. Berikan array nilai tanggal waktu sebagai data kategori (sumbu X), bersama dengan nilai rangkaian yang sesuai. Hal ini memungkinkan Anda untuk memplot titik data dengan nilai tanggal dan waktu pada grafik.

#### Q3. Bagaimana cara mengonfigurasi sumbu untuk menampilkan nilai tanggal dan waktu?
 Anda dapat mengonfigurasi sumbu bagan untuk menampilkan nilai tanggal dan waktu dengan mengatur properti yang sesuai. Misalnya, Anda dapat menentukan nilai minimum dan maksimum untuk sumbu menggunakan`Scaling.Minimum` Dan`Scaling.Maximum` properti, masing-masing. Selain itu, Anda dapat mengatur satuan mayor dan minor untuk menentukan interval dan tanda centang untuk sumbu.
