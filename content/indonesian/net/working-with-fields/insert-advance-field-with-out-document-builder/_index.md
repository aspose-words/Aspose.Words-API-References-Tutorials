---
title: Sisipkan Bidang Lanjutan Tanpa Pembuat Dokumen
linktitle: Sisipkan Bidang Lanjutan Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang lanjutan ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Penyisipan Bidang Lanjutan tanpa DocumentBuilder" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan Paragraf

Kita mulai dengan membuat dokumen baru dan mengambil paragraf pertama.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Langkah 3: Memasukkan bidang lanjutan

 Kami menggunakan`AppendField()` metode untuk menyisipkan bidang lanjutan ke dalam paragraf.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Kami kemudian mengkonfigurasi berbagai properti bidang lanjutan dengan menentukan nilai yang diinginkan.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang lanjutan tanpa DocumentBuilder dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Masukkan bidang lanjutan.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menyisipkan kolom lanjutan tanpa menggunakan DocumentBuilder, mengonfigurasi berbagai properti kolom, dan menyimpan dokumen dengan nama file tertentu.

Ini menyimpulkan panduan kami tentang cara menggunakan fitur "Sisipkan Bidang Lanjutan Tanpa Pembuat Dokumen" dengan Aspose.Words untuk .NET.

### FAQ

#### T: Apa yang dimaksud dengan bidang lanjutan di Aspose.Words?

J: Bidang Lanjutan di Aspose.Words adalah tipe bidang khusus yang memungkinkan Anda melakukan penghitungan, menyertakan kondisi, dan melakukan operasi kompleks dalam dokumen Word. Ini menawarkan fleksibilitas luar biasa untuk membuat bidang dinamis dan khusus.

#### T: Bagaimana cara menyisipkan bidang lanjutan di dokumen Word tanpa menggunakan Pembuat Dokumen di Aspose.Words?

J: Untuk menyisipkan bidang lanjutan di dokumen Word tanpa menggunakan Pembuat Dokumen di Aspose.Words, Anda dapat mengikuti langkah-langkah berikut:

1. Impor kelas Dokumen dan Bidang dari namespace Aspose.Words.Fields.
2. Buat instance Dokumen dengan memuat dokumen Anda yang sudah ada.
3. Gunakan metode InsertField untuk menyisipkan bidang lanjutan dengan menentukan kode bidang lanjutan.
4. Simpan dokumennya.

#### Q: Bagaimana cara mendapatkan hasil field lanjutan di dokumen Word?

A: Untuk mendapatkan hasil bidang lanjutan di dokumen Word, Anda bisa menggunakan properti Hasil yang tersedia di kelas Bidang. Properti ini mengembalikan hasil perhitungan bidang.

#### T: Dapatkah saya mengubah rumus bidang lanjutan setelah menyisipkannya ke dalam dokumen Word?

A: Ya, Anda dapat mengedit rumus bidang lanjutan setelah memasukkannya ke dalam dokumen Word. Anda dapat melakukan ini dengan mengakses properti FieldCode kelas Field dan memperbarui rumus dengan memodifikasi teks rumus.