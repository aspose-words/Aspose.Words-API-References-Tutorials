---
title: Masukkan Bidang Blok Alamat Gabungan Surat Menggunakan DOM
linktitle: Masukkan Bidang Blok Alamat Gabungan Surat Menggunakan DOM
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara Menyisipkan bidang blok alamat gabungan surat ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan Bidang Blok Alamat Gabungan Surat" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

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

 Kami menggunakan DocumentBuilder`MoveTo()` metode untuk memindahkan kursor ke paragraf di mana kita ingin menyisipkan bidang blok alamat gabungan surat.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Langkah 4: Memasukkan Bidang Blok Alamat Gabungan Surat

 Kami menggunakan DocumentBuilder`InsertField()` metode untuk menyisipkan bidang blok alamat gabungan surat ke dalam paragraf.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Kami kemudian mengonfigurasi properti bidang blok alamat dengan menentukan opsi yang sesuai, seperti menyertakan nama negara/wilayah, memformat alamat menurut negara/wilayah, nama negara/wilayah dikecualikan, format nama dan alamat, dan pengidentifikasi bahasa.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang blok alamat gabungan surat dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Kami ingin memasukkan blok alamat gabungan surat seperti ini:
// { BLOK ALAMAT \\c 1 \\d \\e Test2 \\f Test3 \\l \"Tes 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { BLOK ALAMAT \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { BLOK ALAMAT \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { BLOK ALAMAT \\c 1 \\d \\e Tes2 }
field.ExcludedCountryOrRegionName = "Test2";

// { BLOK ALAMAT \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { BLOK ALAMAT \\c 1 \\d \\e Test2 \\f Test3 \\l \"Tes 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ

#### T: Bagaimana cara mengkustomisasi format alamat surat di dokumen Word dengan Aspose.Words untuk .NET?

 J: Anda dapat menyesuaikan format alamat surat dalam dokumen Word dengan Aspose.Words untuk .NET menggunakan properti dari`FieldAddressBlock`obyek. Anda dapat mengatur opsi pemformatan seperti gaya alamat, pemisah, item opsional, dll. untuk mendapatkan format yang diinginkan.

#### T: Bagaimana cara menentukan data sumber untuk bidang alamat surat di Aspose.Words untuk .NET?

 J: Untuk menentukan data sumber untuk bidang alamat surat di Aspose.Words untuk .NET, Anda dapat menggunakan`FieldAddressBlock.StartAddress`Dan`FieldAddressBlock.EndAddress` properti. Properti ini digunakan untuk menentukan rentang alamat di sumber data eksternal, seperti file CSV, database, dll.

#### T: Bisakah saya menyertakan elemen opsional di bidang alamat surat dengan Aspose.Words untuk .NET?

 J: Ya, Anda dapat menyertakan elemen opsional di bidang alamat surat dengan Aspose.Words untuk .NET. Anda dapat menentukan elemen opsional dengan menggunakan`FieldAddressBlock.OmitOptional` metode untuk menentukan apakah akan menyertakan atau mengecualikan elemen opsional seperti nama penerima, nama perusahaan, dll.

#### T: Apakah memasukkan bidang alamat surat menggunakan DOM memengaruhi struktur dokumen Word dengan Aspose.Words untuk .NET?

J: Memasukkan kolom alamat surat menggunakan DOM tidak secara langsung mempengaruhi struktur dokumen Word. Namun, ini menambahkan elemen bidang baru ke konten dokumen. Anda dapat memanipulasi struktur dokumen dengan menambahkan, menghapus atau memodifikasi elemen yang ada sesuai kebutuhan Anda.