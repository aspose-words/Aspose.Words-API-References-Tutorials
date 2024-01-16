---
title: Mengonfigurasi Tautan Ke Konten
linktitle: Mengonfigurasi Tautan Ke Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyiapkan penautan ke konten dalam dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/configuring-link-to-content/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menyiapkan penautan ke konten dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menautkan ke konten tertentu dalam dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Membuat Dokumen dan Konstruktor

Pada langkah ini kita akan membuat dokumen baru dan menginisialisasi konstruktor. Gunakan kode berikut:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Buat penanda

Sekarang kita akan membuat bookmark di dokumen. Gunakan kode berikut untuk membuat bookmark dengan teks di dalamnya:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Kode ini membuat bookmark bernama "MyBookmark" dan menambahkan beberapa teks di dalamnya.

## Langkah 4: Menyiapkan tautan konten

Sekarang kita akan mengonfigurasi tautan ke konten menggunakan properti dokumen. Gunakan kode berikut untuk menambahkan dan mengambil tautan ke konten:

```csharp
// Dapatkan daftar semua properti khusus dalam dokumen.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Tambahkan properti terikat konten.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Kode ini menambahkan properti terkait konten yang disebut "Bookmark" dengan bookmark "MyBookmark". Kemudian, ia mengambil informasi properti terkait konten seperti status tautan, sumber tautan, dan nilai properti.

### Contoh kode sumber untuk Mengonfigurasi Tautan Ke Konten menggunakan Aspose.Words untuk .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Ambil daftar semua properti dokumen kustom dari file.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Tambahkan properti tertaut ke konten.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Anda sekarang telah mempelajari cara mengonfigurasi tautan ke konten dalam dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah membuat dan mengonfigurasi tautan ke konten tertentu di dokumen Anda sendiri.