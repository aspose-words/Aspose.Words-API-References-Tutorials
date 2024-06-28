---
title: Tetapkan Opsi Default Untuk Label Data Dalam Bagan
linktitle: Tetapkan Opsi Default Untuk Label Data Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur opsi default untuk label data dalam bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/default-options-for-data-labels/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengatur opsi default untuk label data dalam bagan. Kode yang diberikan menunjukkan cara membuat bagan, menambahkan seri data, dan mengkustomisasi label data menggunakan Aspose.Words.

## Langkah 1: Siapkan proyek

Sebelum kita mulai, pastikan Anda memiliki persyaratan berikut:

- Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mendownloadnya menggunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen keluaran akan disimpan.

## Langkah 2: Buat dokumen baru dan masukkan bagan.

 Pertama, mari buat yang baru`Document` objek dan a`DocumentBuilder` untuk membuat dokumen tersebut.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Selanjutnya, kita menyisipkan bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder`. Dalam contoh ini, kita akan menyisipkan diagram lingkaran.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan seri data ke bagan

Sekarang, mari tambahkan seri data ke bagan. Dalam contoh ini, kita akan menambahkan tiga kategori dan nilainya yang sesuai.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Langkah 4: Sesuaikan label data

 Untuk menyesuaikan label data dalam bagan, kita perlu mengakses`ChartDataLabelCollection` objek yang terkait dengan rangkaian tersebut.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Kami kemudian dapat memodifikasi berbagai properti`labels`objek untuk mengatur opsi yang diinginkan untuk label data. Dalam contoh ini, kami akan mengaktifkan menampilkan persentase dan nilai, menonaktifkan garis pemimpin, dan menetapkan pemisah khusus.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Langkah 5: Simpan dokumen

 Terakhir, kami menyimpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Ini menyelesaikan implementasi pengaturan opsi default untuk label data dalam bagan menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Opsi Default Untuk Label Data menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur opsi default untuk label data dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat bagan, menambahkan seri data, dan menyesuaikan label data untuk memenuhi kebutuhan spesifik Anda. Aspose.Words untuk .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan bagan di dokumen Word, memungkinkan Anda memanipulasi berbagai elemen bagan dan mencapai tampilan dan fungsionalitas yang diinginkan.

 Dengan mengatur properti dari`ChartDataLabelCollection`objek yang terkait dengan rangkaian bagan, Anda dapat mengontrol tampilan label data, termasuk opsi seperti menampilkan persentase, nilai, garis pemimpin, dan pemisah khusus. Fleksibilitas ini memungkinkan Anda menyajikan data secara efektif dan menyempurnakan representasi visual bagan Anda.

### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka yang memungkinkan pengembang membuat, memanipulasi, dan menyimpan dokumen Word secara terprogram menggunakan aplikasi .NET. Ini menyediakan berbagai fitur untuk Pemrosesan Kata dengan elemen dokumen, termasuk bagan.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstal Aspose.Words untuk .NET dengan mengunduhnya menggunakan manajer paket NuGet di Visual Studio. Cukup cari "Apose.Words" di manajer paket NuGet dan instal ke proyek Anda.

#### Q3. Bisakah saya mengkustomisasi aspek bagan lainnya menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET memungkinkan Anda menyesuaikan berbagai aspek bagan, seperti tipe bagan, label sumbu, legenda, area plot, dan banyak lagi. Anda dapat mengakses dan memodifikasi berbagai properti objek bagan untuk mencapai tampilan dan perilaku yang diinginkan.

#### Q4. Bisakah saya menyimpan grafik dalam format berbeda?
 Ya, Aspose.Words untuk .NET mendukung penyimpanan dokumen yang berisi bagan dalam berbagai format, termasuk DOCX, PDF, HTML, dan banyak lagi. Anda dapat memilih format yang sesuai berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen.

#### Q5. Bisakah saya menerapkan teknik ini pada tipe grafik lainnya?
Ya, teknik yang dijelaskan dalam tutorial ini dapat diterapkan ke tipe bagan lain yang didukung oleh Aspose.Words untuk .NET. Kuncinya adalah mengakses objek dan properti relevan yang spesifik untuk tipe bagan yang Anda gunakan untuk Pemrosesan Kata.