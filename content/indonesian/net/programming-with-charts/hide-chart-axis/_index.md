---
title: Sembunyikan Sumbu Bagan Dalam Dokumen Word
linktitle: Sembunyikan Sumbu Bagan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyembunyikan sumbu bagan di dokumen Word menggunakan Aspose.Words untuk .NET dengan tutorial langkah demi langkah kami yang mendetail.
type: docs
weight: 10
url: /id/net/programming-with-charts/hide-chart-axis/
---
## Perkenalan

Membuat dokumen Word yang dinamis dan menarik secara visual sering kali melibatkan penggabungan bagan dan grafik. Salah satu skenario tersebut mungkin memerlukan penyembunyian sumbu bagan untuk presentasi yang lebih rapi. Aspose.Words for .NET menyediakan API yang komprehensif dan mudah digunakan untuk tugas-tugas tersebut. Tutorial ini akan memandu Anda melalui langkah-langkah untuk menyembunyikan sumbu bagan di dokumen Word menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk .NET: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Setiap IDE yang mendukung pengembangan .NET, seperti Visual Studio.
- .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
- Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace

Untuk mulai bekerja dengan Aspose.Words untuk .NET, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah diikuti.

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

Langkah pertama melibatkan pembuatan dokumen Word baru dan menginisialisasi objek DocumentBuilder.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Pada langkah ini, kita menentukan jalur dimana dokumen akan disimpan. Kami kemudian membuat yang baru`Document` objek dan a`DocumentBuilder` keberatan untuk mulai membuat dokumen kita.

## Langkah 2: Sisipkan Bagan

 Selanjutnya, kita akan menyisipkan bagan ke dalam dokumen menggunakan`DocumentBuilder` obyek.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 Di sini, kami menyisipkan bagan kolom dengan dimensi tertentu. Itu`InsertChart` metode mengembalikan a`Shape` objek yang berisi grafik.

## Langkah 3: Hapus Seri yang Ada

Sebelum menambahkan data baru ke grafik, kita perlu menghapus semua rangkaian yang ada.

```csharp
chart.Series.Clear();
```

Langkah ini memastikan bahwa data default apa pun dalam bagan dihapus, sehingga memberi jalan bagi data baru yang akan kita tambahkan berikutnya.

## Langkah 4: Tambahkan Data Seri

Sekarang, mari tambahkan seri data kita sendiri ke bagan.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

Pada langkah ini, kami menambahkan rangkaian berjudul "Aspose Seri 1" dengan kategori dan nilai yang sesuai.

## Langkah 5: Sembunyikan Sumbu Y

 Untuk menyembunyikan sumbu Y pada grafik, kita cukup mengaturnya`Hidden` properti sumbu Y ke`true`.

```csharp
chart.AxisY.Hidden = true;
```

Baris kode ini menyembunyikan sumbu Y, sehingga tidak terlihat dalam grafik.

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Perintah ini menyimpan dokumen Word dengan bagan ke jalur yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyembunyikan sumbu bagan di dokumen Word menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memudahkan manipulasi dokumen Word secara terprogram. Dengan mengikuti langkah-langkah ini, Anda dapat membuat dokumen yang disesuaikan dan terlihat profesional dengan sedikit usaha.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah API yang kuat untuk membuat, mengedit, mengonversi, dan memanipulasi dokumen Word dalam aplikasi .NET.

### Bisakah saya menyembunyikan sumbu X dan Y dalam grafik?
 Ya, Anda dapat menyembunyikan kedua sumbu dengan menyetel`Hidden` milik keduanya`AxisX`Dan`AxisY` ke`true`.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lainnya?
 Anda dapat menemukan dokumentasi terperinci di Aspose.Words untuk .NET[Di Sini](https://reference.aspose.com/words/net/).

### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Words untuk .NET?
 Anda bisa mendapatkan dukungan dari komunitas Aspose[Di Sini](https://forum.aspose.com/c/words/8).
