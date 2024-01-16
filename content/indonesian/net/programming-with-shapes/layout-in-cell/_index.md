---
title: Tata Letak Dalam Sel
linktitle: Tata Letak Dalam Sel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menata letak bentuk dalam sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/layout-in-cell/
---

Tutorial ini menjelaskan cara menata letak bentuk dalam sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan menyesuaikan properti bentuk dan menggunakan opsi tata letak, Anda bisa mengontrol posisi dan tampilan bentuk di dalam sel.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Bangun Tabel
 Menggunakan`StartTable`, `EndTable`, `InsertCell` , Dan`Write` metode dari`DocumentBuilder` objek untuk membuat tabel. Tetapkan tinggi baris dan aturan tinggi yang diinginkan menggunakan`RowFormat` properti.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Langkah 4: Buat dan Format Bentuknya
 Membuat`Shape` objek dan konfigurasikan propertinya untuk menentukan tanda air. Atur bentuk yang akan ditata di dalam sel menggunakan`IsLayoutInCell` Properti.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Langkah 5: Sesuaikan Bentuknya
 Sesuaikan tampilan dan teks bentuk tanda air dengan mengatur properti seperti`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, dll.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Langkah 6: Masukkan Bentuk ke dalam Dokumen
Masukkan bentuk tanda air ke dalam dokumen menggunakan`InsertNode` metode`DocumentBuilder` obyek. Posisikan bentuk menggunakan`MoveTo` metode untuk menempatkannya setelah proses terakhir dalam dokumen.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Langkah 7: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithShapes.LayoutInCell.docx".

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Contoh kode sumber Layout In Cell menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Menampilkan bentuk di luar sel tabel jika akan ditempatkan ke dalam sel.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Itu dia! Anda telah berhasil menata bentuk dalam sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET.