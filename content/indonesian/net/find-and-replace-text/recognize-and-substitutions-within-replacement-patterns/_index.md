---
title: Kenali Dan Substitusi Dalam Pola Penggantian
linktitle: Kenali Dan Substitusi Dalam Pola Penggantian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan pola penggantian dengan pengenalan dan substitusi di Aspose.Words untuk .NET untuk memanipulasi dokumen Word.
type: docs
weight: 10
url: /id/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Kenali Dan Substitusi Dalam Pola Penggantian di perpustakaan Aspose.Words untuk .NET. Fitur ini membantu mengenali pola pencarian yang kompleks dan melakukan substitusi berdasarkan kelompok yang ditangkap selama manipulasi dokumen.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen Baru

Sebelum kita mulai menggunakan kecocokan dan substitusi dalam pola penggantian, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
Document doc = new Document();
```

## Langkah 2: Sisipkan teks ke dalam dokumen

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Dalam contoh kami, kami menggunakan`Write` metode untuk menyisipkan frasa "Jason memberi Paul sejumlah uang." :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Langkah 3: Pengakuan dan Substitusi dalam Pola Penggantian

 Sekarang kita akan menggunakan`Range.Replace` berfungsi untuk melakukan pencarian dan penggantian teks menggunakan ekspresi reguler untuk mengenali pola tertentu. Dalam contoh kami, kami menggunakan ekspresi reguler`([A-z]+) gives money to ([A-z]+)` untuk mengenali kalimat dimana seseorang memberikan uang kepada orang lain. Kami menggunakan pola penggantian`$2 takes money from $1` untuk melakukan pergantian pemain dengan membalikkan peran. Penggunaan`$1` Dan`$2` mengacu pada grup yang ditangkap oleh ekspresi reguler:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Contoh kode sumber untuk Mengenali Dan Mengganti Pola Penggantian menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mengilustrasikan penggunaan kecocokan dan substitusi dalam pola penggantian dengan Aspose.Words untuk .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fitur Kenali Dan Substitusi Dalam Pola Penggantian Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks, melakukan pencarian dan penggantian menggunakan ekspresi reguler dan pola substitusi berdasarkan grup yang diambil, dan memanipulasi dokumen.

### FAQ

#### T: Apa yang dimaksud dengan fitur "Kenali dan Substitusi dalam Pola Penggantian" di Aspose.Words untuk .NET?

J: Fitur "Kenali Dan Substitusi Dalam Pola Penggantian" di Aspose.Words untuk .NET memungkinkan Anda mengenali pola pencarian kompleks menggunakan ekspresi reguler dan melakukan substitusi berdasarkan grup yang diambil selama manipulasi dokumen. Ini memungkinkan Anda mengubah teks yang cocok secara dinamis dengan mereferensikan grup yang diambil dalam pola penggantian.

#### T: Bagaimana cara membuat dokumen baru menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat dokumen baru menggunakan Aspose.Words untuk .NET, Anda dapat membuat instance a`Document` obyek. Berikut contoh kode C# untuk membuat dokumen baru:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks ke dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks menggunakan a`DocumentBuilder` obyek. Misalnya, untuk menyisipkan frasa "Jason memberikan uang kepada Paul.", Anda dapat menggunakan`Write` metode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### T: Bagaimana cara melakukan pencarian dan penggantian teks menggunakan ekspresi reguler di Aspose.Words untuk .NET?

 J: Untuk melakukan pencarian dan penggantian teks menggunakan ekspresi reguler di Aspose.Words untuk .NET, Anda dapat menggunakan`Range.Replace` berfungsi bersama dengan pola ekspresi reguler. Anda dapat membuat`Regex` objek dengan pola yang diinginkan dan meneruskannya ke`Replace` metode:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### T: Bagaimana cara menggunakan grup yang diambil dalam pola penggantian selama pencarian teks dan penggantian di Aspose.Words untuk .NET?

 J: Untuk menggunakan grup yang ditangkap dalam pola penggantian selama pencarian dan penggantian teks di Aspose.Words untuk .NET, Anda dapat mengaktifkan`UseSubstitutions` properti dari`FindReplaceOptions` obyek. Ini memungkinkan Anda untuk mereferensikan grup yang ditangkap menggunakan`$1`, `$2`, dll. dalam pola penggantian:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### T: Apa yang ditunjukkan oleh contoh kode sumber untuk fitur "Kenali dan Substitusi dalam Pola Penggantian" di Aspose.Words untuk .NET?

J: Contoh kode sumber menunjukkan penggunaan fitur "Kenali dan Substitusi dalam Pola Penggantian" di Aspose.Words untuk .NET. Ini menunjukkan cara membuat dokumen, menyisipkan teks, melakukan pencarian dan penggantian teks menggunakan ekspresi reguler, dan menggunakan grup yang diambil dalam pola penggantian untuk mengubah teks yang cocok secara dinamis.

#### T: Di mana saya dapat menemukan informasi lebih lanjut dan contoh tentang penggunaan ekspresi reguler di Aspose.Words untuk .NET?

J: Untuk informasi lebih lanjut dan contoh penggunaan ekspresi reguler di Aspose.Words untuk .NET, Anda dapat merujuk ke[Aspose.Words untuk referensi .NET API](https://reference.aspose.com/words/net/). Dokumentasi ini memberikan penjelasan mendetail dan contoh kode untuk berbagai skenario yang melibatkan ekspresi reguler dan manipulasi teks di Aspose.Words untuk .NET.

#### T: Bisakah saya memanipulasi aspek lain dari dokumen berdasarkan grup yang diambil selama pencarian dan penggantian teks?

J: Ya, Anda dapat memanipulasi aspek lain dari dokumen berdasarkan grup yang diambil selama pencarian dan penggantian teks. Selain melakukan substitusi teks, Anda dapat mengubah pemformatan, gaya, struktur dokumen, dan elemen lainnya berdasarkan grup yang diambil menggunakan berbagai API yang disediakan oleh Aspose.Words untuk .NET.

#### T: Apakah ada batasan atau pertimbangan saat menggunakan ekspresi reguler dan grup yang ditangkap di Aspose.Words untuk .NET?

J: Meskipun ekspresi reguler dan grup yang diambil menawarkan kemampuan canggih untuk pencarian dan penggantian teks di Aspose.Words untuk .NET, penting untuk mempertimbangkan kompleksitas dan implikasi kinerja. Ekspresi reguler yang sangat kompleks dan sejumlah besar grup yang ditangkap dapat memengaruhi performa. Disarankan untuk menguji dan mengoptimalkan ekspresi reguler untuk kasus penggunaan spesifik Anda guna memastikan manipulasi dokumen yang efisien.

#### Q: Bisakah saya menggunakan fitur "Kenali dan Substitusi dalam Pola Penggantian" dengan bahasa selain bahasa Inggris?

A: Ya, fitur "Kenali Dan Substitusi Dalam Pola Penggantian" di Aspose.Words untuk .NET dapat digunakan dengan bahasa selain bahasa Inggris. Ekspresi reguler tidak bergantung pada bahasa dan dapat dibuat untuk mencocokkan pola tertentu dalam bahasa apa pun. Anda dapat menyesuaikan pola ekspresi reguler agar sesuai dengan bahasa yang Anda inginkan dan pola teks spesifik yang ingin Anda kenali dan gantikan.