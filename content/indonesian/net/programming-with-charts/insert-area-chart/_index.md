---
title: Sisipkan Bagan Area ke dalam Dokumen Word
linktitle: Sisipkan Bagan Area ke dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bagan area ke dalam dokumen menggunakan Aspose.Words untuk .NET. Tambahkan data seri dan simpan dokumen dengan bagan.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-area-chart/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan bagan area ke dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyimpan dokumen.

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

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan bagan area ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan lima titik data dengan tanggal dan nilai yang sesuai.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Ini menyelesaikan implementasi penyisipan bagan area menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Bagan Area menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyisipkan bagan area ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan diagram area, menambahkan data seri, dan menyimpan dokumen dengan diagram.

Aspose.Words for .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan bagan di dokumen Word. Hanya dengan beberapa baris kode, Anda dapat membuat bagan area yang terlihat profesional dan menyesuaikannya sesuai kebutuhan Anda. Bagan area biasanya digunakan untuk menampilkan besaran dan tren data dari waktu ke waktu atau kategori.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengotomatiskan proses pembuatan dokumen dengan bagan area, menghemat waktu dan tenaga dalam pembuatan dokumen manual. Pustaka ini menawarkan beragam tipe bagan dan opsi penyesuaian, memungkinkan Anda membuat bagan yang menarik secara visual dan informatif di dokumen Word Anda.

### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi dokumen Word secara terprogram dalam aplikasi .NET. Ini menyediakan serangkaian API komprehensif untuk Pemrosesan Kata dengan elemen dokumen, termasuk bagan, paragraf, tabel, dan banyak lagi.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Untuk menginstal Aspose.Words untuk .NET, Anda dapat menggunakan manajer paket NuGet di Visual Studio untuk menginstal pustaka langsung ke proyek Anda. Cukup cari "Apose.Words" di manajer paket NuGet dan instal paketnya.

#### Q3. Bisakah saya menyesuaikan tampilan bagan area?
Ya, menggunakan Aspose.Words untuk .NET, Anda dapat menyesuaikan berbagai aspek tampilan bagan area. Anda dapat mengubah properti seperti judul bagan, warna rangkaian, label sumbu, dan format area bagan. Pustaka ini menyediakan serangkaian API untuk mengontrol elemen visual bagan dan membuat tampilan yang disesuaikan dengan kebutuhan Anda.

#### Q4. Bisakah saya menambahkan beberapa rangkaian ke diagram area?
Ya, Anda dapat menambahkan beberapa rangkaian ke bagan area menggunakan Aspose.Words untuk .NET. Setiap rangkaian mewakili sekumpulan titik data yang diplot pada bagan. Anda dapat menambahkan seri dengan kumpulan data berbeda dan menyesuaikan setiap seri satu per satu, termasuk namanya, titik data, dan tampilannya.

#### Q5. Bisakah saya menyimpan dokumen dengan bagan area yang disisipkan dalam format berbeda?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen dengan bagan area yang disisipkan dalam berbagai format, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Bagan area yang disisipkan akan disimpan dalam dokumen yang disimpan.

#### Q6. Bisakah saya mengubah data dan tampilan diagram area setelah memasukkannya?
Ya, setelah memasukkan diagram area ke dalam dokumen, Anda dapat mengubah data dan tampilannya menggunakan API yang disediakan oleh Aspose.Words untuk .NET. Anda bisa memperbarui data seri, mengubah tipe bagan, mengkustomisasi properti sumbu, dan menerapkan opsi pemformatan untuk membuat bagan dinamis dan interaktif di dokumen Word Anda.