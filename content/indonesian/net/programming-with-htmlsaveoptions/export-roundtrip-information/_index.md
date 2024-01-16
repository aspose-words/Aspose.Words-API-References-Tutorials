---
title: Ekspor Informasi Pulang Pergi
linktitle: Ekspor Informasi Pulang Pergi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor informasi pulang pergi saat menyimpan dokumen sebagai HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengekspor informasi bolak-balik dari dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda memasukkan informasi bolak-balik ke dalam file HTML yang diekspor, sehingga memudahkan untuk mengambil perubahan yang dilakukan pada dokumen asli.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen yang akan diekspor. Gunakan kode berikut untuk memuat dokumen dari direktori tertentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Kode ini membuat sebuah instance dari`Document` dengan memuat dokumen dari direktori yang ditentukan.

## Langkah 3: Mengonfigurasi opsi cadangan HTML

Sekarang kita akan mengonfigurasi opsi penyimpanan HTML untuk mengekspor informasi bolak-balik dokumen. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions`dan mengatur`ExportRoundtripInformation` pilihan untuk`true` untuk memasukkan informasi pulang pergi saat mengekspor.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML termasuk informasi pulang pergi, dan menyimpan file HTML yang diekspor ke direktori yang ditentukan.

### Contoh kode sumber untuk Mengekspor Informasi Pulang Pergi menggunakan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.