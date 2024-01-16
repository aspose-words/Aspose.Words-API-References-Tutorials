---
title: Tetapkan Bahasa Rusia Sebagai Bahasa Pengeditan Default
linktitle: Tetapkan Bahasa Rusia Sebagai Bahasa Pengeditan Default
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyetel bahasa Rusia sebagai bahasa pengeditan default dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengatur bahasa Rusia sebagai bahasa pengeditan default dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengatur bahasa default saat memuat dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita atur bahasa Rusia sebagai bahasa pengeditan default. Gunakan kode berikut untuk memuat dokumen:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Memeriksa bahasa default

Setelah mengunggah dokumen, kami akan memeriksa apakah bahasa default telah disetel dengan benar ke bahasa Rusia. Gunakan kode berikut untuk mendapatkan ID bahasa default:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Kode memeriksa apakah ID bahasa cocok dengan bahasa Rusia. Berdasarkan hasilnya, ini akan menampilkan pesan yang sesuai.

### Contoh kode sumber untuk Tetapkan Bahasa Rusia Sebagai Bahasa Pengeditan Default menggunakan Aspose.Words untuk .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengatur bahasa Rusia sebagai bahasa pengeditan default untuk dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah