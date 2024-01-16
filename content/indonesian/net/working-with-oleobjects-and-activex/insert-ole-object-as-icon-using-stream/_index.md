---
title: Masukkan Objek Ole Sebagai Ikon Menggunakan Stream
linktitle: Masukkan Objek Ole Sebagai Ikon Menggunakan Stream
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan objek OLE sebagai ikon menggunakan aliran dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang mengilustrasikan cara menyisipkan objek OLE sebagai ikon menggunakan aliran dengan Aspose.Words untuk .NET.

## Langkah 1: Impor referensi yang diperlukan
Sebelum memulai, pastikan Anda telah mengimpor referensi yang diperlukan untuk menggunakan Aspose.Words untuk .NET ke dalam proyek Anda. Ini termasuk mengimpor perpustakaan Aspose.Words dan menambahkan namespace yang diperlukan ke file sumber Anda.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Langkah 2: Buat dokumen baru dan pembuat dokumen
 Pada langkah ini, kita akan membuat dokumen baru menggunakan`Document` kelas dan pembuat dokumen menggunakan`DocumentBuilder` kelas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan objek OLE sebagai ikon dari aliran
 Gunakan Pembuat Dokumen`InsertOleObjectAsIcon` metode untuk menyisipkan objek OLE sebagai ikon dari aliran ke dalam dokumen. Tentukan aliran data, tipe objek, jalur ikon, dan nama objek yang disematkan.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Langkah 4: Simpan dokumen
 Gunakan dokumen itu`Save` metode untuk menyimpan dokumen ke file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Contoh kode sumber untuk menyisipkan objek OLE sebagai ikon menggunakan aliran dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Ini adalah contoh kode lengkap untuk menyisipkan objek OLE sebagai ikon menggunakan aliran dengan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda.

## Kesimpulan

Panduan langkah demi langkah di atas menjelaskan cara menyisipkan objek OLE sebagai ikon dalam dokumen Word menggunakan alur dengan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda akan dapat mengintegrasikan fungsi ini ke dalam proyek Anda. Pastikan untuk mengimpor referensi yang diperlukan, buat dokumen baru dan pembuat dokumen, masukkan objek OLE sebagai ikon dari aliran, lalu simpan dokumen. Gunakan kode contoh yang disediakan sebagai titik awal dan sesuaikan dengan kebutuhan Anda.

### FAQ

#### T. Bagaimana cara mengimpor referensi yang diperlukan untuk menggunakan Aspose.Words untuk .NET?

A. Untuk mengimpor referensi yang diperlukan, Anda harus mengikuti langkah-langkah berikut:

 Tambahkan yang berikut ini`using` pernyataan di bagian atas file sumber Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Pastikan Anda telah menambahkan perpustakaan Aspose.Words ke proyek Anda.

#### T. Bagaimana cara membuat dokumen baru dan pembuat dokumen menggunakan Aspose.Words untuk .NET?

A. Untuk membuat dokumen baru dan pembuat dokumen, Anda dapat mengikuti langkah-langkah berikut:

 Menggunakan`Document` kelas untuk membuat dokumen baru:

```csharp
Document doc = new Document();
```
 Menggunakan`DocumentBuilder`kelas untuk membuat pembuat dokumen yang terkait dengan dokumen yang dibuat sebelumnya:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### T. Bagaimana cara menyisipkan objek OLE sebagai ikon dari aliran menggunakan Aspose.Words untuk .NET?

A. Untuk menyisipkan objek OLE sebagai ikon dari aliran, Anda dapat mengikuti langkah-langkah berikut:

 Menggunakan`InsertOleObjectAsIcon` metode pembuat dokumen untuk memasukkan objek OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. Bagaimana cara menyimpan dokumen dalam sebuah file?

A.  Untuk menyimpan dokumen ke file, Anda dapat menggunakan`Save` metode dokumen yang menentukan jalur tujuan:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### T. Bagaimana cara menyematkan kode untuk menyisipkan objek OLE sebagai ikon dari aliran ke dalam proyek saya?

A. Untuk menyematkan kode untuk menyisipkan objek OLE sebagai ikon dari aliran ke dalam proyek Anda, ikuti langkah-langkah berikut:
-  Impor referensi yang diperlukan dengan menambahkan yang sesuai`using` pernyataan.
-  Buat dokumen baru dan pembuat dokumen menggunakan`Document` Dan`DocumentBuilder` kelas.
- Gunakan kode untuk menyisipkan objek OLE sebagai ikon dari aliran.
-  Simpan dokumen menggunakan`Save` metode dengan jalur tujuan yang sesuai.

Dengan mengikuti langkah-langkah ini, Anda akan berhasil menyisipkan objek OLE sebagai ikon dari aliran menggunakan Aspose.Words untuk .NET. Pastikan untuk mengikuti instruksi dan mengimpor referensi yang diperlukan untuk mendapatkan hasil yang diinginkan.