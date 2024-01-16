---
title: Abaikan Teks di Dalam Sisipkan Revisi
linktitle: Abaikan Teks di Dalam Sisipkan Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan fitur "Abaikan Teks di Dalam Sisipkan Revisi" dari Aspose.Words untuk .NET untuk memanipulasi revisi sisipan di dokumen Word.
type: docs
weight: 10
url: /id/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Abaikan Teks di Dalam Sisipkan Revisi di pustaka Aspose.Words untuk .NET. Fitur ini berguna ketika kita ingin mengabaikan teks di dalam revisi sisipan saat memanipulasi dokumen.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen Baru

 Sebelum kita mulai memanipulasi teks di dalam revisi sisipan, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
Document doc = new Document();
```

## Langkah 2: Sisipkan teks dengan pelacakan revisi

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks dengan pelacakan revisi menggunakan a`DocumentBuilder`obyek. Misalnya, untuk menyisipkan teks "Dimasukkan" dengan pelacakan revisi, kita dapat menggunakan`StartTrackRevisions`, `Writeln` Dan`StopTrackRevisions` metode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Langkah 3: Sisipkan teks yang belum ditinjau

 Selain teks dengan pelacakan revisi, kita juga dapat menyisipkan teks yang belum direvisi menggunakan`DocumentBuilder` obyek. Misalnya untuk menyisipkan teks "Teks" tanpa revisi, kita bisa menggunakan`Write` metode:

```csharp
builder.Write("Text");
```

## Langkah 4: Menggunakan fungsi Abaikan Teks di Dalam Sisipkan Revisi

 Untuk mengabaikan teks di dalam revisi sisipan pada operasi selanjutnya, kita dapat menggunakan a`FindReplaceOptions` objek dan atur`IgnoreInserted`properti ke`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Langkah 5: Menggunakan ekspresi reguler untuk pencarian dan penggantian

Untuk melakukan operasi pencarian dan penggantian pada teks dokumen, kami akan menggunakan ekspresi reguler. Dalam contoh kita, kita akan mencari semua kemunculan huruf "e" dan menggantinya dengan tanda bintang "* ". Kami akan menggunakan .NET`Regex` kelas untuk ini:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Langkah 6: Melihat Output Dokumen yang Dimodifikasi

 Setelah menerapkan pencarian dan penggantian, kita dapat menampilkan konten dokumen yang diubah menggunakan`GetText` metode:

```csharp
Console.WriteLine(doc.GetText());
```

## Langkah 7: Mengubah Opsi untuk Menyertakan Sisipkan Revisi

Jika kita ingin memasukkan teks di dalam revisi sisipan pada hasil keluaran, kita dapat mengubah opsi untuk tidak mengabaikan revisi sisipan. Untuk ini kami akan mengaturnya`IgnoreInserted`properti ke`false`:

```csharp
options.IgnoreInserted = false;
```

## Langkah 8: Melihat Dokumen yang Dimodifikasi dengan Sisipkan Revisi

Setelah mengubah opsi, kita dapat melakukan pencarian dan penggantian lagi untuk mendapatkan hasil dengan teks di dalam revisi sisipan yang disertakan:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Contoh kode sumber untuk Abaikan Teks di Dalam Sisipkan Revisi menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk mendemonstrasikan penggunaan fungsi Ignore Text Inside Insert Revisions dengan Aspose.Words untuk .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Sisipkan teks dengan pelacakan revisi.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Sisipkan teks yang tidak direvisi.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Abaikan Teks di Dalam Sisipkan Revisi di Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks dengan melacak revisi dan teks yang belum direvisi, menggunakan fungsi Abaikan Teks di Dalam Sisipkan Revisi, melakukan operasi pencarian dan penggantian dengan ekspresi reguler, dan menampilkan dokumen yang dimodifikasi.

### FAQ

#### T: Apa yang dimaksud dengan fitur "Abaikan Teks di Dalam Sisipkan Revisi" di Aspose.Words untuk .NET?

J: Fitur "Abaikan Teks di Dalam Sisipan Revisi" di Aspose.Words untuk .NET memungkinkan Anda menentukan apakah teks di dalam revisi sisipan harus diabaikan selama operasi tertentu, seperti mencari dan mengganti teks. Jika fitur ini diaktifkan, teks di dalam revisi sisipan tidak dipertimbangkan selama pengoperasian.

#### T: Bagaimana cara membuat dokumen baru menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat dokumen baru menggunakan Aspose.Words untuk .NET, Anda dapat membuat instance a`Document` obyek. Berikut contoh kode C# untuk membuat dokumen baru:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks dengan pelacakan revisi di Aspose.Words untuk .NET?

J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks dengan pelacakan revisi menggunakan a`DocumentBuilder` obyek. Misalnya, untuk menyisipkan teks "Dimasukkan" dengan pelacakan revisi, Anda dapat menggunakan`StartTrackRevisions`, `Writeln` , Dan`StopTrackRevisions` metode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### T: Bagaimana cara menyisipkan teks yang belum direvisi di Aspose.Words untuk .NET?

 J: Selain teks dengan pelacakan revisi, Anda juga dapat menyisipkan teks yang belum direvisi menggunakan`DocumentBuilder` obyek. Misalnya, untuk menyisipkan teks "Teks" tanpa revisi, Anda dapat menggunakan`Write` metode:

```csharp
builder.Write("Text");
```

#### T: Bagaimana cara mengabaikan teks di dalam revisi sisipan di Aspose.Words untuk .NET?

 J: Untuk mengabaikan teks di dalam revisi penyisipan selama operasi selanjutnya, Anda dapat menggunakan a`FindReplaceOptions` objek dan atur`IgnoreInserted`properti ke`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### T: Bagaimana cara melakukan pencarian dan penggantian menggunakan ekspresi reguler di Aspose.Words untuk .NET?

 A: Untuk melakukan operasi pencarian dan penggantian pada teks dokumen menggunakan ekspresi reguler, Anda dapat menggunakan .NET`Regex` kelas. Misalnya untuk mencari semua kemunculan huruf "e" dan menggantinya dengan tanda bintang "* ", Anda dapat membuat`Regex` objek dan menggunakannya dengan`Replace` metode:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### T: Bagaimana cara melihat keluaran dokumen yang dimodifikasi di Aspose.Words untuk .NET?

 J: Setelah menerapkan operasi pencarian dan penggantian, Anda dapat melihat konten dokumen yang diubah menggunakan`GetText` metode:

```csharp
Console.WriteLine(doc.GetText());
```

#### T: Bagaimana cara menyertakan revisi sisipan dalam hasil keluaran di Aspose.Words untuk .NET?

 A: Untuk memasukkan teks di dalam revisi sisipan pada hasil keluaran, Anda dapat mengubah opsi untuk tidak mengabaikan revisi sisipan. Untuk ini, Anda dapat mengaturnya`IgnoreInserted` properti dari`FindReplaceOptions` objek untuk`false`:

```csharp
options.IgnoreInserted = false;
```

#### T: Bagaimana cara menampilkan dokumen yang dimodifikasi dengan revisi sisipan di Aspose.Words untuk .NET?

A: Setelah mengubah opsi untuk memasukkan revisi sisipan, Anda dapat melakukan pencarian dan mengganti lagi untuk mendapatkan hasil dengan teks di dalam sisipan revisi yang disertakan:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```