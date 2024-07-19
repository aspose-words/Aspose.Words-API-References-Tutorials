---
title: Tentukan Properti Sumbu XY Dalam Bagan
linktitle: Tentukan Properti Sumbu XY Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan properti sumbu XY dalam bagan menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk pengembang .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/define-xyaxis-properties/
---
## Perkenalan

Bagan adalah alat yang ampuh untuk memvisualisasikan data. Saat Anda perlu membuat dokumen profesional dengan bagan dinamis, Aspose.Words for .NET adalah perpustakaan yang sangat berharga. Artikel ini akan memandu Anda melalui proses menentukan properti sumbu XY dalam bagan menggunakan Aspose.Words untuk .NET, menguraikan setiap langkah untuk memastikan kejelasan dan kemudahan pemahaman.

## Prasyarat

Sebelum mendalami pengkodean, ada beberapa prasyarat yang perlu Anda miliki:

1. Aspose.Words for .NET: Pastikan Anda memiliki perpustakaan Aspose.Words for .NET. Kamu bisa[Unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Anda memerlukan lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.
3. .NET Framework: Pastikan lingkungan pengembangan Anda diatur untuk pengembangan .NET.
4. Pengetahuan Dasar C#: Panduan ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

## Impor Namespace

Untuk memulainya, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Hal ini memastikan Anda memiliki akses ke semua kelas dan metode yang diperlukan untuk membuat dan memanipulasi dokumen dan bagan.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Kami akan membagi prosesnya menjadi beberapa langkah sederhana, masing-masing berfokus pada bagian tertentu dalam menentukan properti sumbu XY dalam bagan.

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

 Pertama, Anda perlu menginisialisasi dokumen baru dan a`DocumentBuilder` obyek. Itu`DocumentBuilder` membantu dalam memasukkan konten ke dalam dokumen.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bagan

Selanjutnya, Anda akan memasukkan bagan ke dalam dokumen. Dalam contoh ini, kita akan menggunakan bagan Area. Anda dapat menyesuaikan dimensi bagan sesuai kebutuhan.

```csharp
// Sisipkan bagan
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Hapus Seri Default dan Tambahkan Data Khusus

Secara default, bagan akan memiliki beberapa rangkaian yang telah ditentukan sebelumnya. Kami akan menghapusnya dan menambahkan seri data khusus kami.

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

## Langkah 4: Tentukan Properti Sumbu X

Sekarang saatnya mendefinisikan properti sumbu X. Ini termasuk mengatur jenis kategori, menyesuaikan perpotongan sumbu, dan menyesuaikan tanda centang dan label.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Diukur dalam satuan tampilan sumbu Y (ratusan).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Langkah 5: Tentukan Properti Sumbu Y

Demikian pula, Anda akan mengatur properti untuk sumbu Y. Ini termasuk pengaturan posisi label centang, unit mayor dan minor, unit tampilan, dan penskalaan.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang Anda tentukan. Ini akan menghasilkan dokumen Word dengan bagan yang disesuaikan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Kesimpulan

Membuat dan menyesuaikan bagan di dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah setelah Anda memahami langkah-langkah yang terlibat. Panduan ini telah memandu Anda melalui proses menentukan properti sumbu XY dalam bagan, mulai dari menginisialisasi dokumen hingga menyimpan produk akhir. Dengan keterampilan ini, Anda dapat membuat bagan mendetail dan terlihat profesional yang menyempurnakan dokumen Anda.

## FAQ

### Jenis bagan apa yang dapat saya buat dengan Aspose.Words untuk .NET?
Anda dapat membuat berbagai jenis bagan, termasuk Area, Batang, Garis, Pai, dan lainnya.

### Bagaimana cara menginstal Aspose.Words untuk .NET?
 Anda dapat mengunduh Aspose.Words untuk .NET dari[Di Sini](https://releases.aspose.com/words/net/) dan ikuti petunjuk instalasi yang diberikan.

### Bisakah saya menyesuaikan tampilan grafik saya?
Ya, Aspose.Words untuk .NET memungkinkan penyesuaian bagan yang ekstensif, termasuk warna, font, dan properti sumbu.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan tutorial dan dokumentasi lainnya?
 Anda dapat menemukan lebih banyak tutorial dan dokumentasi terperinci di[Halaman dokumentasi Aspose.Words untuk .NET](https://reference.aspose.com/words/net/).
