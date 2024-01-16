---
title: Sisipkan Bagan Kolom Dalam Dokumen Word
linktitle: Sisipkan Bagan Kolom Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bagan kolom ke dalam dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-column-chart/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan bagan kolom ke dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyimpan dokumen.

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

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan dua kategori dan nilainya yang sesuai.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Ini menyelesaikan implementasi penyisipan bagan kolom menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Bagan Kolom menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyisipkan bagan kolom ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda bisa membuat dokumen baru, menyisipkan bagan kolom, menambahkan data seri, dan menyimpan dokumen dengan bagan.

Aspose.Words for .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan bagan di dokumen Word. Bagan kolom biasanya digunakan untuk menampilkan dan membandingkan data di berbagai kategori atau grup. Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah membuat bagan kolom yang memvisualisasikan data Anda secara efektif dan memberikan wawasan berharga.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengotomatiskan proses pembuatan dokumen dengan bagan kolom, menghemat waktu dan tenaga dalam pembuatan dokumen manual. Pustaka ini menawarkan beragam tipe bagan dan opsi penyesuaian, memungkinkan Anda membuat bagan yang menarik secara visual dan kaya data di dokumen Word Anda.

### FAQ

#### Q1. Apa itu bagan kolom?
Bagan kolom adalah jenis bagan yang mewakili data dalam batang atau kolom vertikal. Setiap kolom biasanya mewakili suatu kategori atau grup, dan tinggi atau panjang kolom menunjukkan nilai data yang terkait dengan kategori tersebut. Bagan kolom biasanya digunakan untuk membandingkan data di berbagai kategori atau untuk melacak perubahan seiring waktu.

#### Q2. Bisakah saya menambahkan beberapa rangkaian ke bagan kolom?
Ya, Anda dapat menambahkan beberapa rangkaian ke bagan kolom menggunakan Aspose.Words untuk .NET. Setiap rangkaian mewakili sekumpulan titik data dengan kategori dan nilainya masing-masing. Dengan menambahkan beberapa rangkaian, Anda dapat membandingkan dan menganalisis kumpulan data yang berbeda dalam diagram yang sama, sehingga memberikan tampilan data yang komprehensif.

#### Q3. Bisakah saya menyesuaikan tampilan bagan kolom?
Ya, menggunakan Aspose.Words untuk .NET, Anda dapat menyesuaikan berbagai aspek tampilan bagan kolom. Anda dapat mengubah properti seperti warna rangkaian, label sumbu, lebar kolom, dan format area bagan. Pustaka ini menyediakan serangkaian API untuk mengontrol elemen visual bagan dan membuat tampilan yang disesuaikan dengan kebutuhan Anda.

#### Q4. Bisakah saya menyimpan dokumen dengan bagan kolom yang disisipkan dalam format berbeda?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen dengan bagan kolom yang disisipkan dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Bagan kolom yang disisipkan akan disimpan dalam dokumen yang disimpan.

#### Q5. Bisakah saya mengubah data dan tampilan bagan kolom setelah memasukkannya?
Ya, setelah memasukkan bagan kolom ke dalam dokumen, Anda dapat mengubah data dan tampilannya menggunakan API yang disediakan oleh Aspose.Words untuk .NET. Anda bisa memperbarui data seri, mengubah warna kolom, mengkustomisasi properti sumbu, dan menerapkan opsi pemformatan untuk membuat bagan dinamis dan interaktif di dokumen Word Anda.