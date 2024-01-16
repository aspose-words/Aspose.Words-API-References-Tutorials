---
title: Ubah Sumber Budaya Pembaruan Bidang
linktitle: Ubah Sumber Budaya Pembaruan Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Ubah Sumber Budaya Pembaruan Bidang, Panduan langkah demi langkah untuk mengubah sumber budaya di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/change-field-update-culture-source/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses mengubah sumber budaya pembaruan bidang di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan memodifikasi sumber budaya, Anda dapat mengontrol format tanggal selama pembaruan bidang dan operasi gabungan surat. Kami akan memberi Anda kode sumber C# yang diperlukan dan petunjuk langkah demi langkah untuk mencapai hal ini.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen dan DocumentBuilder
Untuk memulai, buat sebuah instance dari kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Masukkan Konten dengan Lokal Tertentu
Selanjutnya, atur lokal ke Jerman dan masukkan kolom dengan format tanggal:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Pada kode di atas, kita mengatur font lokal ke Jerman (ID lokal 1031) dan menyisipkan dua kolom dengan format tanggal tertentu.

## Langkah 3: Ubah Sumber Budaya Pembaruan Bidang
Untuk mengubah sumber budaya pembaruan bidang, gunakan kelas FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Dalam contoh ini, kami mengatur budaya yang digunakan selama pembaruan lapangan untuk dipilih dari budaya yang digunakan di lapangan.

## Langkah 4: Lakukan Penggabungan Surat
Lakukan operasi gabungan surat dan tentukan nilai tanggal untuk bidang "Tanggal2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Dalam cuplikan kode ini, kami menjalankan operasi gabungan surat dan memberikan nilai DateTime untuk bidang "Date2".

## Langkah 5: Simpan Dokumen
Simpan dokumen yang dimodifikasi ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Contoh Kode Sumber untuk Mengubah Sumber Budaya Pembaruan Bidang menggunakan Aspose.Words untuk .NET
Berikut adalah kode sumber lengkap untuk mengubah sumber budaya pembaruan bidang di dokumen Word menggunakan Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengubah sumber budaya pembaruan bidang di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda kini dapat mengontrol budaya yang digunakan untuk pemformatan tanggal selama pembaruan bidang dan operasi penggabungan surat. Sesuaikan sumber budaya sesuai dengan kebutuhan Anda untuk memastikan tanggal yang akurat dan konsisten.

### FAQ

#### T: Bagaimana cara mengubah sumber budaya pembaruan lapangan di Aspose.Words untuk .NET?

 A: Untuk mengubah sumber budaya pembaruan bidang di Aspose.Words untuk .NET, Anda dapat menggunakan`Document.FieldOptions.CultureSource` properti dan tetapkan nilainya menjadi`FieldCultureSource.FieldCode` atau`FieldCultureSource.CurrentThread` . Misalnya, Anda bisa menggunakan`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` untuk menggunakan budaya yang ditentukan dalam kode lapangan.

#### T: Bagaimana cara menentukan budaya tertentu untuk memperbarui bidang di Aspose.Words untuk .NET?

J: Untuk menentukan budaya tertentu untuk memperbarui bidang di Aspose.Words untuk .NET, Anda dapat menggunakan`Document.FieldOptions.FieldUpdateCultureInfo` properti dan atur`CultureInfo` objek yang sesuai dengan budaya yang diinginkan. Misalnya, Anda bisa menggunakan`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` untuk menentukan budaya Perancis (Prancis).

#### T: Apakah mungkin untuk menonaktifkan pembaruan bidang otomatis di Aspose.Words untuk .NET?

 J: Ya, dimungkinkan untuk menonaktifkan pembaruan bidang otomatis di Aspose.Words untuk .NET. Anda dapat menggunakan`Document.FieldOptions.UpdateFields` properti dan setel ke`false` untuk mencegah kolom diperbarui secara otomatis. Ini memungkinkan Anda mengontrol pembaruan bidang secara manual sesuai kebutuhan.

#### T: Bagaimana cara memperbarui kolom dokumen secara manual di Aspose.Words untuk .NET?

 J: Untuk memperbarui bidang secara manual dalam dokumen di Aspose.Words untuk .NET, Anda dapat menggunakan`Field.Update` metode untuk setiap bidang secara individual. Misalnya, Anda bisa menggunakan`field.Update()` untuk memperbarui bidang tertentu.