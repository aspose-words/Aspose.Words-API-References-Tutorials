---
title: Pindah Ke Sel Tabel Di Dokumen Word
linktitle: Pindah Ke Sel Tabel Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menggunakan Pindah Ke Sel Tabel dalam fitur dokumen kata Aspose.Words untuk .NET
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/move-to-table-cell/
---
Dalam contoh ini, kami akan memandu Anda tentang cara menggunakan fitur Pindah Ke Sel Tabel di dokumen Word Aspose.Words untuk .NET menggunakan kode sumber C# yang disediakan langkah demi langkah. Fitur ini memungkinkan Anda menavigasi dan memanipulasi sel tertentu di dalam tabel di dokumen Word. Ikuti langkah-langkah di bawah ini untuk mengintegrasikan fungsi ini ke dalam aplikasi Anda.

## Langkah 1: Muat dokumen yang berisi tabel

Pertama, kita perlu memuat dokumen yang berisi tabel tempat kita ingin memindahkan sel. Gunakan kode berikut untuk menyelesaikan langkah ini:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Kode ini memuat dokumen yang ditentukan (ganti "MyDir + "Tables.docx"" dengan jalur sebenarnya dari dokumen Anda yang berisi tabel).

## Langkah 2: Pindahkan DocumentBuilder ke sel tabel tertentu

Selanjutnya, kita akan memindahkan DocumentBuilder ke sel tabel tertentu. Gunakan kode berikut untuk melakukan langkah ini:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Kode ini membuat DocumentBuilder dari dokumen yang ada dan kemudian memindahkan kursor dari DocumentBuilder ke sel tabel yang ditentukan. Terakhir, ia menambahkan konten ke sel tersebut menggunakan DocumentBuilder`Write()` metode.

## Langkah 3: Periksa hasilnya

Anda sekarang dapat memverifikasi bahwa perpindahan ke sel tabel berhasil. Gunakan kode berikut untuk menyelesaikan langkah ini:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Kode ini memverifikasi bahwa sel yang ditentukan memang merupakan sel DocumentBuilder saat ini. Ini juga memverifikasi bahwa konten yang ditambahkan oleh DocumentBuilder telah disimpan dengan benar di sel tabel.

Itu saja ! Anda sekarang telah memahami cara menggunakan fungsionalitas pindah ke sel tabel Aspose.Words untuk .NET menggunakan kode sumber yang disediakan. Anda sekarang dapat mengintegrasikan fungsi ini ke dalam aplikasi Anda sendiri dan memanipulasi sel tabel tertentu di dokumen Word.


### Contoh kode sumber untuk berpindah ke sel tabel menggunakan Aspose.Words untuk .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Pindahkan pembuat ke baris 3, sel 4 pada tabel pertama.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Kesimpulan

Dalam contoh ini, kami menjelajahi fitur Pindah Ke Sel Tabel Aspose.Words untuk .NET. Kita mempelajari cara memuat dokumen yang berisi tabel, memindahkan DocumentBuilder ke sel tabel tertentu, dan menambahkan konten ke sel tersebut. Fitur ini memberi pengembang alat canggih untuk menavigasi dan memanipulasi sel tertentu dalam tabel dokumen Word secara terprogram menggunakan Aspose.Words untuk .NET. Ini bisa menjadi tambahan berharga bagi aplikasi Anda untuk pemrosesan dokumen Word dinamis dan manajemen konten tabel.

### FAQ untuk pindah ke sel tabel di dokumen Word

#### T: Apa tujuan fitur Pindah Ke Sel Tabel di Aspose.Words untuk .NET?

J: Fitur Pindah Ke Sel Tabel di Aspose.Words untuk .NET memungkinkan pengembang menavigasi dan memanipulasi sel tertentu di dalam tabel dalam dokumen Word secara terprogram. Ini memberikan kemampuan untuk menyisipkan, mengubah, atau menghapus konten dalam sel tertentu.

#### T: Bagaimana cara memindahkan DocumentBuilder ke sel tabel tertentu di dokumen Word?

J: Untuk memindahkan DocumentBuilder ke sel tabel tertentu di dokumen Word, Anda bisa menggunakan metode MoveToCell dari kelas DocumentBuilder. Metode ini mengambil indeks baris dan sel target dalam tabel sebagai parameter dan menempatkan kursor di awal sel tersebut.

#### T: Dapatkah saya menambahkan atau mengubah konten setelah berpindah ke sel tabel tertentu menggunakan fitur Pindah Ke Sel Tabel?

J: Ya, setelah DocumentBuilder diposisikan pada sel tabel yang diinginkan menggunakan MoveToCell, Anda bisa menggunakan berbagai metode kelas DocumentBuilder, seperti Write, Writeln, atau InsertHtml, untuk menambah atau mengubah konten sel tersebut.

#### T: Bagaimana cara memverifikasi bahwa perpindahan ke sel tabel berhasil?

J: Anda dapat memverifikasi keberhasilan perpindahan ke sel tabel dengan memeriksa posisi kursor DocumentBuilder. Misalnya, Anda bisa membandingkan node DocumentBuilder saat ini dengan sel yang ingin Anda pindahkan dan memverifikasi bahwa konten yang ditambahkan oleh DocumentBuilder disimpan dengan benar di sel tabel.