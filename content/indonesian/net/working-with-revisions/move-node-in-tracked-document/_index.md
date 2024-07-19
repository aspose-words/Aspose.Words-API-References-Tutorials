---
title: Pindahkan Node Dalam Dokumen yang Dilacak
linktitle: Pindahkan Node Dalam Dokumen yang Dilacak
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pindahkan node dalam dokumen yang dilacak dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/move-node-in-tracked-document/
---

Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara memindahkan simpul dalam dokumen Word yang dilacak menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Membuat dokumen

Langkah pertama adalah membuat dokumen baru dan menambahkan paragraf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Langkah 2: Lacak revisi

Kami akan mengaktifkan pelacakan revisi dalam dokumen.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Langkah 3: Pindahkan sebuah simpul

Kami akan memindahkan node (paragraf) dari satu posisi ke posisi lain sambil menghasilkan revisi.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Langkah 4: Hentikan Pelacakan Ulasan

Kami akan berhenti melacak revisi dalam dokumen.

```csharp
doc.StopTrackRevisions();
```

## Langkah 5: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save`metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Contoh kode sumber untuk Memindahkan Node Dalam Dokumen yang Dilacak menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk memindahkan node dalam dokumen terlacak menggunakan Aspose.Words untuk .NET:


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Mulai lacak revisi.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Hasilkan revisi saat memindahkan node dari satu lokasi ke lokasi lain.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Hentikan proses pelacakan revisi.
doc.StopTrackRevisions();

// Ada 3 paragraf tambahan dalam rentang pindah dari.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memindahkan node dalam dokumen Word yang dilacak menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah membuat dokumen, mengaktifkan pelacakan revisi, memindahkan node, dan menghentikan pelacakan revisi, kami berhasil melakukan manipulasi ini. Aspose.Words for .NET adalah alat yang ampuh untuk Pemrosesan Kata dengan dokumen Word dan menawarkan fitur-fitur canggih untuk mengelola revisi. Sekarang Anda dapat menggunakan pengetahuan ini untuk memindahkan node di dokumen Word Anda sendiri sambil melacak revisi menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara mengaktifkan pelacakan revisi dalam dokumen Aspose.Words for .NET?

 J: Untuk mengaktifkan pelacakan revisi dalam dokumen Aspose.Words for .NET, Anda dapat menggunakan`StartTrackRevisions` metode`Document` obyek. Metode ini mengambil parameter nama pembuat revisi dan tanggal mulai tindak lanjut revisi.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### T: Bagaimana cara memindahkan node dalam dokumen yang dilacak tanpa membuat revisi?

 J: Jika Anda ingin memindahkan node dalam dokumen yang dilacak tanpa membuat revisi, Anda dapat menggunakan`Remove`Dan`InsertAfter` atau`InsertBefore` metode dari`Node` obyek. Misalnya untuk memindahkan paragraf demi paragraf lainnya, Anda dapat menggunakan kode berikut:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### T: Bagaimana cara menghentikan pelacakan revisi dalam dokumen Aspose.Words untuk .NET?

 J: Untuk berhenti melacak revisi dalam dokumen Aspose.Words untuk .NET, Anda dapat menggunakan`StopTrackRevisions` metode`Document` obyek.

```csharp
doc.StopTrackRevisions();
```