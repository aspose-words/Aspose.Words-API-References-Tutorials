---
title: Sisipkan Bidang TOA Tanpa Pembuat Dokumen
linktitle: Sisipkan Bidang TOA Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyisipkan bidang TOA tanpa Pembuat Dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-toafield-without-document-builder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "TOA Field Insertion" dari Aspose.Words untuk .NET. Ikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan Paragraf

Kita mulai dengan membuat dokumen baru dan menginisialisasi paragraf.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Langkah 3: Memasukkan bidang TA

Kami menggunakan kelas FieldTA untuk menyisipkan bidang TA ke dalam paragraf.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Langkah 4: Menambahkan paragraf ke badan dokumen

Kami menambahkan paragraf yang berisi bidang TA ke badan dokumen.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Langkah 5: Membuat paragraf untuk bidang TOA

Kami membuat paragraf baru untuk bidang TOA.

```csharp
para = new Paragraph(doc);
```

## Langkah 6: Memasukkan kolom TOA

Kami menggunakan kelas FieldToa untuk menyisipkan bidang TOA ke dalam paragraf.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Langkah 7: Menambahkan paragraf ke badan dokumen

Kami menambahkan paragraf yang berisi bidang TOA ke badan dokumen.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Langkah 8: Perbarui Bidang TOA

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang TOA.

```csharp
fieldToa.Update();
```

### Contoh kode sumber untuk penyisipan bidang TOA tanpa Pembuat Dokumen dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Kami ingin memasukkan bidang TA dan TOA seperti ini:
// { TA \c 1 \l "Nilai 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### FAQ

#### T: Bagaimana cara menyesuaikan tampilan bidang TOA yang disisipkan dalam dokumen Word dengan Aspose.Words untuk .NET?

J: Anda dapat menyesuaikan tampilan bidang TOA yang disisipkan dengan menggunakan properti`FieldTOA` objek untuk menentukan opsi pemformatan.

#### T: Dapatkah saya menambahkan beberapa bidang TOA dalam satu dokumen Word menggunakan Aspose.Words untuk .NET?

J: Ya, Anda dapat menambahkan beberapa bidang TOA dalam satu dokumen Word menggunakan Aspose.Words untuk .NET. Ulangi saja langkah penyisipan untuk setiap bidang.

#### T: Bagaimana cara memeriksa apakah bidang TOA berhasil dimasukkan ke dalam dokumen Word dengan Aspose.Words untuk .NET?

J: Untuk memeriksa apakah kolom TOA berhasil dimasukkan, Anda dapat menelusuri konten dokumen dan mencari contoh kolom TOA.

#### T: Apakah menyisipkan bidang TOA tanpa menggunakan DocumentBuilder memengaruhi pemformatan dokumen Word dengan Aspose.Words untuk .NET?

J: Memasukkan bidang TOA tanpa menggunakan DocumentBuilder tidak secara langsung mempengaruhi format dokumen Word. Namun, opsi pemformatan bidang TOA dapat memengaruhi pemformatan dokumen secara keseluruhan.