---
title: Mulai Ulang Daftar Di Setiap Bagian
linktitle: Mulai Ulang Daftar Di Setiap Bagian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur ulang daftar bernomor ke setiap bagian dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-list/restart-list-at-each-section/
---

Dalam tutorial langkah demi langkah ini, kami akan menunjukkan kepada Anda cara mengatur ulang daftar bernomor ke setiap bagian dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Membuat Dokumen dan Daftar

Pertama, buat dokumen baru dan tambahkan daftar bernomor default:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Langkah 2: Menambahkan item ke daftar

 Kemudian gunakan a`DocumentBuilder` untuk menambahkan item ke daftar. Anda dapat menggunakan loop untuk menambahkan beberapa item ke daftar:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Dalam contoh ini, kita menyisipkan pemisah bagian setelah item daftar ke-15 untuk mengilustrasikan penomoran ulang.

## Langkah 3: Simpan dokumen yang dimodifikasi

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Jadi ! Anda telah berhasil mengatur ulang daftar bernomor ke setiap bagian dalam dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk mengatur ulang daftar di setiap bagian

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya agar sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara memulai ulang daftar di setiap bagian di Aspose.Words?

 J: Untuk memulai ulang daftar di setiap bagian di Aspose.Words, Anda perlu membuat instance dari`List`kelas dan berikan daftar bernomor padanya. Kemudian Anda dapat menggunakan`List.IsRestartAtEachSection` properti untuk menentukan bahwa penomoran harus dimulai ulang di setiap bagian. Anda dapat mengaitkan daftar ini dengan satu atau beberapa bagian dokumen Anda sehingga penomoran dimulai ulang dengan benar di setiap bagian.

#### T: Dapatkah saya menyesuaikan format penomoran daftar di Aspose.Words?

 A: Ya, Anda dapat menyesuaikan format penomoran daftar di Aspose.Words. Itu`List` class menawarkan beberapa properti untuk ini, seperti`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, dll. Anda dapat menggunakan properti ini untuk mengatur jenis daftar (bernomor, berpoin, dll.), format penomoran (angka Arab, angka Romawi, huruf, dll.), dan opsi pemformatan penomoran lainnya.

#### T: Apakah mungkin untuk menambahkan level tambahan ke daftar bernomor di Aspose.Words?

 J: Ya, dimungkinkan untuk menambahkan level tambahan ke daftar bernomor di Aspose.Words. Itu`ListLevel`kelas memungkinkan Anda mengatur properti pemformatan untuk setiap level daftar. Anda dapat mengatur opsi seperti awalan, akhiran, perataan, indentasi, dll. Ini memungkinkan Anda membuat daftar dengan berbagai tingkat hierarki.