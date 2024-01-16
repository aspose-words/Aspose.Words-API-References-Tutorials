---
title: Sisipkan Bagan Kolom Sederhana Dalam Dokumen Word
linktitle: Sisipkan Bagan Kolom Sederhana Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bagan kolom sederhana ke dalam dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-simple-column-chart/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan bagan kolom sederhana ke dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyimpan dokumen.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan bagan kolom ke dalam dokumen. Anda dapat menentukan berbagai jenis dan ukuran bagan sesuai kebutuhan Anda.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kami akan menambahkan beberapa rangkaian dengan masing-masing dua kategori.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Ini menyelesaikan implementasi penyisipan bagan kolom sederhana menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Bagan Kolom Sederhana menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Anda dapat menentukan jenis dan ukuran bagan yang berbeda.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Hapus seri yang dihasilkan secara default.
	seriesColl.Clear();
	// Buat array nama kategori, dalam tutorial ini kita memiliki dua kategori.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Harap dicatat, array data tidak boleh kosong dan array harus berukuran sama.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyisipkan bagan kolom sederhana ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan bagan kolom, menambahkan beberapa rangkaian dengan kategori dan nilai terkait, dan menyimpan dokumen dengan bagan.

Aspose.Words for .NET menyediakan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan bagan di dokumen Word. Bagan kolom sederhana adalah cara efektif untuk mewakili dan membandingkan data dalam berbagai kategori. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah membuat bagan kolom dengan data khusus, menambahkan beberapa rangkaian untuk perbandingan visual, dan menyesuaikan tampilan bagan sesuai dengan kebutuhan Anda.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengotomatiskan proses pembuatan dokumen dengan bagan kolom, menghemat waktu dan tenaga dalam pembuatan dokumen manual. Pustaka ini menawarkan berbagai jenis bagan, termasuk bagan kolom sederhana, dan menyediakan berbagai opsi penyesuaian untuk menyesuaikan tampilan bagan agar sesuai dengan kebutuhan Anda.

### FAQ

#### Q1. Apa itu bagan kolom?
Bagan kolom adalah jenis bagan yang menampilkan data menggunakan batang vertikal dengan ketinggian bervariasi. Setiap kolom mewakili suatu kategori, dan tinggi kolom sesuai dengan nilai kategori tersebut. Bagan kolom biasanya digunakan untuk membandingkan data di berbagai kategori atau untuk melacak perubahan seiring waktu.

#### Q2. Bisakah saya menambahkan beberapa rangkaian ke bagan kolom?
Ya, menggunakan Aspose.Words untuk .NET, Anda dapat menambahkan beberapa rangkaian ke bagan kolom. Setiap rangkaian mewakili sekumpulan titik data dengan kategori dan nilainya masing-masing. Dengan menambahkan beberapa rangkaian, Anda dapat membandingkan dan menganalisis kumpulan data yang berbeda dalam diagram kolom yang sama, sehingga memberikan tampilan data yang komprehensif.

#### Q3. Bisakah saya menyesuaikan tampilan bagan kolom?
Ya, Aspose.Words untuk .NET memungkinkan Anda menyesuaikan berbagai aspek tampilan bagan kolom. Anda dapat mengubah properti seperti warna rangkaian, label sumbu, label data, dan format area bagan. Pustaka ini menyediakan serangkaian API untuk mengontrol elemen visual bagan dan membuat tampilan yang disesuaikan dengan kebutuhan Anda.

#### Q4. Bisakah saya menyimpan dokumen dengan bagan kolom yang disisipkan dalam format berbeda?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen dengan bagan kolom yang disisipkan dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Bagan kolom yang disisipkan akan disimpan dalam dokumen yang disimpan.

#### Q5. Bisakah saya mengubah data dan tampilan bagan kolom setelah memasukkannya?
Ya, setelah memasukkan bagan kolom ke dalam dokumen, Anda dapat mengubah data dan tampilannya menggunakan API yang disediakan oleh Aspose.Words untuk .NET. Anda bisa memperbarui data seri dengan kategori dan nilai baru, mengubah warna dan format kolom, mengkustomisasi properti sumbu, dan menerapkan berbagai opsi pemformatan untuk membuat bagan dinamis dan menarik secara visual di dokumen Word Anda.