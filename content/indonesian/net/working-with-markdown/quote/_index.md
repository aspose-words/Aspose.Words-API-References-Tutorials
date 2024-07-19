---
title: Mengutip
linktitle: Mengutip
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan kutipan dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/quote/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan fitur kutipan dengan Aspose. Kata-kata untuk .NET Kutipan digunakan untuk menyorot bagian teks dengan mengelilinginya dengan batas khusus.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Menggunakan Gaya Kutipan Default

Kami akan menggunakan gaya paragraf default yang disebut "Kutipan" untuk menerapkan format kutipan pada teks.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Langkah 3: Membuat gaya untuk level bertingkat

 Kita dapat membuat gaya untuk level bertingkat menggunakan`Styles.Add` metode`Document`obyek. Dalam contoh ini, kita membuat gaya yang disebut "Quote1" untuk mewakili tingkat kutipan bertingkat.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Contoh kode sumber untuk kutipan dengan Aspose.Words untuk .NET


```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Secara default, dokumen menyimpan gaya blockquote untuk tingkat pertama.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Buat gaya untuk level bertingkat melalui pewarisan gaya.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fitur kutipan dengan Aspose.Words untuk .NET.


### FAQ

#### T: Apa yang dimaksud dengan kutipan di Markdown?

J: Kutipan di Markdown adalah cara untuk menyorot bagian teks dari sumber lain atau merujuk pada kutipan terkenal.

#### T: Bagaimana cara menggunakan tanda kutip di Markdown?

A: Untuk menggunakan kutipan dalam Markdown, sertakan teks kutipan dalam tanda kurung siku (`>`). Setiap baris kutipan harus diawali dengan tanda chevron.

#### T: Apakah kutipan Markdown mendukung atribut?

J: Kutipan penurunan harga tidak mendukung atribut tertentu. Mereka hanya disorot oleh format teks yang dikutip.

#### T: Bisakah Anda menyematkan kutipan di Markdown?

J: Ya, dimungkinkan untuk menyarangkan tanda kutip di Markdown dengan menambahkan tanda kurung sudut tambahan (`>`).