---
title: Ganti Dengan String
linktitle: Ganti Dengan String
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengganti teks dengan string di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/find-and-replace-text/replace-with-string/
---
Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Ganti Dengan String di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda melakukan penggantian teks berdasarkan string karakter tertentu dalam dokumen Word.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen Baru

 Sebelum kita mulai menggunakan penggantian string, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Sisipkan teks ke dalam dokumen

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Writeln` metode untuk menyisipkan frase "sedih gila buruk":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Langkah 3: Ganti dengan string

 Kami menggunakan`Range.Replace`metode untuk mengganti teks dengan string. Dalam contoh kita, kita mengganti semua kemunculan kata "sedih" dengan "buruk" menggunakan`FindReplaceOptions` pilihan dengan`FindReplaceDirection.Forward` arah pencarian:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Langkah 4: Menyimpan dokumen yang diedit

Terakhir, kami menyimpan dokumen yang dimodifikasi ke direktori tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Contoh kode sumber untuk Ganti Dengan String menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk mengilustrasikan penggunaan penggantian string karakter dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Kesimpulan

Dalam artikel ini, kita menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Ganti Dengan String dari Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks, mengganti dengan string, dan menyimpan dokumen yang dimodifikasi.

### FAQ

#### T: Apa yang dimaksud dengan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET?

J: Fungsi "Ganti Dengan String" di Aspose.Words untuk .NET memungkinkan Anda melakukan penggantian teks berdasarkan string karakter tertentu dalam dokumen Word. Ini memungkinkan Anda menemukan kemunculan string tertentu dan menggantinya dengan string lain yang ditentukan.

#### T: Bagaimana cara membuat dokumen baru menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat dokumen baru menggunakan Aspose.Words untuk .NET, Anda dapat membuat instance a`Document` obyek. Berikut contoh kode C# untuk membuat dokumen baru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks ke dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Di Aspose.Words untuk .NET, Anda dapat menggunakan berbagai metode`DocumentBuilder` kelas untuk menyisipkan teks di lokasi yang berbeda. Misalnya, Anda dapat menggunakan`Writeln` metode untuk menyisipkan teks pada baris baru. Berikut ini contohnya:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### T: Bagaimana cara melakukan penggantian teks dengan string di Aspose.Words untuk .NET?

 A: Untuk melakukan penggantian teks dengan string di Aspose.Words untuk .NET, Anda dapat menggunakan`Range.Replace` metode dan tentukan string yang akan diganti dan string yang akan diganti. Metode ini melakukan pencocokan teks sederhana dan menggantikan semua kemunculan string yang ditentukan. Berikut ini contohnya:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### T: Dapatkah saya melakukan penggantian teks peka huruf besar-kecil dengan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET?

J: Ya, secara default, fungsi "Ganti Dengan String" di Aspose.Words untuk .NET peka huruf besar-kecil. Artinya, ini hanya akan mengganti teks yang sama persis dengan string yang ditentukan berdasarkan huruf besar/kecil. Jika Anda ingin melakukan penggantian peka huruf besar-kecil, Anda dapat memodifikasi teks yang akan diganti dan string pengganti agar memiliki huruf besar/kecil yang sama, atau Anda dapat menggunakan teknik lain seperti ekspresi reguler.

#### T: Bisakah saya mengganti beberapa kemunculan string dalam dokumen menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET?

 J: Ya, Anda dapat mengganti beberapa kemunculan string dalam dokumen menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET. Itu`Range.Replace` metode ini akan menggantikan semua kemunculan string yang ditentukan dalam konten dokumen.

#### T: Apakah ada batasan atau pertimbangan saat menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET?

J: Saat menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET, penting untuk mengetahui konteksnya dan memastikan bahwa penggantian hanya diterapkan jika dimaksudkan. Pastikan string pencarian tidak muncul di tempat yang tidak diinginkan, seperti di dalam kata lain atau sebagai bagian dari format khusus. Selain itu, pertimbangkan implikasi kinerja saat Pemrosesan Kata dengan dokumen besar atau penggantian yang sering.

#### T: Bisakah saya mengganti string dengan panjang berbeda menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET?

J: Ya, Anda dapat mengganti string dengan panjang berbeda menggunakan fungsi "Ganti Dengan String" di Aspose.Words untuk .NET. Panjang string pengganti bisa berapa pun, dan akan menggantikan string pencarian yang sama persis. Dokumen akan menyesuaikan untuk mengakomodasi panjang string baru.