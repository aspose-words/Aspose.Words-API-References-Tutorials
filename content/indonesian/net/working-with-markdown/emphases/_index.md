---
title: Penekanan
linktitle: Penekanan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan penekanan (tebal dan miring) dengan Aspose.Words for .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/emphases/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan penekanan dengan Aspose.Words untuk .NET. Penekanan digunakan untuk menekankan bagian tertentu dari teks, seperti huruf tebal dan miring.

## Langkah 1: Inisialisasi dokumen

 Pertama, kita akan menginisialisasi dokumen dengan membuat sebuah instance dari`Document` kelas.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Menggunakan pembuat dokumen

Selanjutnya, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Tambahkan teks dengan Penekanan

Kita dapat menambahkan teks penekanan dengan mengubah properti font pembuat dokumen. Dalam contoh ini, kami menggunakan huruf tebal dan miring untuk menekankan bagian teks yang berbeda.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Langkah 4: Menyimpan dokumen

 Terakhir, kita bisa menyimpan dokumen dalam format yang diinginkan. Dalam contoh ini, kami menggunakan`.md` ekstensi untuk format penurunan harga.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Selamat! Anda sekarang telah mempelajari cara menggunakan penekanan dengan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Penekanan menggunakan Aspose.Words untuk .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ

#### T: Bagaimana cara menyorot teks menggunakan Markdown?

 J: Untuk menyorot teks menggunakan Markdown, cukup kelilingi teks dengan simbol yang sesuai. Menggunakan`*` atau`_` untuk huruf miring,`**` atau`__` untuk berani, dan`~~` untuk dicoret.

#### T: Bisakah kita menggabungkan sorotan berbeda dalam teks yang sama?

 J: Ya, dimungkinkan untuk menggabungkan sorotan berbeda dalam teks yang sama. Misalnya, Anda dapat mencetak tebal dan miring sebuah kata dengan menggunakan keduanya`**` Dan`*`di sekitar kata.

#### T: Opsi penyorotan apa yang tersedia di Markdown?

J: Opsi penyorotan yang tersedia di Markdown dicetak miring (`*` atau`_`), berani (`**` atau`__`), dan coretan (`~~`).

#### T: Bagaimana cara menangani kasus ketika teks berisi karakter khusus yang digunakan oleh Markdown untuk menyorot?

 J: Jika teks Anda berisi karakter khusus yang digunakan oleh Markdown untuk menyorot, Anda dapat menghindarinya dengan mengawalinya dengan a`\` . Misalnya,`\*` akan menampilkan tanda bintang literal.

#### T: Bisakah kami menyesuaikan tampilan penyorotan menggunakan CSS?

J: Penyorotan di Markdown biasanya dirender menggunakan gaya default browser. Jika Anda mengonversi Markdown ke HTML, Anda dapat menyesuaikan tampilan penyorotan menggunakan aturan CSS.