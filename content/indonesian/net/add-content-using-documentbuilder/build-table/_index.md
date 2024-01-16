---
title: Bangun Tabel Dalam Dokumen Word
linktitle: Bangun Tabel Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/build-table/
---
Dalam tutorial langkah demi langkah ini, Anda akan mempelajari cara membuat tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat membuat tabel dengan format dan konten khusus menggunakan kelas DocumentBuilder.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Mulai Tabel
Selanjutnya, gunakan metode StartTable dari kelas DocumentBuilder untuk mulai membuat tabel:

```csharp
Table table = builder.StartTable();
```

## Langkah 3: Sisipkan Sel dan Tambahkan Konten
Sekarang, Anda bisa menyisipkan sel ke dalam tabel dan menambahkan konten ke dalamnya menggunakan metode InsertCell dan Write dari kelas DocumentBuilder. Sesuaikan format sel sesuai kebutuhan:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Langkah 4: Akhiri Baris
Setelah menambahkan konten ke sel baris pertama, gunakan metode EndRow kelas DocumentBuilder untuk mengakhiri baris:

```csharp
builder.EndRow();
```

## Langkah 5: Sesuaikan Pemformatan Baris
Anda dapat mengkustomisasi pemformatan baris dengan mengatur properti objek RowFormat dan CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Langkah 6: Akhiri Tabel
Untuk melengkapi tabel, gunakan metode EndTable dari kelas DocumentBuilder:

```csharp
builder.EndTable();
```

### Contoh Kode Sumber untuk Membuat Tabel menggunakan Aspose.Words untuk .NET
Berikut ini kode sumber lengkap untuk membuat tabel menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara membuat tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat membuat tabel dengan format khusus.

### FAQ untuk membuat tabel di dokumen Word

#### T: Apa itu Aspose.Words untuk .NET?

J: Aspose.Words untuk .NET adalah pustaka pemrosesan dokumen canggih yang memungkinkan pengembang membuat, membaca, mengedit, dan mengonversi dokumen Microsoft Word secara terprogram dalam aplikasi .NET. Ini menyediakan berbagai fitur untuk bekerja dengan dokumen Word, seperti manipulasi teks, pembuatan tabel, perlindungan dokumen, pemformatan, dan banyak lagi.

#### T: Bagaimana cara membuat tabel di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk membuat tabel di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat instance baru dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Menggunakan`StartTable` metode`DocumentBuilder`kelas untuk mulai membuat meja.
3.  Masukkan sel ke dalam tabel dan tambahkan konten menggunakan`InsertCell` Dan`Write` metode dari`DocumentBuilder` kelas.
4.  Akhiri baris menggunakan`EndRow` metode`DocumentBuilder` kelas.
5.  Sesuaikan pemformatan baris dengan mengatur properti`RowFormat` Dan`CellFormat` objek.
6.  Akhiri tabel menggunakan`EndTable` metode`DocumentBuilder` kelas.
7. Simpan dokumennya.

#### T: Bagaimana cara menyesuaikan format tabel dan selnya?

 J: Anda dapat menyesuaikan format tabel dan selnya dengan mengatur berbagai properti`RowFormat` Dan`CellFormat` objek. Misalnya, Anda dapat menyesuaikan perataan sel, orientasi teks vertikal dan horizontal, tinggi sel, tinggi baris, dan lainnya. Dengan menggunakan properti ini, Anda dapat memperoleh tampilan tabel dan konten yang diinginkan.

#### T: Dapatkah saya membuat tabel kompleks dengan sel gabungan dan fitur lanjutan lainnya?

 J: Ya, Aspose.Words untuk .NET menyediakan fitur lanjutan untuk membuat tabel kompleks, termasuk dukungan untuk sel gabungan, tabel bertumpuk, dan tata letak tabel kompleks. Anda dapat menggunakan`MergeCells` metode untuk menggabungkan sel,`StartTable`metode untuk membuat tabel bersarang, dan metode lain untuk mencapai struktur tabel yang diinginkan.

#### T: Apakah Aspose.Words untuk .NET kompatibel dengan format dokumen Word yang berbeda?

J: Ya, Aspose.Words untuk .NET kompatibel dengan berbagai format dokumen Word, termasuk DOC, DOCX, RTF, dan banyak lagi. Ini mendukung format lama (DOC) dan format berbasis XML modern (DOCX) dan memungkinkan Anda bekerja dengan dokumen dalam format berbeda tanpa masalah apa pun.

#### T: Di mana saya dapat menemukan informasi dan dokumentasi lebih lanjut untuk Aspose.Words untuk .NET?

 J: Anda dapat menemukan dokumentasi lengkap dan contoh kode di[Referensi API](https://reference.aspose.com/words/net/). Dokumentasi akan memberikan informasi rinci tentang fitur perpustakaan dan cara menggunakannya dalam aplikasi .NET Anda.