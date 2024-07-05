---
title: Sesuaikan Label Data Bagan
linktitle: Sesuaikan Label Data Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dan mengkustomisasi label data dalam bagan menggunakan Aspose.Words untuk .NET untuk memberikan informasi tambahan tentang titik data.
type: docs
weight: 10
url: /id/net/programming-with-charts/chart-data-label/
---

Tutorial ini menjelaskan cara menambahkan dan mengkustomisasi label data dalam bagan menggunakan Aspose.Words untuk .NET. Label data memberikan informasi tambahan tentang titik data dalam bagan.

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 4: Sesuaikan Label Data
Akses kumpulan label data dari rangkaian bagan dan ubah berbagai properti untuk menyesuaikan tampilan label data.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Langkah 5: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Contoh kode sumber untuk Label Data Bagan menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Secara default, saat Anda menambahkan label data ke titik data dalam diagram lingkaran, garis pemimpin ditampilkan untuk label data yang
	// diposisikan jauh di luar akhir titik data. Garis pemimpin membuat hubungan visual antara label data dan label datanya
	// titik data yang sesuai.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Itu dia! Anda telah berhasil menambahkan dan mengkustomisasi label data dalam bagan menggunakan Aspose.Words untuk .NET.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara menambahkan dan mengkustomisasi label data dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda bisa menyisipkan bagan, mengakses kumpulan label data, dan mengubah properti untuk mengkustomisasi tampilan label data. Aspose.Words untuk .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan dokumen dan bagan Word, memungkinkan Anda membuat bagan yang menarik secara visual dan informatif dengan label data yang disesuaikan.

### FAQ

#### Q1. Apa yang dimaksud dengan label data dalam bagan?
Label data dalam bagan memberikan informasi tambahan tentang titik data yang diwakili dalam bagan. Mereka dapat menampilkan nilai, kategori, nama rangkaian, persentase, atau detail relevan lainnya bergantung pada jenis bagan dan konfigurasi.

#### Q2. Bisakah saya menyesuaikan tampilan label data?
Ya, Anda dapat menyesuaikan tampilan label data dalam bagan. Aspose.Words untuk .NET menyediakan opsi untuk mengubah berbagai properti label data, seperti menampilkan kunci legenda, garis pemimpin, nama kategori, nama seri, nilai, dan banyak lagi. Anda juga dapat mengatur pemisah dan memformat label untuk memenuhi kebutuhan spesifik Anda.

#### Q3. Bisakah saya menambahkan label data ke tipe bagan apa pun?
Ya, Anda dapat menambahkan label data ke berbagai jenis diagram, termasuk diagram batang, diagram lingkaran, diagram garis, dan lainnya. Proses penambahan dan penyesuaian label data mungkin sedikit berbeda tergantung pada tipe bagan dan pustaka atau alat yang Anda gunakan.
