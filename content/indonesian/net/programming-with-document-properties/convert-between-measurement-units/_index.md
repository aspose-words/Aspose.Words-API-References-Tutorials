---
title: Konversi Antar Satuan Pengukuran
linktitle: Konversi Antar Satuan Pengukuran
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengonversi antar unit pengukuran dalam dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/convert-between-measurement-units/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengonversi antar unit pengukuran dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan margin, jarak header dan footer, dll. dalam satuan pengukuran yang berbeda.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Membuat Dokumen dan Konstruktor

Pada langkah ini kita akan membuat dokumen baru dan menginisialisasi konstruktor. Gunakan kode berikut:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Konfigurasikan satuan ukuran

Sekarang kita akan mengonversi nilai margin, jarak header dan footer, dll. dalam satuan pengukuran yang berbeda. Gunakan kode berikut untuk menentukan nilai dalam satuan pengukuran tertentu:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Kode ini menggunakan`ConvertUtil` kelas Aspose.Words untuk mengonversi nilai yang ditentukan menjadi inci (`InchToPoint` ). Anda juga dapat menggunakan metode konversi lain yang tersedia di`ConvertUtil` kelas untuk mengonversi nilai ke unit pengukuran lainnya.

### Contoh kode sumber untuk Konversi Antar Unit Pengukuran menggunakan Aspose.Words untuk .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Anda sekarang telah mempelajari cara mengonversi antar unit pengukuran saat menentukan margin, jarak header dan footer, dll. dalam dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menentukan nilai dalam satuan pengukuran yang diinginkan di dokumen Anda sendiri.