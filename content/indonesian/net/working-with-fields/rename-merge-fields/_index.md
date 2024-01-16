---
title: Ganti nama Bidang Gabungan
linktitle: Ganti nama Bidang Gabungan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, Anda akan mempelajari cara mengganti nama bidang gabungan dalam dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/rename-merge-fields/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang menggunakan fitur penggantian nama bidang gabungan Aspose.Words untuk .NET. Ikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat dokumen dan menyisipkan bidang gabungan

Kita mulai dengan membuat dokumen baru dan menggunakan a`DocumentBuilder` untuk menyisipkan bidang gabungan.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Langkah 3: Mengganti Nama Bidang Gabungan

Kami mengulangi setiap bidang dalam rentang dokumen, dan jika itu adalah bidang gabungan, kami mengganti nama bidang tersebut dengan menambahkan "_Berganti nama menjadi "akhiran.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Langkah 4: Menyimpan dokumen

 Akhirnya, kami menelepon`Save()` metode untuk menyimpan dokumen yang dimodifikasi.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Contoh kode sumber untuk mengganti nama bidang gabungan dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan masukkan bidang gabungan.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Ganti nama bidang gabungan.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Simpan dokumennya.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Ikuti langkah-langkah berikut untuk mengganti nama bidang gabungan di dokumen Anda menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara mengganti nama bidang gabungan di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk mengganti nama bidang gabungan dalam dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengulang bidang dalam dokumen menggunakan`FieldMergingArgs` kelas dan gunakan`FieldMergingArgs.FieldName` metode untuk mengganti nama bidang.

#### T: Apakah mungkin untuk mengganti nama hanya bidang gabungan tertentu dalam dokumen Word dengan Aspose.Words untuk .NET?

J: Ya, dimungkinkan untuk mengganti nama hanya bidang gabungan tertentu dalam dokumen Word dengan Aspose.Words untuk .NET. Anda dapat memfilter bidang mana yang akan diganti namanya menggunakan kriteria tertentu, seperti nama bidang atau properti relevan lainnya. Kemudian Anda dapat mengganti nama bidang terkait menggunakan`FieldMergingArgs.FieldName` metode.

#### T: Bagaimana cara memeriksa apakah bidang gabungan berhasil diganti namanya di dokumen Word dengan Aspose.Words untuk .NET?

 J: Untuk memeriksa apakah bidang gabungan berhasil diganti namanya dalam dokumen Word dengan Aspose.Words untuk .NET, Anda dapat menggunakan`FieldMergedArgs` kelas dan akses`FieldMergedArgs.IsMerged` properti untuk menentukan apakah bidang tersebut diganti namanya dengan hit.

#### T: Apa konsekuensi mengganti nama bidang gabungan di dokumen Word dengan Aspose.Words untuk .NET?

J: Saat Anda mengganti nama bidang gabungan di dokumen Word dengan Aspose.Words untuk .NET, hal ini akan mengubah nama bidang dalam dokumen, yang mungkin berdampak pada fungsionalitas atau proses lain yang bergantung pada nama bidang. Pastikan untuk mempertimbangkan potensi konsekuensi ini sebelum mengganti nama bidang gabungan.

#### T: Apakah mungkin memulihkan nama asli bidang gabungan setelah mengganti namanya dengan Aspose.Words untuk .NET?

J: Ya, dimungkinkan untuk memulihkan nama asli bidang gabungan setelah mengganti namanya dengan Aspose.Words untuk .NET. Anda dapat menyimpan nama asli bidang dalam variabel atau daftar, lalu menggunakan informasi tersebut untuk memulihkan nama asli jika diperlukan.