---
title: Sisipkan Bidang Sertakan Teks Tanpa Pembuat Dokumen
linktitle: Sisipkan FieldIncludeText Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang FieldIncludeText di dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fungsionalitas "Sisipkan bidang FieldIncludeText" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

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

## Langkah 3: Memasukkan bidang FieldIncludeText

 Kami menggunakan`AppendField()` metode untuk menyisipkan bidang FieldIncludeText ke dalam paragraf.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Kami kemudian mengkonfigurasi properti bidang FieldIncludeText dengan menentukan nama bookmark dan nama file sumber.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Selanjutnya, kita menambahkan paragraf ke badan dokumen.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
fieldIncludeText.Update();
```

### Contoh kode sumber untuk menyisipkan bidang FieldIncludeText dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan paragraf.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Sisipkan bidang FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menginisialisasi paragraf, menyisipkan FieldIncludeTexten yang menentukan nama bookmark dan nama file sumber, dan menyimpan dokumen dengan nama file tertentu.

Ini menyimpulkan panduan kami tentang penggunaan fitur "Sisipkan FieldIncludeText" dengan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara menentukan file sumber untuk bidang penyertaan teks di Aspose.Words untuk .NET?

 J: Untuk menentukan file sumber untuk bidang penyertaan teks di Aspose.Words untuk .NET, Anda dapat menggunakan`FieldIncludeText.SourceFullName`properti untuk mengatur path lengkap file sumber. Pastikan file sumber dapat diakses dan berisi konten yang ingin Anda sertakan dalam bidang penyertaan teks.

#### T: Bisakah saya menyertakan teks dari makro di bidang penyertaan teks dengan Aspose.Words untuk .NET?

 J: Ya, Anda dapat menyertakan teks dari makro di bidang penyertaan teks dengan Aspose.Words untuk .NET. Anda dapat menggunakan`FieldIncludeText.IncludeText` properti untuk menentukan nama makro yang kontennya harus disertakan dalam bidang.

#### T: Apakah menyisipkan bidang penyertaan teks tanpa pembuat dokumen memengaruhi struktur dokumen Word dengan Aspose.Words untuk .NET?

J: Memasukkan bidang penyertaan teks tanpa pembuat dokumen tidak secara langsung mempengaruhi struktur dokumen Word. Namun, ini menambahkan elemen bidang baru ke konten dokumen. Anda dapat memanipulasi struktur dokumen dengan menambahkan, menghapus atau memodifikasi elemen yang ada sesuai kebutuhan Anda.

#### T: Dapatkah saya mengkustomisasi tampilan bidang penyertaan teks dalam dokumen Word dengan Aspose.Words untuk .NET?

J: Penyertaan bidang teks tidak secara langsung menyesuaikan tampilannya di dokumen Word. Namun, Anda dapat memformat teks yang disertakan menggunakan properti paragraf, properti font, dan objek pemformatan lain yang tersedia di Aspose.Words untuk .NET.