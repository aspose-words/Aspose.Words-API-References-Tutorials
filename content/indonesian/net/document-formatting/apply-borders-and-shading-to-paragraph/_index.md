---
title: Terapkan Batas Dan Bayangan Pada Paragraf Dalam Dokumen Word
linktitle: Terapkan Batas Dan Bayangan Pada Paragraf Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerapkan batas dan bayangan pada paragraf di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Dalam tutorial ini, kami akan menunjukkan kepada Anda cara menerapkan batas dan bayangan pada paragraf di dokumen Word menggunakan fungsionalitas Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan pemformatan.

## Langkah 1: Membuat dan mengonfigurasi dokumen

Untuk memulai, buat dokumen baru dan objek DocumentBuilder terkait. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Konfigurasi perbatasan

Sekarang mari kita konfigurasikan batas paragraf dengan menentukan gaya batas untuk setiap sisi. Begini caranya:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Langkah 3: Pengaturan Pengisian

Sekarang kita akan mengkonfigurasi isi paragraf dengan menentukan tekstur dan warna isian. Begini caranya:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Langkah 4: Tambahkan konten

Kami akan menambahkan beberapa konten berformat ke paragraf. Begini caranya:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Langkah 3: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Contoh kode sumber untuk Menerapkan Batas Dan Bayangan Ke Paragraf menggunakan Aspose.Words untuk .NET

Berikut source code lengkap fitur Apply Borders dan shading to Paragraph dengan Aspose.Words for .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Kesimpulan

 Dalam tutorial ini, kita mempelajari cara menerapkan batas dan bayangan pada paragraf di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengkonfigurasi paragraf`Borders` Dan`Shading` properti, kami dapat mengatur gaya batas, warna garis, dan warna isian untuk paragraf. Aspose.Words untuk .NET memberikan kemampuan pemformatan yang kuat untuk menyesuaikan tampilan paragraf dan menyempurnakan representasi visual dokumen Anda.

### FAQ

#### T: Bagaimana cara menerapkan batas dan bayangan pada paragraf di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk menerapkan batas dan bayangan pada paragraf di dokumen Word menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:
1.  Buat dokumen baru dan a`DocumentBuilder` obyek.
2.  Konfigurasikan batas paragraf dengan mengakses`Borders` properti dari`ParagraphFormat` dan mengatur gaya perbatasan untuk setiap sisi.
3. Konfigurasikan pengisian paragraf dengan mengakses`Shading` properti dari`ParagraphFormat` dan menentukan tekstur dan warna isian.
4.  Tambahkan konten ke paragraf menggunakan`Write` metode`DocumentBuilder`.
5.  Simpan dokumen menggunakan`Save` metode.

#### T: Bagaimana cara mengatur gaya batas untuk setiap sisi paragraf?

 A: Untuk mengatur gaya batas setiap sisi paragraf, Anda dapat mengakses`Borders` properti dari`ParagraphFormat` dan atur`LineStyle` properti untuk masing-masing`BorderType` (misalnya.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Anda dapat menentukan gaya garis yang berbeda seperti`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, dll.

#### T: Bagaimana cara menentukan tekstur dan warna isian untuk bayangan paragraf?

 A: Untuk menentukan tekstur dan warna isian untuk bayangan paragraf, Anda dapat mengakses`Shading` properti dari`ParagraphFormat` dan atur`Texture` properti ke indeks tekstur yang diinginkan (misalnya,`TextureIndex.TextureDiagonalCross` ). Anda juga dapat mengatur`BackgroundPatternColor` Dan`ForegroundPatternColor` properti ke warna yang diinginkan menggunakan`System.Drawing.Color` kelas.