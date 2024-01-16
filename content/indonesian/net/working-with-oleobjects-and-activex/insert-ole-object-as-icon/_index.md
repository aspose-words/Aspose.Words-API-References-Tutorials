---
title: Sisipkan Objek Ole Di Dokumen Word Sebagai Ikon
linktitle: Sisipkan Objek Ole Di Dokumen Word Sebagai Ikon
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan objek OLE di dokumen Word sebagai ikon dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang menggambarkan cara menyisipkan objek OLE di dokumen Word sebagai ikon menggunakan Aspose.Words untuk .NET.

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

## Langkah 3: Sisipkan objek OLE sebagai ikon
 Gunakan Pembuat Dokumen`InsertOleObjectAsIcon`metode untuk menyisipkan objek OLE sebagai ikon ke dalam dokumen. Tentukan jalur file OLE, tanda tampilan, jalur ikon, dan nama objek yang disematkan.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Langkah 4: Simpan dokumen
 Gunakan dokumen itu`Save` metode untuk menyimpan dokumen ke file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Contoh kode sumber untuk menyisipkan objek OLE sebagai ikon dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Ini adalah contoh kode lengkap untuk menyisipkan objek OLE sebagai ikon dengan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda.

## Kesimpulan

Sebagai kesimpulan, kami menjelajahi panduan langkah demi langkah untuk menyisipkan objek OLE sebagai ikon dalam dokumen Word menggunakan Aspose.Words untuk .NET.

Dengan mengikuti langkah-langkah ini, Anda akan berhasil menyisipkan objek OLE sebagai ikon di dokumen Word Anda menggunakan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti instruksi dengan cermat untuk mendapatkan hasil yang diinginkan.

### FAQ untuk menyisipkan objek ole di dokumen Word sebagai ikon

#### T. Referensi apa yang diperlukan untuk menyisipkan objek OLE sebagai ikon dalam dokumen Word menggunakan Aspose.Words untuk .NET?

J: Anda perlu mengimpor referensi berikut ke proyek Anda untuk menggunakan Aspose.Words untuk .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q. Bagaimana cara membuat dokumen baru dan pembuat dokumen di Aspose.Words untuk .NET?

 J: Anda dapat membuat dokumen baru menggunakan`Document` kelas dan pembuat dokumen menggunakan`DocumentBuilder` kelas. Berikut ini contohnya:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. Bagaimana cara menyisipkan objek OLE sebagai ikon di dokumen?

 J: Gunakan Pembuat Dokumen`InsertOleObjectAsIcon` metode untuk menyisipkan objek OLE sebagai ikon. Tentukan jalur file OLE, tanda tampilan, jalur ikon, dan nama objek yang disematkan. Berikut ini contohnya:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. Bagaimana cara menyimpan dokumen dengan objek OLE yang disisipkan sebagai ikon?

 J: Gunakan dokumen tersebut`Save` metode untuk menyimpan dokumen ke file. Berikut ini contohnya:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```