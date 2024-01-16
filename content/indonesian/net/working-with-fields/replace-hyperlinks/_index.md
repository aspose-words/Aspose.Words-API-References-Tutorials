---
title: Ganti Hyperlink
linktitle: Ganti Hyperlink
second_title: API Pemrosesan Dokumen Aspose.Words
description: Ganti hyperlink di dokumen Word menggunakan Aspose.Words untuk .NET. Petunjuk langkah demi langkah untuk mengganti hyperlink.
type: docs
weight: 10
url: /id/net/working-with-fields/replace-hyperlinks/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut untuk menggantikan hyperlink menggunakan Aspose.Words untuk fungsionalitas .NET. Pastikan Anda telah menyertakan perpustakaan Aspose.Words di proyek Anda sebelum menggunakan kode ini.

## Langkah 1: Tetapkan jalur direktori dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda yang berisi`Hyperlinks.docx` mengajukan.

## Langkah 2: Muat dokumen yang berisi hyperlink

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Di sini kita membuat sebuah instance dari`Document` kelas dari file yang ditentukan.

## Langkah 3: Telusuri bidang untuk menemukan hyperlink

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Beberapa hyperlink mungkin bersifat lokal (link ke bookmark di dalam dokumen), kami mengabaikannya.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Perulangan ini melewati semua bidang dalam dokumen untuk mencari bidang tipe`FieldType.FieldHyperlink` . Setelah bidang jenis ini ditemukan, kami memeriksa apakah itu adalah tautan lokal dengan mencentang`SubAddress` Properti. Jika tidak, kami mengganti alamat tautannya dengan`"http://www.aspose.com"` dan hasilnya dengan`"Aspose - The .NET & Java Component Editor"`.

## Langkah 4: Simpan dokumen yang dimodifikasi

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Terakhir, kami menyimpan dokumen yang dimodifikasi dengan hyperlink yang diganti ke file tertentu.

### Contoh kode sumber untuk menggantikan hyperlink dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Beberapa hyperlink mungkin bersifat lokal (link ke bookmark di dalam dokumen), kami mengabaikannya.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Ini adalah contoh kode sumber untuk menggantikan hyperlink dalam dokumen menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara mengganti hyperlink di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk mengganti hyperlink di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Document.Range.Replace`metode menentukan teks yang akan dicari dan teks pengganti. Pastikan untuk menggunakan opsi yang sesuai untuk mengatur parameter pencarian dan penggantian.

#### T: Apakah mungkin untuk mengganti hanya hyperlink tertentu di dokumen Word dengan Aspose.Words untuk .NET?

J: Ya, dimungkinkan untuk mengganti hanya hyperlink tertentu di dokumen Word dengan Aspose.Words untuk .NET. Anda dapat memfilter hyperlink yang akan diganti menggunakan kriteria tertentu, seperti URL link, teks link, atau properti relevan lainnya. Kemudian Anda dapat menerapkan penggantian hanya pada hyperlink yang cocok.

#### T: Bagaimana cara mengabaikan hyperlink di header, footer, atau catatan kaki saat mengganti dengan Aspose.Words untuk .NET?

J: Untuk mengabaikan hyperlink di header, footer, atau catatan kaki saat mengganti dengan Aspose.Words untuk .NET, Anda dapat menggunakan opsi pencarian lanjutan dan menentukan batas pencarian yang sesuai. Misalnya, Anda dapat membatasi pencarian pada bagian utama dokumen dan mengecualikan header, footer, atau catatan kaki.

#### T: Apakah mungkin untuk mengganti hyperlink dengan link internal ke bagian lain dokumen?

 J: Ya, hyperlink dapat diganti dengan link internal ke bagian lain dokumen dengan Aspose.Words untuk .NET. Anda dapat menggunakan jangkar atau id teks untuk membuat tautan internal dan kemudian menggantinya menggunakan`Document.Range.Replace` metode dengan pilihan yang sesuai.

#### T: Apakah mengganti hyperlink dengan Aspose.Words untuk .NET mempertahankan properti tautan, seperti warna atau gaya?

J: Ya, saat mengganti hyperlink dengan Aspose.Words untuk .NET, properti tautan seperti warna atau gaya dipertahankan. Anda dapat menentukan properti pemformatan yang sama di teks pengganti untuk mencapai hasil yang konsisten.