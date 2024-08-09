---
title: Format Jumlah Label Data Dalam Bagan
linktitle: Format Jumlah Label Data Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memformat label data dalam bagan menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurnakan dokumen Word Anda dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-charts/format-number-of-data-label/
---
## Perkenalan

Membuat dokumen yang menarik dan informatif sering kali melibatkan penyertaan bagan dengan label data yang diformat dengan baik. Jika Anda seorang pengembang .NET yang ingin menyempurnakan dokumen Word Anda dengan bagan canggih, Aspose.Words for .NET adalah perpustakaan fantastis untuk membantu Anda mencapainya. Tutorial ini akan memandu Anda melalui proses pemformatan label angka dalam bagan menggunakan Aspose.Words untuk .NET, langkah demi langkah.

## Prasyarat

Sebelum mendalami kodenya, ada beberapa prasyarat yang perlu Anda miliki:

-  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Jika Anda belum menginstalnya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan .NET. Visual Studio sangat direkomendasikan.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# sangat penting karena tutorial ini melibatkan penulisan dan pemahaman kode C#.
-  Lisensi Sementara: Untuk menggunakan Aspose.Words tanpa batasan apa pun, Anda bisa mendapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/).

Sekarang, mari selami proses langkah demi langkah dalam memformat label angka dalam bagan.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.Words untuk .NET. Tambahkan baris berikut di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Sebelum Anda dapat mulai memanipulasi dokumen Word Anda, Anda perlu menentukan direktori tempat dokumen Anda akan disimpan. Ini penting untuk operasi penyimpanan nanti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Inisialisasi Dokumen dan DocumentBuilder

 Langkah selanjutnya adalah inisialisasi yang baru`Document` dan sebuah`DocumentBuilder` . Itu`DocumentBuilder` adalah kelas pembantu yang memungkinkan kita membuat konten dokumen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Masukkan Bagan ke dalam Dokumen

 Sekarang, mari masukkan bagan ke dalam dokumen menggunakan`DocumentBuilder`. Dalam tutorial ini, kita akan menggunakan diagram Garis sebagai contoh.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Di sini, kita menyisipkan diagram Garis dengan lebar dan tinggi tertentu, dan mengatur judul diagram.

## Langkah 4: Hapus Seri Default dan Tambahkan Seri Baru

Secara default, bagan akan memiliki beberapa rangkaian yang telah dibuat sebelumnya. Kita perlu menghapusnya dan menambahkan rangkaian kita sendiri dengan titik data tertentu.

```csharp
// Hapus seri yang dihasilkan secara default.
chart.Series.Clear();

// Tambahkan seri baru dengan titik data khusus.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Langkah 5: Aktifkan Label Data

Untuk menampilkan label data pada grafik, kita perlu mengaktifkannya untuk rangkaian kita.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Langkah 6: Format Label Data

Inti dari tutorial ini adalah memformat label data. Kita dapat menerapkan format angka yang berbeda untuk setiap label data satu per satu.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Format mata uang
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Format tanggal
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Format persentase
```

 Selain itu, Anda bisa menautkan format label data ke sel sumber. Saat dihubungkan, itu`NumberFormat` akan diatur ulang ke umum dan diwarisi dari sel sumber.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Langkah 7: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Tindakan ini akan menyimpan dokumen Anda dengan nama tertentu dan memastikan bagan Anda dengan label data yang diformat tetap dipertahankan.

## Kesimpulan

Memformat label data dalam bagan menggunakan Aspose.Words untuk .NET dapat meningkatkan keterbacaan dan profesionalisme dokumen Word Anda secara signifikan. Dengan mengikuti panduan langkah demi langkah ini, Anda kini dapat membuat bagan, menambahkan seri data, dan memformat label data untuk memenuhi kebutuhan Anda. Aspose.Words for .NET adalah alat canggih yang memungkinkan penyesuaian ekstensif dan otomatisasi dokumen Word, menjadikannya aset yang sangat berharga bagi pengembang .NET.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang kuat untuk membuat, memanipulasi, dan mengonversi dokumen Word secara terprogram menggunakan C#.

### Bisakah saya memformat jenis bagan lain dengan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET mendukung berbagai tipe bagan, termasuk batang, kolom, pai, dan banyak lagi.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words untuk .NET?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Apakah mungkin untuk menghubungkan label data ke sel sumber di Excel?
Ya, Anda bisa menautkan label data ke sel sumber, memungkinkan format angka diwarisi dari sel sumber.

### Di mana saya dapat menemukan dokumentasi lebih rinci untuk Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi yang komprehensif[Di Sini](https://reference.aspose.com/words/net/).
