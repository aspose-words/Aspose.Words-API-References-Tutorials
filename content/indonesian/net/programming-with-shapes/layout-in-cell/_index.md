---
title: Tata Letak Dalam Sel
linktitle: Tata Letak Dalam Sel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur tata letak di sel menggunakan Aspose.Words untuk .NET dengan panduan komprehensif ini. Sempurna untuk pengembang yang ingin menyesuaikan dokumen Word.
type: docs
weight: 10
url: /id/net/programming-with-shapes/layout-in-cell/
---
## Perkenalan

Jika Anda ingin menyempurnakan tata letak sel tabel di dokumen Word secara terprogram, Anda berada di tempat yang tepat. Hari ini, kita akan mendalami cara mengatur tata letak di sel menggunakan Aspose.Words untuk .NET. Kami akan memberikan contoh praktis, menguraikannya langkah demi langkah sehingga Anda dapat mengikutinya dengan mudah.

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Jika belum, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Anda memerlukan lingkungan pengembangan yang diatur dengan .NET. Visual Studio adalah pilihan tepat jika Anda mencari rekomendasi.
3. Pengetahuan Dasar C#: Meskipun saya akan menjelaskan setiap langkah, pemahaman dasar C# akan membantu Anda mengikutinya dengan lebih mudah.
4.  Direktori Dokumen: Siapkan jalur direktori tempat Anda akan menyimpan dokumen Anda. Kami akan menyebut ini sebagai`YOUR DOCUMENT DIRECTORY`.

## Impor Namespace

Untuk memulai, pastikan Anda mengimpor namespace yang diperlukan dalam proyek Anda:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola.

## Langkah 1: Buat Dokumen Baru

 Pertama, kita akan membuat dokumen Word baru dan menginisialisasi a`DocumentBuilder` objek untuk membantu kami membangun konten kami.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Mulai Tabel dan Atur Format Baris

Kita akan mulai membuat tabel dan menentukan aturan tinggi dan tinggi untuk baris.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Langkah 3: Sisipkan Sel dan Isi dengan Konten

Selanjutnya, kita melakukan loop untuk memasukkan sel ke dalam tabel. Untuk setiap 7 sel, kita akan mengakhiri baris untuk membuat sel baru.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Langkah 4: Tambahkan Bentuk Tanda Air

 Sekarang, mari tambahkan tanda air ke dokumen kita. Kami akan membuat`Shape` objek dan mengatur propertinya.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Menampilkan bentuk di luar sel tabel jika akan ditempatkan ke dalam sel.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Langkah 5: Sesuaikan Tampilan Tanda Air

Kami selanjutnya akan menyesuaikan tampilan tanda air dengan mengatur properti warna dan teksnya.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Langkah 6: Masukkan Tanda Air ke dalam Dokumen

Kami akan menemukan proses terakhir dalam dokumen dan memasukkan tanda air pada posisi itu.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Langkah 7: Optimalkan Dokumen untuk Word 2010

Untuk memastikan kompatibilitas, kami akan mengoptimalkan dokumen untuk Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Langkah 8: Simpan Dokumen

Terakhir, kami akan menyimpan dokumen kami ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat dokumen Word dengan tata letak tabel yang disesuaikan dan menambahkan tanda air menggunakan Aspose.Words untuk .NET. Tutorial ini bertujuan untuk memberikan panduan langkah demi langkah yang jelas untuk membantu Anda memahami setiap bagian proses. Dengan keterampilan ini, kini Anda dapat membuat dokumen Word yang lebih canggih dan disesuaikan secara terprogram.

## FAQ

### Bisakah saya menggunakan font berbeda untuk teks tanda air?
 Ya, Anda dapat mengubah font dengan mengatur`watermark.TextPath.FontFamily` properti ke font yang Anda inginkan.

### Bagaimana cara mengatur posisi tanda air?
 Anda dapat memodifikasi`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , Dan`VerticalAlignment` properti untuk menyesuaikan posisi tanda air.

### Apakah mungkin menggunakan gambar sebagai pengganti teks untuk tanda air?
 Sangat! Anda dapat membuat`Shape` dengan tipenya`ShapeType.Image` dan atur gambarnya menggunakan`ImageData.SetImage` metode.

### Bisakah saya membuat tabel dengan tinggi baris yang bervariasi?
Ya, Anda dapat mengatur ketinggian berbeda untuk setiap baris dengan mengubah`RowFormat.Height` properti sebelum memasukkan sel ke dalam baris itu.

### Bagaimana cara menghapus tanda air dari dokumen?
 Anda dapat menghapus tanda air dengan menempatkannya di kumpulan bentuk dokumen dan memanggil`Remove` metode.