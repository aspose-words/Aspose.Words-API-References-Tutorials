---
title: Sisipkan Bidang Bersarang
linktitle: Sisipkan Bidang Bersarang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang bersarang dengan mudah ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-nested-fields/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan Bidang Bersarang" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan DocumentBuilder

Kita mulai dengan membuat dokumen baru dan menginisialisasi DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Memasukkan hentian halaman

Kami menggunakan loop untuk memasukkan beberapa hentian halaman ke dalam dokumen.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Langkah 4: Pindah ke Footer

 Kami menggunakan`MoveToHeaderFooter()` metode DocumentBuilder untuk memindahkan kursor ke footer utama.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Langkah 5: Memasukkan bidang bersarang

 Kami menggunakan DocumentBuilder`InsertField()` metode untuk menyisipkan bidang bersarang ke footer.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang bersarang dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan hentian halaman.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Pindah ke catatan kaki.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Sisipkan bidang bersarang.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Perbarui bidangnya.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menyisipkan hentian halaman, memindahkan kursor ke footer, lalu menyisipkan kolom bersarang di footer.

### FAQ

#### T: Bagaimana cara menyisipkan bidang bertumpuk dalam dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk menyisipkan bidang bertumpuk dalam dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:

1. Dapatkan paragraf di mana Anda ingin menyisipkan bidang bersarang.
2.  Membuat`FieldStart` objek untuk bidang induk.
3.  Tambahkan bidang anak menggunakan`FieldStart.NextSibling` metode melewati yang sesuai`FieldStart` objek sebagai parameter.

#### T: Apa manfaat menggunakan bidang bertumpuk di dokumen Word dengan Aspose.Words untuk .NET?

J: Menggunakan bidang bertingkat menawarkan beberapa keuntungan dalam dokumen Word dengan Aspose.Words untuk .NET. Hal ini memungkinkan fleksibilitas yang lebih besar dalam membuat templat dokumen dinamis, dengan memungkinkan penyisipan nilai variabel dan perhitungan ke dalam bidang yang disarangkan. Bidang bersarang juga dapat memfasilitasi pembuatan konten otomatis, seperti membuat daftar isi, nomor halaman, dll.

#### T: Bisakah saya memiliki bidang bertingkat bertingkat di dokumen Word dengan Aspose.Words untuk .NET?

J: Ya, dimungkinkan untuk memiliki bidang bertingkat bertingkat dalam dokumen Word dengan Aspose.Words untuk .NET. Anda dapat membuat hierarki kompleks dari bidang bersarang dengan menggunakan`FieldStart.NextSibling` metode untuk menambahkan bidang anak ke bidang induk yang ada.

#### T: Bagaimana cara mengkustomisasi properti bidang bertumpuk di dokumen Word dengan Aspose.Words untuk .NET?

 J: Untuk mengkustomisasi properti bidang bertumpuk dalam dokumen Word dengan Aspose.Words untuk .NET, Anda dapat mengakses yang sesuai`FieldStart` objek dan memodifikasi propertinya sesuai kebutuhan. Anda dapat mengatur opsi pemformatan, nilai, perhitungan, dll., dari bidang bersarang untuk mencapai hasil yang diinginkan.

#### T: Apakah menyisipkan bidang bertumpuk memengaruhi kinerja dokumen Word dengan Aspose.Words untuk .NET?

J: Menyisipkan bidang bertumpuk dapat memengaruhi kinerja dokumen Word dengan Aspose.Words untuk .NET, terutama jika dokumen berisi bidang bertumpuk dalam jumlah besar atau hierarki yang kompleks. Disarankan untuk mengoptimalkan kode dengan menghindari operasi yang tidak perlu atau berulang pada bidang bersarang untuk meningkatkan kinerja.