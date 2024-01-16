---
title: Tampilkan Kesalahan Tata Bahasa dan Ejaan
linktitle: Tampilkan Kesalahan Tata Bahasa dan Ejaan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengaktifkan tampilan kesalahan tata bahasa dan ejaan dalam dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengaktifkan tampilan kesalahan tata bahasa dan ejaan dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda melihat kesalahan tata bahasa dan ejaan dalam suatu dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita tampilkan kesalahan tata bahasa dan ejaannya. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Aktifkan Tampilan Kesalahan

Sekarang kita akan mengaktifkan tampilan kesalahan tata bahasa dan ejaan dalam dokumen. Gunakan kode berikut untuk mengaktifkan tampilan kesalahan:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Kode ini memungkinkan tampilan kesalahan tata bahasa (`ShowGrammaticalErrors`) dan kesalahan ejaan (`ShowSpellingErrors`) dalam dokumen.

### Contoh kode sumber untuk Menampilkan Kesalahan Tata Bahasa dan Ejaan menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengaktifkan tampilan kesalahan tata bahasa dan ejaan dalam dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah mengaktifkan fitur ini di dokumen Anda sendiri.