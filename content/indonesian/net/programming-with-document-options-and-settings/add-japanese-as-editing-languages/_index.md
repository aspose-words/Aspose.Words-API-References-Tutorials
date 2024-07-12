---
title: Tambahkan Bahasa Jepang Sebagai Bahasa Pengeditan
linktitle: Tambahkan Bahasa Jepang Sebagai Bahasa Pengeditan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menambahkan bahasa Jepang sebagai bahasa pengeditan dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Dalam tutorial ini, kami akan membawa Anda langkah demi langkah untuk memahami dan mengimplementasikan fungsionalitas menambahkan bahasa Jepang sebagai bahasa pengeditan dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengatur preferensi bahasa saat memuat dokumen dan menambahkan bahasa Jepang sebagai bahasa pengeditan.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang tidak berisi bahasa pengeditan default dan ingin kita tambahkan bahasa Jepang. Gunakan kode berikut untuk memuat dokumen:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Atur preferensi bahasa yang akan digunakan saat memuat dokumen.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Langkah 3: Memeriksa bahasa default

Setelah memuat dokumen, kami akan memeriksa apakah bahasa pengeditan default telah disetel dengan benar ke bahasa Jepang. Gunakan kode berikut untuk mendapatkan ID bahasa Timur Jauh:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Kode tersebut memeriksa apakah ID bahasa Timur Jauh cocok dengan bahasa Jepang. Berdasarkan hasilnya, ini akan menampilkan pesan yang sesuai.

### Contoh kode sumber untuk Menambahkan Bahasa Jepang Sebagai Bahasa Pengeditan menggunakan Aspose.Words untuk .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Tetapkan preferensi bahasa yang akan digunakan saat dokumen dimuat.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

