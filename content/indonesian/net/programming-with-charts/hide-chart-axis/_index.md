---
title: Sembunyikan Sumbu Bagan Dalam Dokumen Word
linktitle: Sembunyikan Sumbu Bagan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyembunyikan sumbu bagan dalam dokumen menggunakan Aspose.Words untuk .NET. Sembunyikan sumbu untuk tampilan grafik yang lebih bersih dan fokus.
type: docs
weight: 10
url: /id/net/programming-with-charts/hide-chart-axis/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyembunyikan sumbu bagan dalam dokumen. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan menyembunyikan sumbu bagan.

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

 Selanjutnya, masukkan bagan ke dalam dokumen menggunakan`InsertChart` metode`DocumentBuilder`. Dalam contoh ini, kita akan menyisipkan bagan kolom.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Tambahkan data seri ke bagan

Tambahkan data seri ke bagan. Dalam contoh ini, kita akan menambahkan lima item dan nilainya yang sesuai.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Langkah 4: Sembunyikan sumbu grafik

 Untuk menyembunyikan sumbu grafik, akses`AxisY` properti bagan dan atur`Hidden`properti ke`true`.

```csharp
chart.AxisY.Hidden = true;
```

Dalam contoh ini, kami menyembunyikan sumbu Y pada grafik.

## Langkah 5: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Ini menyelesaikan implementasi menyembunyikan sumbu bagan menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sembunyikan Sumbu Bagan menggunakan Aspose.Words untuk .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyembunyikan sumbu bagan di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber yang disediakan, Anda dapat membuat bagan, menambahkan data rangkaian, dan menyembunyikan sumbu bagan untuk mencapai efek visual yang diinginkan.

 Aspose.Words untuk .NET menyediakan API komprehensif untuk Pemrosesan Kata dengan bagan di dokumen Word, memungkinkan Anda memanipulasi berbagai aspek bagan, termasuk properti sumbu. Dengan mengakses`AxisY` properti bagan, Anda dapat menyembunyikan sumbu Y untuk menghapusnya dari visualisasi bagan.

Menyembunyikan sumbu bagan dapat berguna saat Anda ingin fokus pada data bagan tanpa gangguan garis sumbu dan label. Ini memberikan tampilan yang lebih bersih dan minimalis pada grafik.

Dengan menggunakan Aspose.Words untuk .NET, Anda dapat dengan mudah menggabungkan kemampuan pembuatan bagan ke dalam aplikasi .NET Anda dan menghasilkan dokumen yang terlihat profesional dengan bagan yang disesuaikan dan sumbu bagan tersembunyi.

### FAQ

#### Q1. Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen canggih yang memungkinkan pengembang membuat, memanipulasi, dan menyimpan dokumen Word secara terprogram dalam aplikasi .NET. Ini menyediakan berbagai fitur untuk Pemrosesan Kata dengan elemen dokumen, termasuk bagan dan sumbu bagan.

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstal Aspose.Words untuk .NET dengan mengunduhnya menggunakan manajer paket NuGet di Visual Studio. Cukup cari "Aspose.Words" di manajer paket NuGet dan instal ke proyek Anda.

#### Q3. Bisakah saya menyembunyikan sumbu X dan sumbu Y pada grafik?
 Ya, Anda dapat menyembunyikan sumbu X dan sumbu Y pada bagan menggunakan Aspose.Words untuk .NET. Untuk menyembunyikan sumbu X, Anda dapat mengakses`AxisX` properti bagan dan atur`Hidden`properti ke`true` . Demikian pula, untuk menyembunyikan sumbu Y, Anda dapat mengakses`AxisY` properti dan atur`Hidden`properti ke`true`. Hal ini memungkinkan Anda untuk menghapus kedua sumbu dari visualisasi grafik.

#### Q4. Bisakah saya menampilkan sumbu lagi setelah menyembunyikannya?
Ya, Anda dapat menampilkan kembali sumbu bagan setelah menyembunyikannya menggunakan Aspose.Words untuk .NET. Untuk menampilkan sumbu tersembunyi, cukup atur`Hidden` milik yang bersangkutan`AxisX` atau`AxisY` objek untuk`false`. Ini akan membuat sumbu terlihat lagi di grafik.

#### Q5. Bisakah saya menyesuaikan properti lain dari sumbu bagan?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyesuaikan berbagai properti sumbu bagan, seperti judul sumbu, label, warna garis, dan banyak lagi. Dengan mengakses`AxisX` Dan`AxisY` properti bagan, Anda dapat mengubah properti seperti`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, dan banyak lagi. Ini memberi Anda kontrol menyeluruh atas tampilan dan perilaku sumbu grafik.

#### Q6. Bisakah saya menyimpan grafik dengan sumbu tersembunyi dalam format file berbeda?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyimpan dokumen yang berisi bagan dengan sumbu tersembunyi dalam berbagai format file, seperti DOCX, PDF, HTML, dan lainnya. Anda dapat memilih format keluaran yang diinginkan berdasarkan kebutuhan Anda dan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen. Sumbu tersembunyi akan disimpan dalam dokumen yang disimpan.