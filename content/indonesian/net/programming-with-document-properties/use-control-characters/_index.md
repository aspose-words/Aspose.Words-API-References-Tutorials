---
title: Gunakan Karakter Kontrol
linktitle: Gunakan Karakter Kontrol
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menggunakan karakter kontrol dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/use-control-characters/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menggunakan karakter kontrol dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda memanipulasi karakter kontrol dalam teks.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Menggunakan karakter kontrol

Pada langkah ini, kita akan menggunakan karakter kontrol dalam teks. Gunakan kode berikut:

```csharp
const string text = "test\r";
// Ganti karakter kontrol "\r" dengan "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Kode ini mendefinisikan a`text` string yang berisi karakter kontrol "\r" (baris baru) dan menggunakan`Replace` metode untuk menggantinya dengan karakter kontrol "\r\n" (baris baru). baris diikuti dengan jeda baris).

### Contoh kode sumber untuk Menggunakan Karakter Kontrol menggunakan Aspose.Words untuk .NET

```csharp

	const string text = "test\r";
	// Ganti karakter kontrol "\r" dengan "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Anda dapat menggunakan kode di atas dalam proyek Anda sendiri dengan menggantinya`text` string dengan teks Anda sendiri yang berisi karakter kontrol.

Anda sekarang telah mempelajari cara menggunakan karakter kontrol dengan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah memanipulasi karakter kontrol di aplikasi Anda sendiri.