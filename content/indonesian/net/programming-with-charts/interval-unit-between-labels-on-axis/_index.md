---
title: Satuan Interval Antar Label Pada Sumbu Bagan
linktitle: Satuan Interval Antar Label Pada Sumbu Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur satuan interval antar label pada sumbu bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengatur satuan interval antar label pada sumbu bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyesuaikan label sumbu.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan bagan kolom ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan lima item dengan nilainya yang sesuai.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Langkah 4: Sesuaikan label sumbu

 Untuk mengatur satuan interval antar label pada sumbu X, akses`AxisX` properti bagan dan atur`TickLabelSpacing` properti ke nilai yang diinginkan. Dalam contoh ini, kami mengatur spasi menjadi 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Langkah 5: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Ini menyelesaikan implementasi pengaturan satuan interval antar label pada sumbu menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber Unit Interval Antar Label Pada Sumbu menggunakan Aspose.Words untuk .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur satuan interval antar label pada sumbu bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan bagan kolom, menambahkan data seri, dan menyesuaikan label sumbu untuk mengontrol jarak antar label.

Aspose.Words untuk .NET menyediakan fitur canggih untuk memanipulasi bagan di dokumen Word. Dengan mengatur satuan interval antar label pada sumbu, Anda dapat mengontrol kepadatan tampilan label dan meningkatkan keterbacaan bagan Anda. Hal ini memungkinkan Anda mengoptimalkan penyajian data dan meningkatkan pengalaman pengguna secara keseluruhan.

Dengan Aspose.Words untuk .NET, Anda memiliki fleksibilitas untuk menyesuaikan berbagai aspek bagan, termasuk label sumbu. Anda dapat mengatur satuan interval yang diinginkan untuk memastikan bahwa label diberi jarak yang tepat dan memberikan representasi titik data yang jelas.

### FAQ

#### Q1. Apa yang dimaksud dengan label sumbu dalam bagan?
Label sumbu dalam bagan merujuk pada representasi tekstual nilai di sepanjang sumbu horizontal (sumbu X) atau vertikal (sumbu Y) bagan. Label ini membantu mengidentifikasi dan menafsirkan titik data yang diplot pada bagan. Label sumbu memberikan konteks dan memungkinkan pengguna memahami skala dan rentang nilai dalam diagram.

#### Q2. Bagaimana cara menyesuaikan jarak antar label sumbu?
 Untuk menyesuaikan jarak antar label sumbu dalam bagan menggunakan Aspose.Words untuk .NET, Anda dapat mengakses`AxisX` atau`AxisY` properti bagan dan memodifikasi`TickLabelSpacing` Properti. Dengan mengatur`TickLabelSpacing` ke nilai tertentu, Anda dapat mengontrol satuan interval antara label pada sumbu masing-masing, menyesuaikan jarak sesuai kebutuhan Anda.

#### Q3. Bisakah saya mengatur jarak yang berbeda untuk label sumbu X dan sumbu Y?
Ya, Anda dapat mengatur jarak berbeda untuk label sumbu X dan sumbu Y menggunakan Aspose.Words untuk .NET. Akses sumbu masing-masing (`AxisX` untuk sumbu X atau`AxisY` untuk sumbu Y) pada grafik dan modifikasi`TickLabelSpacing`properti secara individual untuk setiap sumbu. Hal ini memungkinkan Anda memiliki unit interval dan jarak yang berbeda untuk label pada sumbu X dan sumbu Y, sehingga memberikan kontrol yang lebih baik terhadap tampilan bagan.

#### Q4. Apa arti satuan interval antar label pada sumbu?
Satuan interval antar label pada sumbu menentukan jarak antar label berurutan yang ditampilkan pada grafik. Dengan mengatur satuan interval, Anda dapat mengontrol kepadatan label dan memastikan jarak label tepat untuk menghindari kepadatan dan tumpang tindih. Menyesuaikan satuan interval memungkinkan Anda menyajikan data dengan cara yang lebih mudah dibaca dan menarik secara visual.

#### Q5. Bisakah saya mengubah properti lain dari label sumbu?
Ya, Aspose.Words untuk .NET menyediakan berbagai properti untuk menyesuaikan tampilan dan perilaku label sumbu. Anda dapat memodifikasi properti seperti font, ukuran, warna, orientasi, perataan, dan lainnya untuk mencapai pemformatan dan gaya yang diinginkan untuk label sumbu. Pustaka ini menawarkan kontrol ekstensif atas elemen bagan, memungkinkan Anda membuat bagan yang terlihat profesional dan disesuaikan dengan kebutuhan spesifik Anda.