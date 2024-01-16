---
title: Sisipkan Bidang Gabungan Menggunakan DOM
linktitle: Sisipkan Bidang Gabungan Menggunakan DOM
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang gabungan bidang khusus ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-merge-field-using-dom/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang menggunakan fitur "Sisipkan Bidang Gabungan Bidang" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

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

## Langkah 3: Memindahkan kursor ke paragraf

 Kami menggunakan`MoveTo()` metode DocumentBuilder untuk memindahkan kursor ke paragraf tempat kita ingin menyisipkan bidang gabungan bidang.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Langkah 4: Memasukkan bidang gabungan bidang

 Kami menggunakan DocumentBuilder`InsertField()` metode untuk menyisipkan bidang gabungan bidang ke dalam paragraf.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Kami kemudian mengonfigurasi properti bidang gabungan bidang dengan menentukan opsi yang sesuai, seperti nama bidang, teks sebelum dan sesudah bidang, dan opsi pemformatan vertikal.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang gabungan bidang dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Pindahkan kursor ke paragraf.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Sisipkan bidang gabungan bidang.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Perbarui bidangnya.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Dalam contoh ini, kita membuat dokumen baru, memindahkan kursor ke paragraf yang diinginkan, lalu menyisipkan kolom gabungan bidang ke dalam dokumen.

### FAQ

#### T: Bagaimana cara menyisipkan bidang gabungan dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan DOM?

A: Untuk menyisipkan bidang gabungan dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan DOM, Anda dapat mengikuti langkah-langkah berikut:

1. Navigasikan ke paragraf tempat Anda ingin menyisipkan bidang gabungan.
2.  Membuat`FieldMergeField` obyek.
3. Atur properti bidang gabungan, seperti nama bidang dan opsi pemformatan.
4.  Tambahkan bidang gabungan ke paragraf menggunakan`Paragraph.AppendChild` metode.

#### T: Bagaimana cara menentukan data sumber untuk bidang gabungan di Aspose.Words untuk .NET?

J: Untuk menentukan data sumber untuk bidang gabungan di Aspose.Words untuk .NET, Anda dapat menggunakan`FieldMergeField.FieldName` metode untuk menyetel nama bidang gabungan, yaitu nama bidang di sumber data eksternal seperti file CSV, database, dll. Anda juga dapat menggunakan`FieldMergeField.Text` metode untuk mengatur nilai bidang gabungan secara langsung.

#### T: Bisakah saya mengkustomisasi tampilan bidang gabungan di dokumen Word dengan Aspose.Words untuk .NET?

 J: Ya, Anda dapat mengkustomisasi tampilan bidang gabungan di dokumen Word dengan Aspose.Words untuk .NET. Anda dapat mengatur opsi pemformatan seperti huruf besar/kecil, font, warna, dll. menggunakan properti`FieldMergeField` obyek.

#### T: Bagaimana cara memeriksa apakah bidang gabungan berhasil disisipkan dalam dokumen Word dengan Aspose.Words untuk .NET?

 J: Untuk memeriksa apakah bidang gabungan berhasil dimasukkan, Anda dapat menelusuri konten dokumen dan mencari contoh bidang gabungan. Anda dapat menggunakan metode dan properti dari`Document` objek untuk mengakses paragraf, bidang, dan elemen lain dari dokumen.

#### T: Apakah menyisipkan bidang gabungan menggunakan DOM memengaruhi struktur dokumen Word dengan Aspose.Words untuk .NET?

J: Memasukkan kolom gabungan menggunakan DOM tidak secara langsung mempengaruhi struktur dokumen Word. Namun, ini menambahkan elemen bidang baru ke konten dokumen. Anda dapat memanipulasi struktur dokumen dengan menambahkan, menghapus atau memodifikasi elemen yang ada sesuai kebutuhan Anda.