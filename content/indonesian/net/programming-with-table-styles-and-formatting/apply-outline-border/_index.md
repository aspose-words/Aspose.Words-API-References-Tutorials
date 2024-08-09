---
title: Terapkan Batas Garis Besar
linktitle: Terapkan Batas Garis Besar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerapkan batas kerangka ke tabel di Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk pemformatan tabel yang sempurna.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/apply-outline-border/
---
## Perkenalan

Dalam tutorial hari ini, kita mendalami dunia manipulasi dokumen menggunakan Aspose.Words untuk .NET. Secara khusus, kita akan mempelajari cara menerapkan batas kerangka ke tabel di dokumen Word. Ini adalah keterampilan yang luar biasa untuk dimiliki dalam perangkat Anda jika Anda sering bekerja dengan pembuatan dan pemformatan dokumen otomatis. Jadi, mari kita mulai perjalanan untuk membuat meja Anda tidak hanya fungsional tetapi juga menarik secara visual.

## Prasyarat

Sebelum kita beralih ke kode, ada beberapa hal yang Anda perlukan:

1.  Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Lingkungan pengembangan yang sesuai seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman mendasar tentang C# akan membantu Anda mengikuti tutorial.

## Impor Namespace

Untuk memulainya, pastikan Anda telah mengimpor namespace yang diperlukan. Ini penting untuk mengakses fungsionalitas Aspose.Words.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dikelola.

## Langkah 1: Muat Dokumen

Pertama, kita perlu memuat dokumen Word yang berisi tabel yang ingin kita format.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

 Pada langkah ini, kami menggunakan`Document` kelas dari Aspose.Words untuk memuat dokumen yang ada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat dokumen Anda disimpan.

## Langkah 2: Akses Tabel

Selanjutnya, kita perlu mengakses tabel tertentu yang ingin kita format. 

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

 Di Sini,`GetChild` metode mengambil tabel pertama dalam dokumen. Parameternya`NodeType.Table, 0, true` pastikan kita mendapatkan tipe node yang benar.

## Langkah 3: Sejajarkan Tabel

Sekarang, mari kita ratakan tengah tabel pada halaman.

```csharp
table.Alignment = TableAlignment.Center;
```

Langkah ini memastikan meja berada di tengah dengan rapi, sehingga memberikan tampilan profesional.

## Langkah 4: Hapus Batas yang Ada

Sebelum kita menerapkan perbatasan baru, kita perlu menghapus perbatasan yang sudah ada.

```csharp
table.ClearBorders();
```

Menghapus perbatasan memastikan bahwa perbatasan baru kami diterapkan dengan bersih tanpa ada gangguan gaya lama.

## Langkah 5: Tetapkan Batas Garis Besar

Sekarang, mari terapkan batas garis hijau pada tabel.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

 Setiap jenis batas (kiri, kanan, atas, bawah) diatur satu per satu. Kami menggunakan`LineStyle.Single` untuk garis padat,`1.5` untuk lebar garis, dan`Color.Green` untuk warna perbatasan.

## Langkah 6: Terapkan Shading Sel

Untuk membuat tabel lebih menarik secara visual, mari isi sel dengan warna hijau muda.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

 Di Sini,`SetShading` digunakan untuk menerapkan warna hijau muda solid pada sel, membuat tabel menonjol.

## Langkah 7: Simpan Dokumen

Terakhir, simpan dokumen yang dimodifikasi.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Langkah ini menyimpan dokumen Anda dengan format yang diterapkan. Anda dapat membukanya untuk melihat tabel yang diformat dengan indah.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda telah berhasil menerapkan batas kerangka ke tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini mencakup memuat dokumen, mengakses tabel, menyelaraskannya, menghapus batas yang ada, menerapkan batas baru, menambahkan bayangan sel, dan terakhir menyimpan dokumen. 

Dengan keterampilan ini, Anda dapat meningkatkan presentasi visual tabel Anda, menjadikan dokumen Anda lebih profesional dan menarik. Selamat membuat kode!

## FAQ

### Bisakah saya menerapkan gaya berbeda pada setiap batas tabel?  
 Ya, Anda dapat menerapkan gaya dan warna berbeda pada setiap batas dengan menyesuaikan parameter di`SetBorder` metode.

### Bagaimana cara mengubah lebar perbatasan?  
 Anda dapat mengubah lebarnya dengan memodifikasi parameter ketiga di`SetBorder` metode. Misalnya,`1.5` menetapkan lebar 1,5 poin.

### Apakah mungkin untuk menerapkan bayangan pada sel individual?  
 Ya, Anda dapat menerapkan bayangan ke masing-masing sel dengan mengakses setiap sel dan menggunakan`SetShading` metode.

### Bisakah saya menggunakan warna lain untuk pembatas dan bayangan?  
 Sangat! Anda dapat menggunakan warna apa pun yang tersedia di`System.Drawing.Color` kelas.

### Bagaimana cara menyelaraskan tabel secara horizontal?  
 Itu`table.Alignment = TableAlignment.Center;` baris dalam kode memusatkan tabel secara horizontal pada halaman.