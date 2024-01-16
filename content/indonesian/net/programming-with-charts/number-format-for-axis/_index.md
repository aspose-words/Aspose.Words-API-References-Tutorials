---
title: Format Angka Untuk Sumbu Dalam Bagan
linktitle: Format Angka Untuk Sumbu Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur format angka untuk sumbu dalam bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/number-format-for-axis/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengatur format angka untuk sumbu dalam bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, menambahkan data seri, dan memformat label sumbu.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Langkah 4: Format label sumbu

 Untuk mengatur format angka pada label sumbu Y, akses`AxisY` properti bagan dan atur`NumberFormat.FormatCode` properti ke format yang diinginkan. Dalam contoh ini, kami mengatur format ke "#,##0" untuk menampilkan angka dengan pemisah ribuan.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Langkah 5: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Ini menyelesaikan implementasi pengaturan format angka untuk sumbu menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber Format Angka Untuk Sumbu menggunakan Aspose.Words untuk .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur format angka untuk sumbu dalam bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan bagan kolom, menambahkan data seri, dan memformat label sumbu untuk menampilkan angka dalam format tertentu.

Aspose.Words untuk .NET menyediakan fitur canggih untuk menyesuaikan tampilan bagan di dokumen Word. Dengan mengatur format angka untuk label sumbu, Anda dapat mengontrol cara angka ditampilkan, termasuk opsi seperti tempat desimal, pemisah ribuan, simbol mata uang, dan lainnya. Hal ini memungkinkan Anda menyajikan data numerik dengan cara yang jelas dan bermakna.

Dengan Aspose.Words untuk .NET, Anda memiliki fleksibilitas untuk memformat berbagai aspek bagan, termasuk label sumbu. Dengan mengatur format angka untuk sumbu, Anda dapat memastikan konsistensi dan meningkatkan keterbacaan bagan, sehingga memudahkan pengguna untuk menafsirkan nilai yang diwakili.

### FAQ

#### Q1. Apa format angka untuk sumbu dalam grafik?
Format angka untuk sumbu dalam bagan mengacu pada format yang diterapkan pada nilai numerik yang ditampilkan pada sumbu. Ini memungkinkan Anda mengontrol bagaimana angka disajikan, termasuk opsi seperti tempat desimal, pemisah ribuan, simbol mata uang, tanda persentase, dan banyak lagi. Dengan mengatur format angka, Anda dapat menyesuaikan tampilan data numerik dalam bagan agar sesuai dengan kebutuhan spesifik Anda.

#### Q2. Bagaimana cara mengatur format angka untuk label sumbu?
 Untuk mengatur format angka untuk label sumbu dalam bagan menggunakan Aspose.Words untuk .NET, Anda dapat mengakses`AxisY` properti bagan dan atur`NumberFormat.FormatCode`properti ke kode format yang diinginkan. Kode format mengikuti sintaks pola format numerik standar dan menentukan bagaimana angka ditampilkan. Misalnya, Anda dapat menggunakan "#,##0.00" untuk menampilkan angka dengan dua tempat desimal dan pemisah ribuan.

#### Q3. Bisakah saya mengatur format angka yang berbeda untuk label sumbu X dan sumbu Y?
Ya, Anda dapat mengatur format angka berbeda untuk label sumbu X dan sumbu Y menggunakan Aspose.Words untuk .NET. Akses sumbu masing-masing (`AxisX` untuk sumbu X atau`AxisY` untuk sumbu Y) pada grafik dan modifikasi`NumberFormat.FormatCode` properti secara individual untuk setiap sumbu. Hal ini memungkinkan Anda menerapkan format angka berbeda pada label di setiap sumbu berdasarkan kebutuhan spesifik Anda.

#### Q4. Apa sajakah kode format angka umum yang dapat saya gunakan?
Aspose.Words for .NET mendukung berbagai kode format angka yang dapat Anda gunakan untuk memformat label sumbu dalam bagan. Beberapa kode format umum meliputi:

- `0` atau`#` - Menampilkan angka tanpa tempat desimal.
- `0.00` atau`#.00` - Menampilkan nomor dengan dua tempat desimal.
- `#,##0` Menampilkan angka dengan pemisah ribuan.
- `"€"0.00` - Menampilkan nomor dengan simbol mata uang Euro dan dua tempat desimal.
- `"%"0` - Menampilkan angka sebagai persentase.

 Anda dapat menemukan informasi lebih lanjut tentang nomor[kode format](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) di Referensi API Aspose.Words untuk .NET.

#### Q5. Bisakah saya menyesuaikan properti lain dari label sumbu?
Ya, Aspose.Words untuk .NET menyediakan berbagai properti untuk menyesuaikan tampilan dan perilaku label sumbu. Selain format angka, Anda dapat mengubah properti seperti font, ukuran, warna, orientasi, perataan, dan lainnya. Ini memungkinkan Anda untuk sepenuhnya menyesuaikan label sumbu agar sesuai dengan gaya dan persyaratan presentasi yang Anda inginkan.