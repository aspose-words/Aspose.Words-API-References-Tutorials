---
title: Format Jumlah Label Data Dalam Bagan
linktitle: Format Jumlah Label Data Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memformat jumlah label data dalam bagan menggunakan Aspose.Words untuk .NET. Sesuaikan format angka untuk label data dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-charts/format-number-of-data-label/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk memformat jumlah label data dalam bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyesuaikan format angka label data.

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

 Selanjutnya, masukkan bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder`. Dalam contoh ini, kita akan menyisipkan diagram garis.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan tiga kategori dan nilainya yang sesuai.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Langkah 4: Sesuaikan format angka label data

 Untuk memformat jumlah label data, akses`DataLabels` koleksi yang terkait dengan seri tersebut.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Dalam contoh ini, kami menetapkan format angka berbeda untuk setiap label data. Label data pertama diformat sebagai mata uang, label kedua sebagai tanggal, dan label ketiga sebagai persentase.

## Langkah 5: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Ini menyelesaikan implementasi pemformatan jumlah label data dalam bagan menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber Format Jumlah Label Data menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Hapus seri yang dihasilkan secara default.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Atau Anda dapat mengatur kode format untuk ditautkan ke sel sumber,
	//Dalam hal ini NumberFormat akan diatur ulang ke umum dan diwarisi dari sel sumber.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara memformat jumlah label data dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat bagan, menambahkan data seri, dan menyesuaikan format angka label data sesuai dengan kebutuhan Anda.

 Aspose.Words untuk .NET menyediakan API komprehensif untuk Pemrosesan Kata dengan bagan di dokumen Word, memungkinkan Anda memanipulasi berbagai aspek bagan, termasuk label data. Dengan mengakses`DataLabels` koleksi yang terkait dengan rangkaian, Anda dapat menyesuaikan format angka label data individual.

API memungkinkan Anda mengontrol tampilan nilai, mengatur format angka yang berbeda untuk setiap label data, dan menautkan format angka ke sel sumber. Fleksibilitas ini memungkinkan Anda menyajikan data numerik dalam grafik dengan format yang diinginkan, seperti simbol mata uang, format tanggal, dan nilai persentase.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat menggabungkan kemampuan pembuatan bagan yang kuat ke dalam aplikasi .NET Anda dan menghasilkan dokumen yang tampak profesional dengan bagan dan label data yang diformat sepenuhnya.

### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen kaya fitur yang memungkinkan pengembang membuat, memanipulasi, dan menyimpan dokumen Word secara terprogram dalam aplikasi .NET. Ini menyediakan berbagai fitur untuk Pemrosesan Kata dengan elemen dokumen, termasuk bagan dan label data.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstal Aspose.Words untuk .NET dengan mengunduhnya menggunakan manajer paket NuGet di Visual Studio. Cukup cari "Apose.Words" di manajer paket NuGet dan instal ke proyek Anda.

#### Q3. Bisakah saya memformat aspek lain dari bagan menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET menyediakan kemampuan luas untuk memformat berbagai aspek bagan. Selain label data, Anda dapat mengkustomisasi tipe bagan, data seri, properti sumbu, legenda, judul, area plot, dan banyak elemen bagan lainnya. API ini menawarkan kontrol menyeluruh atas tampilan dan pemformatan bagan.

#### Q4. Bisakah saya menerapkan format angka berbeda ke label data berbeda dalam rangkaian yang sama?
Ya, Aspose.Words untuk .NET memungkinkan Anda menerapkan format angka berbeda ke label data individual dalam rangkaian yang sama. Dengan mengakses`DataLabels` koleksi yang terkait dengan suatu seri, Anda dapat mengaturnya`FormatCode` properti setiap label data untuk menentukan format angka yang diinginkan. Ini memungkinkan Anda menyajikan nilai numerik dalam format berbeda dalam bagan yang sama.

#### Q5. Bisakah saya menggunakan format angka khusus untuk label data?
 Ya, Aspose.Words untuk .NET mendukung format angka khusus untuk label data. Anda dapat menentukan format angka yang diinginkan dengan mengatur`FormatCode` properti label data ke kode format khusus. Ini memberi Anda fleksibilitas untuk menerapkan berbagai format angka, seperti simbol mata uang, format tanggal, nilai persentase, dan banyak lagi.

#### Q6. Bisakah saya menyimpan bagan dengan label data yang diformat dalam format berbeda?
Ya, Aspose.Words for .NET memungkinkan Anda menyimpan dokumen yang berisi bagan dengan label data yang diformat dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format yang sesuai berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Label data yang diformat akan disimpan dalam dokumen yang disimpan.