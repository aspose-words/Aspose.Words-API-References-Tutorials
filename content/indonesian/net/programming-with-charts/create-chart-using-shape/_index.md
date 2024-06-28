---
title: Buat & Sesuaikan Bagan Menggunakan Bentuk
linktitle: Buat & Sesuaikan Bagan Menggunakan Bentuk
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dan mengkustomisasi bagan menggunakan bentuk di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/create-chart-using-shape/
---

Tutorial ini menjelaskan cara membuat bagan menggunakan bentuk di dokumen Word menggunakan Aspose.Words untuk .NET.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 4: Sesuaikan Bagan
Sesuaikan bagan dengan memodifikasi berbagai properti seperti judul bagan dan legenda.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Langkah 5: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Contoh kode sumber untuk Membuat Bagan Menggunakan Bentuk menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Harap dicatat jika nilai nol atau kosong ditentukan sebagai teks judul, judul yang dibuat secara otomatis akan ditampilkan.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Itu dia! Anda telah berhasil membuat bagan menggunakan bentuk di dokumen Word menggunakan Aspose.Words untuk .NET.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara membuat bagan menggunakan bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat menyisipkan dan mengonfigurasi bentuk bagan, menyesuaikan tampilannya, dan menyimpan dokumen. Aspose.Words untuk .NET menyediakan serangkaian fitur komprehensif untuk Pemrosesan Kata dengan dokumen dan bagan Word, memungkinkan Anda membuat bagan yang tampak profesional dan menarik secara visual langsung di aplikasi .NET Anda.

### FAQ

#### Q1. Bisakah saya membuat bagan di dokumen Word menggunakan Aspose.Words untuk .NET?
Ya, dengan Aspose.Words untuk .NET, Anda dapat membuat bagan dalam dokumen Word secara terprogram. Aspose.Words menyediakan API dan fungsionalitas untuk menyisipkan berbagai jenis bagan, menyesuaikan tampilannya, dan memanipulasi data bagan.

#### Q2. Tipe bagan apa yang didukung oleh Aspose.Words untuk .NET?
Aspose.Words untuk .NET mendukung berbagai jenis bagan, termasuk bagan garis, bagan batang, bagan lingkaran, bagan area, bagan sebar, dan banyak lagi. Anda dapat memilih jenis bagan yang sesuai berdasarkan data dan kebutuhan visualisasi Anda.

#### Q3. Bisakah saya menyesuaikan tampilan grafik yang dibuat?
Ya, Anda dapat mengkustomisasi tampilan bagan yang dibuat menggunakan Aspose.Words untuk .NET. Anda dapat memodifikasi properti seperti judul bagan, posisi legenda, label data, label sumbu, warna, dan elemen visual lainnya untuk memenuhi kebutuhan desain dan pemformatan spesifik Anda.
