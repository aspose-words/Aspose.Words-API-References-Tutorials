---
title: Sisipkan Bagan Gelembung di Dokumen Word
linktitle: Sisipkan Bagan Gelembung di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bagan gelembung ke dalam dokumen menggunakan Aspose.Words untuk .NET. Tambahkan data seri dengan nilai X, Y, dan ukuran gelembung.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-bubble-chart/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan bagan gelembung ke dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyimpan dokumen.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan bagan gelembung ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan tiga titik data dengan nilai X, Y, dan ukuran gelembung yang sesuai.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Ini menyelesaikan implementasi penyisipan bagan gelembung menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Bagan Gelembung menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyisipkan bagan gelembung ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan bagan gelembung, menambahkan data seri, dan menyimpan dokumen dengan bagan.

Aspose.Words for .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan bagan di dokumen Word. Bagan gelembung ideal untuk memvisualisasikan data tiga dimensi, di mana setiap titik data diwakili oleh gelembung dengan koordinat X dan Y serta nilai ukuran. Dengan Aspose.Words untuk .NET, Anda dapat membuat bagan gelembung dinamis dan informatif yang menyempurnakan representasi visual data Anda.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengotomatiskan proses pembuatan dokumen dengan bagan gelembung, menghemat waktu dan tenaga dalam pembuatan dokumen manual. Pustaka ini menawarkan beragam tipe bagan dan opsi penyesuaian, memungkinkan Anda membuat bagan yang menarik secara visual dan kaya data di dokumen Word Anda.

### FAQ

#### Q1. Apa itu diagram gelembung?
Bagan gelembung adalah jenis bagan yang menampilkan data tiga dimensi menggunakan gelembung atau bola. Setiap titik data diwakili oleh sebuah gelembung, dengan koordinat X dan Y menentukan posisi gelembung pada grafik, dan ukuran gelembung mewakili dimensi ketiga dari data. Bagan gelembung berguna untuk memvisualisasikan hubungan dan pola di antara banyak variabel.

#### Q2. Bisakah saya menambahkan beberapa rangkaian ke bagan gelembung?
Ya, Anda dapat menambahkan beberapa rangkaian ke bagan gelembung menggunakan Aspose.Words untuk .NET. Setiap rangkaian mewakili sekumpulan titik data dengan nilai ukuran X, Y, dan gelembungnya masing-masing. Dengan menambahkan beberapa rangkaian, Anda dapat membandingkan dan menganalisis kumpulan data yang berbeda dalam diagram yang sama, sehingga memberikan tampilan data yang komprehensif.

#### Q3. Bisakah saya menyesuaikan tampilan bagan gelembung?
Ya, menggunakan Aspose.Words untuk .NET, Anda dapat menyesuaikan berbagai aspek tampilan bagan gelembung. Anda dapat mengubah properti seperti warna rangkaian, ukuran gelembung, label sumbu, dan format area bagan. Pustaka ini menyediakan serangkaian API untuk mengontrol elemen visual bagan dan membuat tampilan yang disesuaikan dengan kebutuhan Anda.

#### Q4. Bisakah saya menyimpan dokumen dengan bagan gelembung yang disisipkan dalam format berbeda?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen dengan bagan gelembung yang disisipkan dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Bagan gelembung yang disisipkan akan disimpan dalam dokumen yang disimpan.

#### Q5. Bisakah saya mengubah data dan tampilan bagan gelembung setelah memasukkannya?
Ya, setelah memasukkan bagan gelembung ke dalam dokumen, Anda dapat mengubah data dan tampilannya menggunakan API yang disediakan oleh Aspose.Words untuk .NET. Anda dapat memperbarui data seri, mengubah ukuran gelembung, mengkustomisasi properti sumbu, dan menerapkan opsi pemformatan untuk membuat bagan dinamis dan interaktif di dokumen Word Anda.