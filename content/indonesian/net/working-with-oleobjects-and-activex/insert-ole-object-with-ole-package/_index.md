---
title: Masukkan Objek Ole Di Word Dengan Paket Ole
linktitle: Masukkan Objek Ole Di Word Dengan Paket Ole
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan objek OLE di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami yang terperinci untuk menyematkan file dengan lancar.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Perkenalan

Jika Anda ingin menyematkan file ke dalam dokumen Word, Anda berada di tempat yang tepat. Baik itu file ZIP, lembar Excel, atau jenis file lainnya, menyematkannya langsung ke dokumen Word Anda bisa sangat berguna. Anggap saja seperti memiliki kompartemen rahasia di dokumen Anda tempat Anda dapat menyimpan segala macam harta karun. Dan hari ini, kita akan membahas cara melakukan ini menggunakan Aspose.Words untuk .NET. Siap menjadi ahli Word? Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki yang berikut ini:

1. Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduh dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan .NET lainnya.
3. Pemahaman Dasar C#: Anda tidak perlu menjadi seorang ahli, tetapi mengetahui cara menggunakan C# akan membantu.
4. Direktori Dokumen: Folder tempat Anda dapat menyimpan dan mengambil dokumen.

## Impor Namespace

Hal pertama yang pertama, mari kita atur namespace kita. Anda perlu menyertakan namespace berikut dalam proyek Anda:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Mari kita bagi menjadi langkah-langkah kecil, sehingga mudah untuk diikuti.

## Langkah 1: Siapkan Dokumen Anda

Bayangkan Anda seorang seniman dengan kanvas kosong. Pertama, kita membutuhkan kanvas kosong, yaitu dokumen Word kita. Inilah cara Anda mengaturnya:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Kode ini menginisialisasi dokumen Word baru dan menyiapkan DocumentBuilder, yang akan kita gunakan untuk memasukkan konten ke dalam dokumen kita.

## Langkah 2: Baca Objek Ole Anda

Selanjutnya, mari kita baca file yang ingin Anda sematkan. Anggap saja ini seperti mengambil harta karun yang ingin Anda sembunyikan di kompartemen rahasia Anda:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Baris ini membaca semua byte dari file ZIP Anda dan menyimpannya dalam array byte.

## Langkah 3: Masukkan Objek Ole

Sekarang sampai pada bagian ajaibnya. Kami akan menyematkan file ke dalam dokumen Word kami:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Di sini, kita membuat aliran memori dari array byte dan menggunakan`InsertOleObject` metode untuk menyematkannya ke dalam dokumen. Kami juga mengatur nama file dan nama tampilan untuk objek yang disematkan.

## Langkah 4: Simpan Dokumen Anda

Terakhir, mari simpan karya kita:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Ini menyimpan dokumen dengan file yang Anda sematkan di direktori yang ditentukan.

## Kesimpulan

Dan itu dia! Anda telah berhasil menyematkan objek OLE ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Ini seperti menambahkan permata tersembunyi di dalam dokumen Anda yang dapat diungkapkan kapan saja. Teknik ini bisa sangat berguna untuk berbagai aplikasi, mulai dari dokumentasi teknis hingga laporan dinamis. 

## FAQ

### Bisakah saya menyematkan jenis file lain menggunakan metode ini?
Ya, Anda dapat menyematkan berbagai jenis file seperti lembar Excel, PDF, dan gambar.

### Apakah saya memerlukan lisensi untuk Aspose.Words?
 Ya, Anda memerlukan lisensi yang valid. Anda bisa mendapatkan[izin sementara](https://purchase.aspose.com/temporary-license/) untuk evaluasi.

### Bagaimana cara menyesuaikan nama tampilan objek OLE?
 Anda dapat mengatur`DisplayName` properti dari`OlePackage` untuk menyesuaikannya.

### Apakah Aspose.Words kompatibel dengan .NET Core?
Ya, Aspose.Words mendukung .NET Framework dan .NET Core.

### Bisakah saya mengedit objek OLE yang tertanam dalam dokumen Word?
Tidak, Anda tidak bisa mengedit objek OLE langsung di dalam Word. Anda harus membukanya di aplikasi aslinya.