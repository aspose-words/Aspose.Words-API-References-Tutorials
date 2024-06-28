---
title: Sesuaikan Titik Data Bagan Tunggal Dalam Bagan
linktitle: Sesuaikan Titik Data Bagan Tunggal Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkustomisasi satu titik data dalam bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/single-chart-data-point/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengkustomisasi satu titik data dalam bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, mengakses titik data tertentu, dan mengubah propertinya.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan diagram garis ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Akses dan sesuaikan titik data

 Untuk mengubah titik data individual, Anda perlu mengakses`ChartDataPointCollection` dari rangkaian dan pilih titik data yang diinginkan menggunakan indeks.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Ini menyelesaikan implementasi penyesuaian satu titik data dalam bagan menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Titik Data Bagan Tunggal menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengkustomisasi satu titik data dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan bagan garis, mengakses titik data tertentu dalam rangkaian bagan, dan memodifikasi propertinya untuk mencapai penyesuaian yang diinginkan.

Aspose.Words untuk .NET menyediakan fitur canggih untuk memanipulasi bagan di dokumen Word. Dengan mengakses titik data individual dalam rangkaian bagan, Anda dapat menerapkan modifikasi spesifik untuk menyesuaikan tampilan dan perilakunya. Hal ini memungkinkan Anda menyorot titik data tertentu, mengubah simbol penanda, menyesuaikan ukuran penanda, dan banyak lagi, untuk menyempurnakan representasi visual bagan Anda.

Menyesuaikan setiap titik data memberi Anda fleksibilitas untuk menekankan data penting atau menyorot tren tertentu dalam bagan Anda. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengakses dan memodifikasi titik data dalam berbagai tipe bagan, memungkinkan Anda membuat bagan yang menarik secara visual dan informatif dalam dokumen Word Anda.

### FAQ

#### Q1. Bisakah saya mengkustomisasi beberapa titik data dalam bagan?
 Ya, Anda dapat mengkustomisasi beberapa titik data dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengakses`ChartDataPointCollection`dari suatu rangkaian, Anda dapat memilih dan mengubah beberapa titik data berdasarkan indeksnya. Gunakan penugasan loop atau individual untuk mengubah properti yang diinginkan untuk setiap titik data. Dengan cara ini, Anda dapat menerapkan penyesuaian berbeda ke beberapa titik data dalam bagan yang sama.

#### Q2. Bagaimana cara mengubah simbol penanda untuk titik data?
 Untuk mengubah simbol penanda titik data dalam bagan menggunakan Aspose.Words untuk .NET, Anda perlu mengakses`Marker` properti dari`ChartDataPoint` objek dan atur`Symbol` properti ke simbol penanda yang diinginkan. Simbol penanda mewakili bentuk atau ikon yang digunakan untuk mewakili setiap titik data pada bagan. Anda dapat memilih dari berbagai simbol penanda bawaan seperti lingkaran, persegi, berlian, segitiga, bintang, dan banyak lagi.

#### Q3. Bisakah saya menyesuaikan ukuran penanda titik data?
 Ya, Anda dapat menyesuaikan ukuran penanda titik data dalam bagan menggunakan Aspose.Words untuk .NET. Akses`Marker` properti dari`ChartDataPoint` objek dan atur`Size`properti ke ukuran penanda yang diinginkan. Ukuran penanda biasanya ditentukan dalam titik, dimana nilai yang lebih besar menunjukkan ukuran penanda yang lebih besar. Menyesuaikan ukuran penanda memungkinkan Anda menekankan titik data tertentu atau membedakannya berdasarkan signifikansinya.

#### Q4. Properti apa lagi yang dapat saya modifikasi untuk titik data?
Aspose.Words untuk .NET menyediakan serangkaian properti yang dapat Anda modifikasi untuk titik data dalam bagan. Beberapa properti yang umum dimodifikasi mencakup simbol penanda, ukuran penanda, warna penanda, visibilitas label data, ledakan, pembalikan jika negatif, dan banyak lagi. Properti ini memungkinkan Anda menyesuaikan tampilan, perilaku, dan interaktivitas titik data individual, memungkinkan Anda membuat bagan yang disesuaikan dengan kebutuhan spesifik Anda.

#### Q5. Bisakah saya mengkustomisasi titik data di tipe bagan lainnya?
Ya, Anda dapat mengkustomisasi titik data dalam berbagai tipe bagan menggunakan Aspose.Words untuk .NET. Meskipun tutorial ini menunjukkan penyesuaian titik data dalam diagram garis, Anda dapat menerapkan teknik serupa ke tipe diagram lainnya seperti diagram kolom, diagram batang, diagram lingkaran, dan banyak lagi. Prosesnya melibatkan pengaksesan rangkaian dan titik data dalam bagan dan memodifikasi propertinya.