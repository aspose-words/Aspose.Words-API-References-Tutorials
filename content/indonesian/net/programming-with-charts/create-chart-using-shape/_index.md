---
title: Buat & Sesuaikan Bagan Menggunakan Bentuk
linktitle: Buat & Sesuaikan Bagan Menggunakan Bentuk
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dan mengkustomisasi bagan di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk visualisasi data.
type: docs
weight: 10
url: /id/net/programming-with-charts/create-chart-using-shape/
---
## Perkenalan

Membuat dan menyesuaikan bagan dalam dokumen Anda adalah keterampilan penting di dunia berbasis data saat ini. Bagan dapat membantu memvisualisasikan data, membuat informasi kompleks lebih mudah dicerna. Aspose.Words for .NET adalah perpustakaan canggih yang memungkinkan Anda membuat dan memanipulasi dokumen Word secara terprogram. Dalam tutorial ini, kami akan memandu Anda melalui proses membuat dan mengkustomisasi diagram garis menggunakan Aspose.Words untuk .NET. Di akhir panduan ini, Anda akan dapat membuat bagan yang terlihat profesional dengan mudah.

## Prasyarat

Sebelum mendalami kodenya, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET Library: Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/words/net/).
- Visual Studio: Versi apa pun yang mendukung .NET.
- Pengetahuan Dasar C#: Memahami dasar-dasar C# akan membantu Anda mengikuti tutorial.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan. Langkah ini penting karena memungkinkan Anda menggunakan kelas dan metode yang disediakan oleh Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Langkah 1: Buat Dokumen Baru

Pertama, Anda perlu membuat dokumen Word baru. Dokumen ini akan berfungsi sebagai kanvas untuk bagan Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bagan

 Selanjutnya, Anda akan memasukkan diagram garis ke dalam dokumen. Itu`DocumentBuilder.InsertChart` metode digunakan untuk tujuan ini.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Sesuaikan Judul Bagan

Menyesuaikan judul bagan dapat membantu memberikan konteks pada data yang ditampilkan. Anda dapat menampilkan judul dan mengatur teksnya menggunakan kode berikut:

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
// Harap dicatat jika nilai nol atau kosong ditentukan sebagai teks judul, judul yang dibuat secara otomatis akan ditampilkan.
```

## Langkah 4: Sesuaikan Posisi Legenda

Legenda membantu mengidentifikasi seri data yang berbeda dalam bagan Anda. Anda dapat menyesuaikan posisi dan pengaturan overlaynya seperti ini:

```csharp
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Langkah 5: Simpan Dokumen

Terakhir, Anda perlu menyimpan dokumen tersebut. Langkah ini memastikan bahwa semua perubahan Anda ditulis ke file.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

## Kesimpulan

Dalam tutorial ini, kita membahas cara membuat dan mengkustomisasi diagram garis di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah, kini Anda dapat membuat bagan yang menarik secara visual yang mengomunikasikan data Anda secara efektif. Aspose.Words untuk .NET menawarkan berbagai opsi penyesuaian, memungkinkan Anda menyesuaikan bagan dengan kebutuhan spesifik Anda.

## FAQ

### Bisakah saya menggunakan Aspose.Words for .NET untuk membuat tipe bagan lainnya?

 Ya, Aspose.Words untuk .NET mendukung berbagai jenis bagan, termasuk diagram batang, diagram lingkaran, dan banyak lagi. Anda dapat menjelajahi dokumentasinya[Di Sini](https://reference.aspose.com/words/net/) untuk lebih jelasnya.

### Bagaimana saya bisa mencoba Aspose.Words untuk .NET sebelum membeli?

 Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/). Ini memungkinkan Anda menguji perpustakaan dan fitur-fiturnya sebelum melakukan pembelian.

### Apakah ada cara untuk mendapatkan dukungan jika saya mengalami masalah?

 Sangat. Anda dapat mengakses dukungan melalui forum komunitas Aspose[Di Sini](https://forum.aspose.com/c/words/8)Komunitas dan staf Aspose sangat responsif.

### Bagaimana cara membeli lisensi Aspose.Words untuk .NET?

 Anda dapat membeli lisensi langsung dari situs Aspose[Di Sini](https://purchase.aspose.com/buy). Ada berbagai pilihan lisensi untuk memenuhi kebutuhan yang berbeda.

### Bagaimana jika saya memerlukan izin sementara untuk proyek jangka pendek?

 Aspose menawarkan lisensi sementara, yang dapat Anda minta[Di Sini](https://purchase.aspose.com/temporary-license/).
