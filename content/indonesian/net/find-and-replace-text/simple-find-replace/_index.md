---
title: Temukan dan Ganti Teks Sederhana di Word
linktitle: Temukan dan Ganti Teks Sederhana di Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara melakukan pencarian dan penggantian teks sederhana di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/find-and-replace-text/simple-find-replace/
---
Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan Temukan dan Ganti Teks Sederhana di perpustakaan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda melakukan penggantian teks sederhana dengan mencari string karakter tertentu dan menggantinya dengan string karakter lain dalam dokumen Word.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen Baru

 Sebelum kita mulai menggunakan pencarian dan penggantian sederhana, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Sisipkan teks ke dalam dokumen

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Writeln` metode untuk menyisipkan frasa "Halo_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Langkah 3: Penggantian Teks Sederhana

 Kami menggunakan`Range.Replace` metode untuk melakukan penggantian teks sederhana. Dalam contoh kita, kita mengganti semua kemunculan string "_ClientName_ " dengan "James Bond" menggunakan`FindReplaceOptions` pilihan dengan`FindReplaceDirection.Forward` arah pencarian:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Langkah 4: Menyimpan dokumen yang diedit

Terakhir, kami menyimpan dokumen yang dimodifikasi ke direktori tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Contoh kode sumber untuk Simple Find Ganti menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mendemonstrasikan penggunaan pencarian sederhana dan penggantian dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Simpan dokumen yang diubah
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Simple Find replace Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks, melakukan penggantian teks sederhana, dan menyimpan dokumen yang diedit.

### FAQ

#### T: Apa fungsi Temukan dan Ganti Teks Sederhana di Aspose.Words untuk .NET?

J: Fitur Temukan dan Ganti Teks Sederhana di Aspose.Words untuk .NET memungkinkan Anda melakukan penggantian teks sederhana di dokumen Word. Ini memungkinkan Anda untuk mencari string karakter tertentu dan menggantinya dengan string karakter lain. Ini bisa berguna ketika Anda ingin membuat perubahan global pada dokumen, seperti mengganti nama, tanggal, atau informasi lainnya.

#### T: Bagaimana cara membuat dokumen baru di Aspose.Words untuk .NET?

 J: Sebelum menggunakan fungsi Temukan dan Ganti Teks Sederhana, Anda harus membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek. Berikut ini contoh kode untuk membuat dokumen baru:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks ke dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Writeln` metode untuk menyisipkan frasa "Halo_CustomerName_::

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### T: Bagaimana cara melakukan penggantian teks sederhana dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Untuk melakukan penggantian teks sederhana, Anda dapat menggunakan`Range.Replace` metode. Dalam contoh kita, kita mengganti semua kemunculan string "_ClientName_ " dengan "James Bond" menggunakan`FindReplaceOptions` pilihan dengan`FindReplaceDirection.Forward` arah pencarian:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### T: Bagaimana cara menyimpan dokumen yang diedit di Aspose.Words untuk .NET?

 A: Setelah Anda selesai melakukan penggantian teks, Anda dapat menyimpan dokumen yang dimodifikasi ke direktori tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```