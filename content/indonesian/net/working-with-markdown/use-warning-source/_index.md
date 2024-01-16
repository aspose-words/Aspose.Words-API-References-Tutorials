---
title: Gunakan Sumber Peringatan
linktitle: Gunakan Sumber Peringatan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan sumber peringatan dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/use-warning-source/
---

Dalam contoh ini, kami akan menunjukkan cara menggunakan sumber peringatan dengan Aspose.Words untuk .NET. Sumber peringatan menunjukkan asal peringatan saat menggunakan fungsi panggilan balik.

## Langkah 1: Memuat dokumen

 Kami akan memuat dokumen yang ada yang berisi peringatan menggunakan`Load` metode`Document` kelas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Langkah 3: Menggunakan Sumber Peringatan

 Kami akan menggunakan sumber peringatan dengan mengatur dokumen`WarningCallback` properti ke koleksi`WarningInfo` objek.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Langkah 4: Menyimpan dokumen

Terakhir, kita bisa menyimpan dokumen dalam format yang diinginkan.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Contoh Kode Sumber untuk Menggunakan Sumber Peringatan dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Selamat! Anda sekarang telah mempelajari cara menggunakan sumber peringatan dengan Aspose.Words untuk .NET.

### FAQ

#### T: Bisakah kami menyesuaikan tampilan tag "Peringatan"?

 J: Pemformatan tag "Peringatan" bergantung pada perender penurunan harga yang digunakan. Dalam kebanyakan kasus, Anda dapat menyesuaikan tampilan dengan menggunakan CSS untuk menargetkan`blockquote` tag di dokumen Anda.

#### T: Apakah mungkin menambahkan ikon ke tag "Peringatan"?

J: Ya, Anda dapat menambahkan ikon ke tag "Peringatan" menggunakan kode HTML di dokumen Penurunan Harga Anda. Anda dapat menyisipkan a`span` tag dengan kelas yang sesuai untuk menampilkan ikon di sebelah teks peringatan.

#### T: Apakah tag "Peringatan" kompatibel dengan semua pembaca Markdown?

 J: Kompatibilitas tag "Peringatan" bergantung pada rendering penurunan harga yang digunakan. Sebagian besar pembaca Markdown akan mendukung`blockquote` tag untuk menampilkan teks yang disorot, namun tampilan persisnya mungkin berbeda.