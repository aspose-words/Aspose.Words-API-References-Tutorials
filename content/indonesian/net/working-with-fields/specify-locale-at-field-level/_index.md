---
title: Tentukan Lokal Di Tingkat Bidang
linktitle: Tentukan Lokal Di Tingkat Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan lokalisasi tingkat bidang di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/specify-locale-at-field-level/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut yang memungkinkan penentuan lokalisasi di tingkat bidang menggunakan fitur Aspose.Words untuk .NET. Pastikan Anda telah menyertakan perpustakaan Aspose.Words di proyek Anda sebelum menggunakan kode ini.

## Langkah 1: Tetapkan jalur direktori dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda tempat dokumen yang diedit akan disimpan.

## Langkah 2: Buat pembuat dokumen

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Di sini kita membuat sebuah instance dari`DocumentBuilder` kelas yang memungkinkan kita menambahkan bidang ke dokumen.

## Langkah 3: Masukkan kolom tanggal dengan lokasi tertentu

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Kami menggunakan pembuat dokumen untuk menyisipkan bidang tipe`FieldType.FieldDate` ke dalam dokumen. Dengan mengatur`LocaleId`properti ke`1049`, kami menentukan lokalisasi Rusia untuk bidang ini.

## Langkah 4: Simpan dokumen yang dimodifikasi

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Terakhir, kami menyimpan dokumen yang dimodifikasi dengan lokasi tertentu ke file tertentu.

### Contoh kode sumber untuk menentukan lokalisasi tingkat bidang dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Ini adalah contoh kode sumber untuk menentukan lokalisasi di tingkat bidang dalam dokumen menggunakan Aspose.Words untuk .NET. Anda dapat menggunakan kode ini untuk menyisipkan kolom tanggal dengan lokasi tertentu di dokumen Word Anda.

### FAQ

#### T: Bagaimana cara menentukan lokal tingkat bidang di Aspose.Words untuk .NET?

 J: Untuk menentukan lokal di tingkat bidang di Aspose.Words untuk .NET, Anda dapat menggunakan`FieldOptions` kelas dan itu`FieldLocale` properti untuk mengatur lokal yang diinginkan. Misalnya, Anda bisa menggunakan`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` untuk menentukan lokal Perancis (Prancis).

#### T: Apakah mungkin untuk menentukan lokal yang berbeda untuk setiap bidang di Aspose.Words untuk .NET?

 J: Ya, dimungkinkan untuk menentukan lokal berbeda untuk setiap bidang di Aspose.Words untuk .NET. Anda dapat menggunakan`FieldOptions.FieldLocale` properti sebelum membuat atau memperbarui bidang tertentu untuk menetapkan lokal yang berbeda.

#### T: Bagaimana cara mendapatkan lokal yang saat ini digunakan untuk bidang di Aspose.Words untuk .NET?

 J: Untuk mendapatkan lokal yang saat ini digunakan untuk bidang di Aspose.Words untuk .NET, Anda dapat menggunakan bidang tersebut`Field.LocaleId`Properti. Ini akan memungkinkan Anda untuk mendapatkan pengenal lokal yang terkait dengan bidang tersebut.