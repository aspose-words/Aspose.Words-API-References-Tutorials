---
title: Masukkan ASKField Tanpa Pembuat Dokumen
linktitle: Masukkan ASKField Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang ASK ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan bidang ASK tanpa DocumentBuilder" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan Paragraf

Kita mulai dengan membuat dokumen baru dan mengambil paragraf pertama.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Langkah 3: Memasukkan bidang ASK

 Kami menggunakan`AppendField()` metode untuk menyisipkan bidang ASK ke dalam paragraf.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Kami kemudian mengkonfigurasi berbagai properti bidang ASK dengan menentukan nilai yang diinginkan.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang ASK tanpa DocumentBuilder dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Masukkan bidang ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menyisipkan kolom ASK tanpa menggunakan DocumentBuilder, mengonfigurasi berbagai properti kolom, dan menyimpan dokumen dengan nama file tertentu.

Ini menyimpulkan panduan kami tentang penggunaan fitur "Sisipkan Bidang ASK Tanpa Pembuat Dokumen" dengan Aspose.Words untuk .NET.

### FAQ

#### T: Apa yang dimaksud dengan bidang ASK di Aspose.Words?

J: Bidang ASK di Aspose.Words digunakan untuk menanyakan pertanyaan kepada pengguna saat membuka dokumen. Ini sering digunakan untuk meminta informasi atau umpan balik tertentu yang mungkin berbeda dari pengguna ke pengguna.

#### T: Bagaimana cara menyisipkan kolom ASK di dokumen Word tanpa menggunakan Pembuat Dokumen di Aspose.Words?

J: Untuk menyisipkan kolom ASK di dokumen Word tanpa menggunakan Pembuat Dokumen di Aspose.Words, Anda dapat mengikuti langkah-langkah berikut:

1. Impor kelas Dokumen dan Bidang dari namespace Aspose.Words.Fields.
2. Buat instance Dokumen dengan memuat dokumen Anda yang sudah ada.
3. Gunakan metode InsertField untuk menyisipkan kolom ASK dengan menentukan nama pertanyaan.
4. Simpan dokumennya.

#### T: Bagaimana cara mendapatkan respons pengguna untuk bidang ASK di dokumen Word?

J: Untuk mendapatkan respon pengguna untuk kolom ASK di dokumen Word, Anda bisa menggunakan metode GetFieldNames yang tersedia di kelas Dokumen. Metode ini mengembalikan daftar nama bidang yang ada dalam dokumen. Anda kemudian dapat memeriksa apakah nama bidang ASK ada dalam daftar dan mengambil respons terkait.

#### Q: Bisakah kolom ASK digunakan untuk meminta informasi lebih lanjut dari pengguna?

J: Ya, kolom ASK dapat digunakan untuk meminta beberapa informasi dari pengguna. Anda dapat menyisipkan beberapa kolom ASK ke dalam dokumen Anda, masing-masing berisi pertanyaan berbeda. Saat dokumen dibuka, pengguna akan dimintai jawaban yang sesuai.