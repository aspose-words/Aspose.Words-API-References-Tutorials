---
title: Sesuaikan Seri Bagan Tunggal Dalam Bagan
linktitle: Sesuaikan Seri Bagan Tunggal Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkustomisasi rangkaian bagan tunggal dalam bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/single-chart-series/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengkustomisasi rangkaian bagan tunggal dalam bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, mengakses rangkaian tertentu, dan mengubah propertinya.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

- Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mendownloadnya dengan menggunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen keluaran akan disimpan.

## Langkah 2: Buat dokumen baru dan masukkan bagan

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

## Langkah 3: Akses dan sesuaikan rangkaian bagan

 Untuk mengubah rangkaian bagan tunggal, Anda perlu mengakses`ChartSeries` objek grafik.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Ini menyelesaikan implementasi penyesuaian rangkaian bagan tunggal menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Seri Bagan Tunggal menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Anda juga dapat menentukan apakah garis yang menghubungkan titik-titik pada grafik harus dihaluskan menggunakan spline Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Menentukan apakah secara default elemen induk akan membalikkan warnanya jika nilainya negatif.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengkustomisasi satu rangkaian bagan dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan diagram garis, mengakses rangkaian diagram tertentu, dan memodifikasi propertinya untuk mencapai penyesuaian yang diinginkan.

Aspose.Words untuk .NET menyediakan fitur canggih untuk memanipulasi bagan di dokumen Word. Dengan mengakses rangkaian bagan individual, Anda dapat menerapkan modifikasi spesifik untuk menyesuaikan tampilan dan perilakunya. Hal ini memungkinkan Anda mengubah nama rangkaian, mengaktifkan penghalusan garis bagan, menyesuaikan penanda untuk titik data, membalikkan warna untuk nilai negatif, dan banyak lagi, untuk menyempurnakan representasi visual bagan Anda.

Menyesuaikan satu rangkaian bagan memberi Anda fleksibilitas untuk menyorot data tertentu atau menekankan tren tertentu dalam bagan Anda. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengakses dan memodifikasi properti rangkaian bagan, memungkinkan Anda membuat bagan yang menarik secara visual dan informatif di dokumen Word Anda.

### FAQ

#### Q1. Bisakah saya mengkustomisasi beberapa rangkaian bagan dalam satu bagan?
 Ya, Anda dapat mengkustomisasi beberapa rangkaian bagan dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengakses`ChartSeries`objek dalam bagan, Anda dapat memilih dan memodifikasi beberapa rangkaian berdasarkan indeks atau kriteria spesifiknya. Gunakan tugas loop atau individual untuk mengubah properti yang diinginkan untuk setiap rangkaian bagan. Dengan cara ini, Anda dapat menerapkan penyesuaian berbeda ke beberapa rangkaian dalam diagram yang sama.

#### Q2. Bagaimana cara mengubah nama rangkaian grafik?
 Untuk mengubah nama rangkaian bagan dalam bagan menggunakan Aspose.Words untuk .NET, Anda perlu mengakses`Name` properti dari`ChartSeries` objek dan atur ke nama yang diinginkan. Nama rangkaian biasanya ditampilkan dalam legenda bagan atau label data, memberikan label deskriptif untuk rangkaian tersebut. Dengan memodifikasi nama rangkaian, Anda dapat memberikan nama bermakna yang mencerminkan data yang diwakili oleh setiap rangkaian.

#### Q3. Apa yang dimaksud dengan pemulusan rangkaian grafik?
Pemulusan rangkaian grafik adalah teknik penyempurnaan visual yang memungkinkan Anda membuat garis halus yang menghubungkan titik-titik pada grafik. Ini menerapkan algoritme penghalusan, seperti spline Catmull-Rom, untuk melakukan interpolasi antar titik data dan membuat kurva yang menarik secara visual. Untuk mengaktifkan penghalusan rangkaian dalam bagan menggunakan Aspose.Words untuk .NET, akses`Smooth` properti dari`ChartSeries` objek dan atur ke`true`. Smoothing dapat berguna untuk menampilkan tren atau pola pada data yang fluktuasinya tidak teratur.

#### Q4. Bagaimana cara menyesuaikan penanda untuk titik data dalam rangkaian bagan?
 Untuk menyesuaikan penanda titik data dalam rangkaian bagan menggunakan Aspose.Words untuk .NET, Anda perlu mengakses`Marker` properti dari`ChartSeries` objek dan memodifikasi propertinya seperti`Symbol` Dan`Size`. Penanda adalah indikator visual yang ditempatkan pada grafik untuk mewakili titik data individual. Anda dapat memilih dari berbagai simbol penanda bawaan dan menyesuaikan ukurannya untuk menyorot atau membedakan titik data tertentu dalam rangkaian.

#### Q5. Bisakah saya membalikkan warna untuk nilai negatif dalam rangkaian bagan?
 Ya, Anda dapat membalikkan warna untuk nilai negatif dalam rangkaian bagan menggunakan Aspose.Words untuk .NET. Dengan mengatur`InvertIfNegative` properti dari`ChartSeries` objek untuk`true`, warna titik data dengan nilai negatif akan dibalik, membuatnya berbeda secara visual dari nilai positif. Fitur ini dapat berguna saat membandingkan nilai positif dan negatif dalam rangkaian bagan, sehingga memberikan perbedaan yang jelas antara keduanya.