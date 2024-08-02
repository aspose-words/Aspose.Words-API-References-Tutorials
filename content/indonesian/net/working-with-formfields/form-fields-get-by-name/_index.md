---
title: Bidang Formulir Dapatkan Berdasarkan Nama
linktitle: Bidang Formulir Dapatkan Berdasarkan Nama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengambil dan mengubah bidang formulir menurut nama di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-formfields/form-fields-get-by-name/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan Aspose.Words untuk .NET untuk mengambil bidang formulir berdasarkan nama dari dokumen Word. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words untuk .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document` objek dengan memberikan jalur ke dokumen sumber Anda yang berisi bidang formulir:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Langkah 2: Mengambil Bidang Formulir

 Selanjutnya, akses`FormFields` properti dari`Range` objek dalam dokumen untuk mengambil semua bidang formulir:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Anda dapat mengambil bidang formulir berdasarkan indeks atau nama. Dalam contoh ini, kita mengambil kolom formulir menggunakan kedua metode:

```csharp
FormField formField1 = documentFormFields[3]; // Mengambil berdasarkan indeks
FormField formField2 = documentFormFields["Text2"]; // Mengambil berdasarkan nama
```

## Langkah 3: Memodifikasi Properti Bidang Formulir

Setelah Anda mengambil bidang formulir, Anda dapat mengubah propertinya sesuai kebutuhan. Dalam contoh ini, kami mengubah ukuran font`formField1` hingga 20 dan warna font`formField2` menjadi merah:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Langkah 4: Menyimpan Dokumen

Terakhir, simpan dokumen yang diubah:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Itu dia! Anda telah berhasil mengambil bidang formulir berdasarkan nama dan mengubah propertinya di dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Bidang Formulir Dapatkan Berdasarkan Nama menggunakan Aspose.Words untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mendapatkan bidang formulir berdasarkan nama di Aspose.Words?

 A: Untuk mendapatkan kolom formulir berdasarkan nama di Aspose.Words, Anda dapat menggunakan`Document.Range.FormFields[name]` metode. Metode ini mengembalikan kolom formulir yang sesuai dengan nama yang ditentukan.

#### Q: Bagaimana jika kolom formulir dengan nama yang ditentukan tidak ada di dokumen?

 A: Jika kolom formulir dengan nama yang ditentukan tidak ada dalam dokumen, maka`Document.Range.FormFields[name]` metode akan kembali`null`. Anda dapat memeriksa hasil ini untuk menangani kasus di mana bidang formulir tidak ditemukan.

#### T: Bagaimana cara mengubah properti bidang formulir yang ditemukan?

J: Setelah Anda mendapatkan bidang formulir berdasarkan nama, Anda dapat mengakses properti individualnya untuk mengeditnya. Misalnya, Anda dapat mengubah nilai bidang, mengaktifkan atau menonaktifkan visibilitasnya, atau mengubah properti lain sesuai kebutuhan.

#### T: Bisakah saya mendapatkan beberapa bidang formulir dengan nama yang sama dalam satu dokumen?

 J: Ya, dimungkinkan untuk memiliki beberapa bidang formulir dengan nama yang sama dalam sebuah dokumen. Dalam hal ini,`Document.Range.FormFields[name]` metode akan mengembalikan bidang formulir pertama yang ditemukan dengan nama yang ditentukan. Jika Anda memiliki beberapa bidang formulir dengan nama yang sama, Anda harus mempertimbangkan hal ini saat memanipulasi bidang tersebut.

#### T: Bagaimana cara mengulangi semua bidang formulir dalam dokumen?

 J: Untuk mengulangi semua bidang formulir dalam dokumen, Anda bisa menggunakan a`foreach` lingkaran di`Document.Range.FormFields` koleksi. Ini akan memungkinkan Anda untuk mengakses setiap bidang formulir satu per satu dan melakukan operasi pada masing-masing bidang tersebut.