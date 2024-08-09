---
title: Rentang Tag Dokumen Terstruktur Mulai Pemetaan Xml
linktitle: Rentang Tag Dokumen Terstruktur Mulai Pemetaan Xml
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengikat data XML secara dinamis ke tag dokumen terstruktur di Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Perkenalan

Pernahkah Anda ingin memasukkan data XML secara dinamis ke dalam dokumen Word? Nah, Anda beruntung! Aspose.Words untuk .NET membuat tugas ini mudah. Dalam tutorial ini, kita mendalami rentang tag dokumen terstruktur, mulai pemetaan XML. Fitur ini memungkinkan Anda mengikat bagian XML khusus ke kontrol konten, memastikan konten dokumen Anda diperbarui secara lancar dengan data XML Anda. Siap mengubah dokumen Anda menjadi karya yang dinamis.

## Prasyarat

Sebelum kita beralih ke bagian pengkodean, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET Library: Pastikan Anda memiliki versi terbaru. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE lain yang mendukung C#.
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# adalah suatu keharusan.
4. Dokumen Word: Contoh dokumen Word untuk digunakan.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini akan memastikan kita memiliki akses ke semua kelas dan metode yang diperlukan di Aspose.Words untuk .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Setiap proyek membutuhkan landasan, bukan? Di sini, kami menyiapkan jalur ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Word

Selanjutnya, kita memuat dokumen Word. Ini adalah dokumen tempat kita akan memasukkan data XML kita.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Langkah 3: Tambahkan Bagian XML Khusus

Kita perlu membuat bagian XML yang berisi data yang ingin kita sisipkan dan menambahkannya ke koleksi CustomXmlPart dokumen. Bagian XML khusus ini akan berfungsi sebagai sumber data untuk tag dokumen terstruktur kami.

### Membuat Bagian XML

Pertama, buat ID unik untuk bagian XML dan tentukan kontennya.

```csharp
// Buat bagian XML yang berisi data dan tambahkan ke koleksi CustomXmlPart dokumen.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Verifikasi Konten Bagian XML

Untuk memastikan bagian XML ditambahkan dengan benar, kami mencetak kontennya.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Langkah 4: Buat Tag Dokumen Terstruktur

Tag Dokumen Terstruktur (SDT) adalah kontrol konten yang dapat mengikat bagian XML. Di sini, kita membuat SDT yang akan menampilkan konten bagian XML kustom kita.

Pertama, temukan awal rentang SDT di dokumen.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Langkah 5: Atur Pemetaan XML untuk SDT

Sekarang, waktunya untuk mengikat bagian XML kita ke SDT. Dengan menyetel pemetaan XML, kami menentukan bagian mana dari data XML yang harus ditampilkan di SDT.

 XPath menunjuk ke elemen tertentu di bagian XML yang ingin kita tampilkan. Di sini, kami menunjuk pada yang kedua`<text>` elemen di dalam`<root>` elemen.

```csharp
// Tetapkan pemetaan untuk StructuredDocumentTag kami
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen untuk melihat perubahannya. SDT di dokumen Word sekarang akan menampilkan konten XML yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Kesimpulan

Dan itu dia! Anda telah berhasil memetakan bagian XML ke tag dokumen terstruktur di dokumen Word menggunakan Aspose.Words untuk .NET. Fitur canggih ini memungkinkan Anda membuat dokumen dinamis dan berbasis data dengan mudah. Baik Anda membuat laporan, faktur, atau jenis dokumen lainnya, pemetaan XML dapat menyederhanakan alur kerja Anda secara signifikan.

## FAQ

### Apa itu tag dokumen terstruktur di Word?
Tag dokumen terstruktur, juga dikenal sebagai kontrol konten, adalah wadah untuk tipe konten tertentu dalam dokumen Word. Mereka dapat digunakan untuk mengikat data, membatasi pengeditan, atau memandu pengguna dalam pembuatan dokumen.

### Bagaimana cara memperbarui konten bagian XML secara dinamis?
 Anda dapat memperbarui konten bagian XML dengan memodifikasi`xmlPartContent` string sebelum menambahkannya ke dokumen. Cukup perbarui string dengan data baru dan tambahkan ke`CustomXmlParts` koleksi.

### Bisakah saya mengikat beberapa bagian XML ke SDT berbeda dalam dokumen yang sama?
Ya, Anda dapat mengikat beberapa bagian XML ke SDT berbeda dalam dokumen yang sama. Setiap SDT dapat memiliki bagian XML dan pemetaan XPath yang unik.

### Apakah mungkin memetakan struktur XML yang kompleks ke SDT?
Sangat! Anda dapat memetakan struktur XML yang kompleks ke SDT dengan menggunakan ekspresi XPath mendetail yang secara akurat menunjuk ke elemen yang diinginkan dalam bagian XML.

### Bagaimana cara menghapus bagian XML dari dokumen?
 Anda dapat menghapus bagian XML dengan memanggil`Remove` metode pada`CustomXmlParts` koleksi, melewati`xmlPartId` dari bagian XML yang ingin Anda hapus.