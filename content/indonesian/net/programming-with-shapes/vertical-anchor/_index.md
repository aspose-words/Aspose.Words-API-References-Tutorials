---
title: Jangkar Vertikal
linktitle: Jangkar Vertikal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memposisikan bentuk secara vertikal dalam dokumen menggunakan fitur jangkar vertikal di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/vertical-anchor/
---

Tutorial ini menjelaskan cara menggunakan fitur jangkar vertikal di Aspose.Words untuk .NET untuk memposisikan bentuk secara vertikal dalam dokumen. Dengan mengatur properti jangkar vertikal suatu bentuk, Anda dapat mengontrol perataan vertikal relatif terhadap teks atau halaman.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan dan Konfigurasikan Bentuk
 Sisipkan bentuk ke dalam dokumen menggunakan`InsertShape` metode`DocumentBuilder` obyek. Tetapkan dimensi yang diinginkan untuk bentuknya.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Langkah 4: Atur Jangkar Vertikal
Atur properti jangkar vertikal pada bentuk untuk mengontrol perataan vertikalnya. Dalam contoh ini, kita menyetelnya ke "Bawah" untuk mengaitkan bentuk di bagian bawah teks atau halaman.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Langkah 5: Tambahkan Konten ke Bentuk
 Menggunakan`MoveTo` metode`DocumentBuilder` objek untuk memindahkan kursor ke paragraf pertama bentuk. Kemudian, gunakan`Write` metode untuk menambahkan konten ke bentuk.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Langkah 6: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save`metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Contoh kode sumber untuk Vertical Anchor menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Itu dia! Anda telah berhasil menggunakan fitur jangkar vertikal di Aspose.Words untuk .NET untuk memposisikan bentuk secara vertikal dalam dokumen.