---
title: Tentukan Properti Sumbu XY Dalam Bagan
linktitle: Tentukan Properti Sumbu XY Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan properti sumbu XY dalam bagan menggunakan Aspose.Words untuk .NET. Opsi penyesuaian untuk sumbu X dan Y diperlihatkan.
type: docs
weight: 10
url: /id/net/programming-with-charts/define-xyaxis-properties/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menentukan properti sumbu X dan Y dalam bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyesuaikan properti sumbu.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

- Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mendownloadnya dengan menggunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen keluaran akan disimpan.

## Langkah 2: Buat dokumen baru dan masukkan bagan.

 Buat yang baru`Document` objek dan a`DocumentBuilder` untuk membuat dokumen tersebut.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Selanjutnya, masukkan bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder`. Dalam contoh ini, kita akan menyisipkan diagram area.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan lima titik data dengan tanggal dan nilai yang sesuai.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Langkah 4: Sesuaikan properti sumbu X dan Y

 Untuk menyesuaikan properti sumbu X dan Y, akses`ChartAxis` objek yang terkait dengan grafik.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Ubah properti dari`xAxis` Dan`yAxis`objek untuk mengatur opsi yang diinginkan untuk sumbu X dan Y. Dalam contoh ini, kami akan menunjukkan beberapa properti umum yang dapat disesuaikan.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Langkah 5: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Ini menyelesaikan implementasi penentuan properti sumbu XY dalam bagan menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menentukan Properti XYAxis menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Sisipkan bagan
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Ubah sumbu X menjadi kategori dan bukan tanggal, sehingga semua titik akan ditempatkan dengan interval yang sama pada sumbu X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Diukur dalam satuan tampilan sumbu Y (ratusan).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menentukan properti untuk sumbu X dan Y dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat bagan, menambahkan data seri, dan menyesuaikan properti sumbu untuk memenuhi kebutuhan spesifik Anda. Aspose.Words untuk .NET menyediakan API komprehensif untuk Pemrosesan Kata dengan bagan di dokumen Word, memungkinkan Anda memanipulasi berbagai aspek bagan, termasuk sumbu.

Dengan mengakses`ChartAxis` objek yang terkait dengan bagan, Anda dapat mengubah properti seperti jenis kategori, persilangan sumbu, tanda centang, posisi label, penskalaan, dan banyak lagi. Fleksibilitas ini memungkinkan Anda menyesuaikan tampilan dan perilaku sumbu diagram untuk menyajikan data Anda secara efektif.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat dengan mudah mengintegrasikan pembuatan bagan dan kemampuan penyesuaian ke dalam aplikasi .NET Anda dan mengotomatiskan pembuatan dokumen yang terlihat profesional dengan visualisasi yang kaya.

### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen canggih yang memungkinkan pengembang membuat, memanipulasi, dan menyimpan dokumen Word secara terprogram dalam aplikasi .NET. Ini menyediakan berbagai fitur untuk Pemrosesan Kata dengan elemen dokumen, termasuk bagan.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstal Aspose.Words untuk .NET dengan mengunduhnya menggunakan manajer paket NuGet di Visual Studio. Cukup cari "Apose.Words" di manajer paket NuGet dan instal ke proyek Anda.

#### Q3. Bisakah saya mengkustomisasi aspek bagan lainnya menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET menyediakan kemampuan luas untuk menyesuaikan berbagai aspek bagan. Selain menentukan properti sumbu, Anda dapat mengubah tipe bagan, seri data, legenda, judul, area plot, label data, dan banyak elemen bagan lainnya. API ini menawarkan kontrol menyeluruh atas tampilan dan perilaku bagan.

#### Q4. Bisakah saya membuat berbagai jenis bagan menggunakan Aspose.Words untuk .NET?
 Ya, Aspose.Words untuk .NET mendukung berbagai jenis bagan, termasuk area, batang, garis, pai, sebar, dan banyak lagi. Anda dapat menggunakan`ChartType` enumerasi untuk menentukan tipe bagan yang diinginkan saat menyisipkan bentuk bagan ke dalam dokumen Word.

#### Q5. Bisakah saya menyimpan grafik dalam format berbeda?
Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen yang berisi bagan dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format yang sesuai berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen.

#### Q6. Bisakah saya menerapkan teknik ini ke beberapa bagan dalam satu dokumen?
 Ya, Anda dapat menerapkan teknik ini ke beberapa bagan dalam satu dokumen dengan mengulangi langkah-langkah yang diperlukan untuk setiap bagan. Anda dapat membuat yang terpisah`Chart` Dan`ChartAxis` objek untuk setiap bagan dan sesuaikan propertinya. Aspose.Words for .NET memberikan dukungan penuh untuk Pemrosesan Kata dengan banyak bagan dalam satu dokumen.