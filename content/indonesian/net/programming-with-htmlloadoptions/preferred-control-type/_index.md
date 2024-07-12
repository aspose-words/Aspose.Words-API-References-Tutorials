---
title: Jenis Kontrol Pilihan Dalam Dokumen Word
linktitle: Jenis Kontrol Pilihan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menentukan jenis kontrol pilihan di dokumen Word saat memuat dokumen HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlloadoptions/preferred-control-type/
---
Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan fitur tipe kontrol pilihan dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara menentukan jenis kontrol pilihan saat memuat dokumen HTML.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan kode HTML

 Untuk memulai, Anda perlu menentukan kode HTML yang ingin Anda muat sebagai dokumen. Dalam contoh ini, kami telah mendefinisikan sebuah`html` variabel yang berisi kode HTML pemilih dengan opsi.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Langkah 2: Tetapkan opsi pemuatan HTML

 Selanjutnya, kita membuat`HtmlLoadOptions` objek dan atur`PreferredControlType`properti ke`HtmlControlType.StructuredDocumentTag`. Ini memberitahu Aspose.Words untuk menggunakan StructuredDocumentTags untuk mewakili HTML saat memuat.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Langkah 3: Muat dan simpan dokumen

 Kami menggunakan`Document` kelas untuk memuat kode HTML dari aliran memori dengan opsi pemuatan yang ditentukan sebelumnya. Kemudian kita simpan dokumen tersebut pada direktori yang ditentukan dengan`.docx`format berkas.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Contoh kode sumber untuk jenis kontrol pilihan dengan Aspose.Words untuk .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Itu saja ! Anda telah berhasil menentukan jenis kontrol pilihan saat memuat dokumen HTML dengan Aspose.Words untuk .NET.

## Kesimpulan

 Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara menggunakan fitur "Jenis Kontrol Pilihan" di Aspose.Words untuk .NET guna menentukan jenis kontrol yang diinginkan saat memuat dokumen HTML. Mengatur`PreferredControlType`properti ke`HtmlControlType.StructuredDocumentTag` memungkinkan Aspose.Words menggunakan StructuredDocumentTags (SDT) untuk representasi dan pemrosesan konten HTML yang lebih baik. Anda juga dapat menjelajahi jenis kontrol lainnya untuk memenuhi kebutuhan spesifik Anda. Menggunakan fitur ini membantu memastikan penanganan dokumen HTML secara akurat dan efisien dalam aplikasi C# Anda dengan Aspose.Words.

### FAQ untuk jenis kontrol pilihan di dokumen Word

#### T: Apa yang dimaksud dengan fitur "Jenis Kontrol Pilihan" di Aspose.Words untuk .NET?

J: Fitur "Jenis Kontrol Pilihan" memungkinkan Anda menentukan jenis kontrol pilihan untuk mewakili elemen HTML saat memuat dokumen HTML. Ini membantu dalam memilih jenis kontrol yang sesuai untuk representasi dan pemrosesan konten HTML yang lebih baik.

#### T: Bagaimana cara menetapkan jenis kontrol pilihan saat memuat dokumen HTML?

 J: Untuk mengatur jenis kontrol pilihan, Anda perlu membuat`HtmlLoadOptions` objek dan mengaturnya`PreferredControlType` properti sesuai keinginan`HtmlControlType` . Dalam contoh yang diberikan,`HtmlControlType.StructuredDocumentTag` digunakan.

#### T: Apa pentingnya penggunaan StructuredDocumentTags (SDT) sebagai jenis kontrol pilihan?

J: StructuredDocumentTags (SDT) adalah elemen berbasis XML yang dapat digunakan untuk mewakili konten dan kontrol kompleks dalam dokumen Word. Menggunakan SDT sebagai jenis kontrol pilihan dapat memberikan kompatibilitas dan representasi konten HTML yang lebih baik.

#### T: Bagaimana cara memastikan bahwa Aspose.Words menggunakan tipe kontrol pilihan saat memuat dokumen HTML?

 J: Dengan mengatur`PreferredControlType`properti ke`HtmlControlType.StructuredDocumentTag`seperti yang ditunjukkan dalam contoh kode sumber, Aspose.Words akan menggunakan SDT untuk mewakili elemen HTML saat memuat dokumen.

#### T: Dapatkah saya menggunakan jenis kontrol lain sebagai opsi pilihan?

 A: Ya, selain itu`HtmlControlType.StructuredDocumentTag` , Aspose.Words untuk .NET mendukung tipe kontrol lain seperti`HtmlControlType.ContentControl`Dan`HtmlControlType.CustomXmlMarkup`.