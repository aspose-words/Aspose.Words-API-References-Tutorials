---
title: Baca Properti XControl Aktif Dari File Word
linktitle: Baca Properti XControl Aktif Dari File Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Baca properti kontrol ActiveX dalam file Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Dalam panduan langkah demi langkah ini, kami akan menunjukkan cara membaca properti kontrol ActiveX di file Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Inisialisasi dokumen

 Langkah pertama adalah menginisialisasi`Document` objek dengan memuat dokumen Word yang berisi kontrol ActiveX. Pastikan untuk mengganti`MyDir` dengan jalur sebenarnya ke direktori yang berisi dokumen.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Langkah 2: Pulihkan kontrol ActiveX

 Pada langkah ini, kita akan mengulanginya masing-masing`Shape` dokumen untuk mengambil kontrol ActiveX dan membaca propertinya.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Contoh kode sumber untuk Membaca Properti XControl Aktif menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk membaca properti kontrol ActiveX menggunakan Aspose.Words untuk .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Kesimpulan

Panduan ini menunjukkan kepada Anda cara membaca properti kontrol ActiveX di file Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat menginisialisasi dokumen, mengambil kontrol ActiveX, dan membaca propertinya. Gunakan kode contoh yang disediakan sebagai titik awal dan sesuaikan dengan kebutuhan spesifik Anda.

Membaca properti kontrol ActiveX memungkinkan Anda mengekstrak informasi penting dari file Word yang berisi kontrol ini. Aspose.Words untuk .NET menawarkan fitur canggih untuk Pemrosesan Kata dengan kontrol ActiveX dan mengotomatiskan pemrosesan dokumen Anda.

### FAQ

#### T: Apa langkah pertama untuk membaca properti kontrol ActiveX di file Word?

 A: Langkah pertama adalah menginisialisasi`Document` objek dengan memuat dokumen Word yang berisi kontrol ActiveX. Pastikan untuk mengganti`MyDir` dengan jalur sebenarnya ke direktori yang berisi dokumen.

#### T: Bagaimana cara memasukkan kontrol ActiveX ke dalam dokumen?

 J: Untuk mengambil kontrol ActiveX, Anda perlu melakukan iterasi melalui masing-masing kontrol`Shape` dokumen dan periksa apakah itu adalah kontrol ActiveX. Menggunakan`OleFormat` milik`Shape` untuk mengakses`OleControl` objek dan mengambil properti yang diperlukan.

#### T: Properti kontrol ActiveX apa yang dapat saya baca?

J: Anda dapat membaca berbagai properti kontrol ActiveX, seperti keterangan, nilai, status diaktifkan atau dinonaktifkan, tipe, dan simpul anak yang terkait dengan kontrol.

#### T: Bagaimana cara mendapatkan jumlah total kontrol ActiveX dalam dokumen?

 J: Untuk mendapatkan jumlah total kontrol ActiveX dalam dokumen, Anda dapat menggunakan`GetChildNodes` metode`Document` objek yang menentukan`NodeType.Shape` ketik dan sertakan node anak.