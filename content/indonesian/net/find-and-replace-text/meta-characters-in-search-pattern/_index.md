---
title: Karakter Meta Dalam Pola Pencarian
linktitle: Karakter Meta Dalam Pola Pencarian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan metakarakter dalam pola pencarian dengan Aspose.Words untuk .NET untuk memanipulasi dokumen Word.
type: docs
weight: 10
url: /id/net/find-and-replace-text/meta-characters-in-search-pattern/
---
Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Meta Characters In Search Pattern di perpustakaan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menggunakan metakarakter khusus untuk melakukan pencarian lanjutan dan penggantian di dokumen Word.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen Baru

 Sebelum kita mulai menggunakan metakarakter dalam pola pencarian, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Sisipkan teks ke dalam dokumen

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Writeln` Dan`Write` metode untuk menyisipkan dua baris teks:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Langkah 3: Temukan dan ganti teks dengan metakarakter

 Sekarang kita akan menggunakan`Range.Replace` berfungsi untuk mencari dan mengganti teks menggunakan pola pencarian yang mengandung metakarakter khusus. Dalam contoh kita, kita mengganti frasa "Ini adalah baris 1&pIni adalah baris 2" dengan "Baris ini diganti" menggunakan`&p` metakarakter untuk mewakili jeda paragraf:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Langkah 4: Memasukkan hentian halaman ke dalam dokumen

 Untuk mengilustrasikan penggunaan metakarakter lain, kami akan menyisipkan hentian halaman ke dalam dokumen menggunakan`InsertBreak` metode dengan`BreakType.PageBreak` parameter. Kami pertama-tama memindahkan kursor dari`DocumentBuilder` di akhir dokumen, lalu kita sisipkan hentian halaman dan baris teks baru:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Langkah 5: Temukan dan ganti dengan metakarakter lain

 Sekarang kita akan melakukan pencarian lain dan mengganti menggunakan`&m` metakarakter untuk mewakili hentian halaman. Kami mengganti frasa "Ini baris 1&mIni baris 2" dengan "Bagian halaman diganti dengan teks baru." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Langkah 6: Menyimpan dokumen yang telah diedit

Terakhir, kami menyimpan dokumen yang dimodifikasi ke direktori tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Contoh kode sumber untuk Karakter Meta Dalam Pola Pencarian menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk mendemonstrasikan penggunaan metakarakter dalam pola pencarian dengan Aspose.Words untuk .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan metakarakter dalam pola pencarian Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks, melakukan pencarian dan penggantian menggunakan karakter meta khusus, menyisipkan hentian halaman, dan menyimpan dokumen yang diedit.

### FAQ

#### T: Apa yang dimaksud dengan fitur Meta Characters In Search Pattern di Aspose.Words untuk .NET?

J: Fitur Meta Characters In Search Pattern di Aspose.Words untuk .NET memungkinkan Anda menggunakan karakter meta khusus untuk melakukan pencarian lanjutan dan penggantian di dokumen Word. Metakarakter ini memungkinkan Anda mewakili hentian paragraf, hentian bagian, hentian halaman, dan elemen khusus lainnya dalam pola pencarian Anda.

#### T: Bagaimana cara membuat dokumen baru di Aspose.Words untuk .NET?

 J: Sebelum menggunakan metakarakter dalam templat pencarian, Anda harus membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek. Berikut ini contoh kode untuk membuat dokumen baru:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks ke dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Writeln` Dan`Write` metode untuk menyisipkan dua baris teks:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### T: Bagaimana cara mencari dan mengganti teks dengan metakarakter dalam dokumen menggunakan Aspose.Words untuk .NET?

 A: Untuk mencari dan mengganti teks dengan metakarakter, Anda dapat menggunakan`Range.Replace` metode. Dalam contoh kita, kita mengganti frasa "Ini adalah baris 1&pIni adalah baris 2" dengan "Baris ini diganti" menggunakan`&p` metakarakter untuk mewakili jeda paragraf:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### T: Bagaimana cara menyisipkan hentian halaman dalam dokumen menggunakan Aspose.Words untuk .NET?

J: Untuk mengilustrasikan penggunaan metakarakter lain, kami akan menyisipkan hentian halaman ke dalam dokumen menggunakan`InsertBreak` metode dengan`BreakType.PageBreak` parameter. Kami pertama-tama memindahkan kursor dari`DocumentBuilder` di akhir dokumen, lalu kita sisipkan hentian halaman dan baris teks baru:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### T: Bagaimana cara mencari dan mengganti dengan metakarakter lain dalam dokumen menggunakan Aspose.Words untuk .NET?

 A: Sekarang kami akan melakukan pencarian lain dan mengganti menggunakan`&m` metakarakter untuk mewakili hentian halaman. Kami mengganti frasa "Ini baris 1&mIni baris 2" dengan "Bagian halaman diganti dengan teks baru." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### T: Bagaimana cara menyimpan dokumen yang diedit di Aspose.Words untuk .NET?

 J: Setelah Anda membuat perubahan pada dokumen, Anda dapat menyimpannya ke direktori tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```