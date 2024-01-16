---
title: Masukkan Objek Ole ke dalam Dokumen Word
linktitle: Masukkan Objek Ole ke dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan objek OLE dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang menggambarkan cara menyisipkan objek OLE di dokumen Word menggunakan Aspose.Words untuk .NET.

## Langkah 1: Impor referensi yang diperlukan
Sebelum memulai, pastikan Anda telah mengimpor referensi yang diperlukan untuk menggunakan Aspose.Words untuk .NET ke dalam proyek Anda. Ini termasuk mengimpor perpustakaan Aspose.Words dan menambahkan namespace yang diperlukan ke file sumber Anda.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Langkah 2: Buat dokumen baru dan pembuat dokumen
 Pada langkah ini, kita akan membuat dokumen baru menggunakan`Document` kelas dan pembuat dokumen menggunakan`DocumentBuilder` kelas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Masukkan objek OLE
 Gunakan Pembuat Dokumen`InsertOleObject` metode untuk memasukkan objek OLE ke dalam dokumen. Tentukan URL objek OLE, tipe objek, opsi tampilan, dan pengaturan lain yang diperlukan.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", benar, benar, nol);
```

## Langkah 4: Simpan dokumen
 Gunakan dokumen itu`Save` metode untuk menyimpan dokumen ke file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Contoh kode sumber untuk menyisipkan objek OLE dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", benar, benar, nol);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Ini adalah contoh kode lengkap untuk menyisipkan objek OLE dengan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda.

## Kesimpulan

Kesimpulannya, memasukkan objek OLE ke dalam dokumen Word adalah fitur canggih yang ditawarkan oleh Aspose.Words untuk .NET. Dengan menggunakan perpustakaan ini, Anda dapat dengan mudah menyematkan objek OLE seperti file HTML, spreadsheet Excel, presentasi PowerPoint, dll., ke dalam dokumen Word Anda.

Pada artikel ini, kita telah melalui panduan langkah demi langkah untuk menjelaskan kode sumber dalam C# yang menggambarkan cara menyisipkan objek OLE ke dalam dokumen Word. Kami membahas referensi yang diperlukan, membuat dokumen baru dan pembuat dokumen, serta langkah-langkah untuk menyisipkan objek OLE dan menyimpan dokumen.

### FAQ untuk menyisipkan objek OLE ke dalam dokumen Word

#### T: Kredensial apa yang perlu saya impor untuk menggunakan Aspose.Words untuk .NET?

J: Untuk menggunakan Aspose.Words untuk .NET, Anda perlu mengimpor referensi berikut:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### T: Bagaimana cara membuat dokumen baru dan pembuat dokumen?

 J: Anda dapat membuat dokumen baru menggunakan`Document` kelas dan pembuat dokumen menggunakan`DocumentBuilder` kelas, seperti gambar dibawah ini:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### T: Bagaimana cara menyisipkan objek OLE ke dalam dokumen?

 J: Gunakan`InsertOleObject`metode pembuat dokumen (`DocumentBuilder`) untuk menyisipkan objek OLE ke dalam dokumen. Tentukan URL objek OLE, tipe objek, opsi tampilan, dan pengaturan lain yang diperlukan. Berikut ini contohnya:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", benar, benar, nol);
```

#### Q: Bagaimana cara menyimpan dokumen?

 J: Gunakan dokumen tersebut`Save` metode untuk menyimpan dokumen ke file. Berikut ini contohnya:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### T: Dapatkah Anda memberikan contoh lengkap menyisipkan objek OLE dengan Aspose.Words untuk .NET?

A: Berikut adalah contoh kode lengkap untuk menyisipkan objek OLE dengan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", benar, benar, nol);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
