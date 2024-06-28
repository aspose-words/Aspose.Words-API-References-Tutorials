---
title: Sisipkan Bagan Sebar di Dokumen Word
linktitle: Sisipkan Bagan Sebar di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan diagram sebar ke dalam dokumen menggunakan Aspose.Words untuk .NET. Tambahkan data seri dengan koordinat X dan Y.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-scatter-chart/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan diagram sebar ke dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyimpan dokumen.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan diagram sebar ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan dua set koordinat X dan Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Ini menyelesaikan implementasi penyisipan diagram sebar menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Bagan Sebar menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyisipkan diagram sebar ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan diagram sebar, menambahkan data seri dengan koordinat X dan Y, dan menyimpan dokumen dengan diagram.

Aspose.Words for .NET menyediakan API komprehensif untuk Pemrosesan Kata dengan bagan di dokumen Word. Bagan sebar berguna untuk memvisualisasikan dan menganalisis data dengan dua variabel numerik. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah membuat diagram sebar yang mewakili hubungan antara nilai X dan Y dan mengidentifikasi pola atau tren dalam data.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengotomatiskan proses pembuatan dokumen dengan diagram sebar, menghemat waktu dan tenaga dalam pembuatan dokumen manual. Pustaka ini menawarkan berbagai jenis bagan, termasuk bagan sebar, dan menyediakan berbagai opsi penyesuaian untuk menyesuaikan tampilan bagan sesuai kebutuhan Anda.

### FAQ

#### Q1. Apa itu diagram sebar?
Bagan sebar adalah jenis bagan yang menampilkan hubungan antara dua variabel numerik. Ini terdiri dari serangkaian titik yang diplot pada kisi koordinat, dengan satu variabel direpresentasikan pada sumbu X dan variabel lainnya direpresentasikan pada sumbu Y. Bagan sebar digunakan untuk mengidentifikasi pola, korelasi, atau tren antara dua kumpulan titik data.

#### Q2. Bisakah saya menambahkan beberapa rangkaian ke diagram sebar?
Ya, Anda dapat menambahkan beberapa rangkaian ke diagram sebar menggunakan Aspose.Words untuk .NET. Setiap rangkaian mewakili sekumpulan titik data dengan koordinat X dan Y masing-masing. Dengan menambahkan beberapa rangkaian, Anda dapat membandingkan dan menganalisis kumpulan data yang berbeda dalam diagram sebar yang sama, sehingga memberikan tampilan data yang komprehensif.

#### Q3. Bisakah saya menyesuaikan tampilan diagram sebar?
Ya, menggunakan Aspose.Words untuk .NET, Anda dapat menyesuaikan berbagai aspek tampilan diagram sebar. Anda dapat mengubah properti seperti warna rangkaian, bentuk penanda, label sumbu, dan format area bagan. Pustaka ini menyediakan serangkaian API untuk mengontrol elemen visual bagan dan membuat tampilan yang disesuaikan dengan kebutuhan Anda.

#### Q4. Bisakah saya menyimpan dokumen dengan diagram sebar yang disisipkan dalam format berbeda?
Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen dengan diagram sebar yang disisipkan dalam berbagai format, seperti DOCX, PDF, HTML, dan banyak lagi. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Bagan sebar yang disisipkan akan disimpan dalam dokumen yang disimpan.

#### Q5. Bisakah saya mengubah data dan tampilan diagram sebar setelah memasukkannya?
Ya, setelah memasukkan diagram sebar ke dalam dokumen, Anda dapat mengubah data dan tampilannya menggunakan API yang disediakan oleh Aspose.Words untuk .NET. Anda bisa memperbarui data seri dengan koordinat X dan Y baru, mengubah bentuk dan warna penanda, mengkustomisasi properti sumbu, dan menerapkan opsi pemformatan untuk membuat bagan dinamis dan interaktif di dokumen Word Anda.