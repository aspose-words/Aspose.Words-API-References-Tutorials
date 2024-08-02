---
title: Masukkan Objek Ole Di Word Dengan Paket Ole
linktitle: Masukkan Objek Ole Di Word Dengan Paket Ole
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan objek OLE dengan paket OLE ke dalam dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini yang mengilustrasikan cara menyisipkan objek OLE di Word dengan paket OLE menggunakan Aspose.Words untuk .NET.

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

## Langkah 3: Masukkan objek OLE dengan paket OLE
 Gunakan Pembuat Dokumen`InsertOleObject`metode untuk menyisipkan objek OLE dengan paket OLE ke dalam dokumen. Tentukan aliran data, tipe objek, opsi tampilan, dan pengaturan lain yang diperlukan.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Langkah 4: Simpan dokumen
 Gunakan dokumen itu`Save` metode untuk menyimpan dokumen ke file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Contoh kode sumber untuk menyisipkan objek OLE dengan paket OLE dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Ini adalah contoh kode lengkap untuk menyisipkan objek OLE dengan paket OLE dengan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda.

## Kesimpulan

Sebagai kesimpulan, kita telah melalui panduan langkah demi langkah untuk menyisipkan objek OLE ke dalam dokumen Word dengan paket OLE menggunakan Aspose.Words untuk .NET.

Dengan mengikuti langkah-langkah ini, Anda akan berhasil menyisipkan objek OLE dengan paket OLE ke dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti instruksi dengan cermat untuk mendapatkan hasil yang diinginkan.

### FAQ untuk menyisipkan objek ole di Word dengan paket ole

#### T: Kredensial apa yang perlu saya impor untuk menggunakan Aspose.Words untuk .NET?

J: Untuk menggunakan Aspose.Words untuk .NET, Anda perlu mengimpor referensi berikut:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### T: Bagaimana cara membuat dokumen baru dan pembuat dokumen?

 J: Anda dapat membuat dokumen baru menggunakan`Document` kelas dan pembuat dokumen menggunakan`DocumentBuilder` kelas, seperti gambar dibawah ini:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### T: Bagaimana cara menyisipkan objek OLE dengan paket OLE ke dalam dokumen?

 J: Gunakan`InsertOleObject` metode pembuat dokumen (`DocumentBuilder`) untuk menyisipkan objek OLE dengan paket OLE ke dalam dokumen. Tentukan aliran data, tipe objek, opsi tampilan, dan pengaturan lain yang diperlukan. Berikut ini contohnya:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q: Bagaimana cara menyimpan dokumen?

 J: Gunakan dokumen tersebut`Save`metode untuk menyimpan dokumen ke file. Berikut ini contohnya:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### T: Dapatkah Anda memberikan contoh lengkap menyisipkan objek OLE dengan paket OLE dengan Aspose.Words untuk .NET?

J: Berikut adalah contoh kode lengkap untuk menyisipkan objek OLE dengan paket OLE menggunakan Aspose.Words untuk .NET. Pastikan untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan sebelumnya untuk mengintegrasikan kode ini ke dalam proyek Anda:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Ini menyimpulkan tutorial kita tentang menyisipkan objek OLE dengan paket OLE ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Jangan ragu untuk mengimpor referensi yang diperlukan dan ikuti langkah-langkah yang dijelaskan untuk mengintegrasikan kode ini ke dalam proyek Anda. Jika Anda memiliki pertanyaan lebih lanjut, jangan ragu untuk menghubungi kami.