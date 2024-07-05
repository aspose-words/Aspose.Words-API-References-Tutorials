---
title: Deteksi Format File Dokumen
linktitle: Deteksi Format File Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mendeteksi format file dokumen dengan Aspose.Words for .NET.
type: docs
weight: 10
url: /id/net/programming-with-fileformat/detect-file-format/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan fitur deteksi format file dokumen dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mendeteksi format file dokumen yang berbeda.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori

 Untuk memulai, Anda perlu menentukan direktori tempat Anda ingin menyimpan file sesuai dengan formatnya. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Kami membuat direktori "Didukung", "Tidak Diketahui", "Terenkripsi" dan "Pre97" jika belum ada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Buat direktori jika belum ada.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Langkah 2: Telusuri File

 Kemudian kita menggunakan`GetFiles` metode`Directory` kelas untuk mendapatkan daftar file di direktori yang ditentukan. Kami juga menggunakan a`Where`klausa untuk mengecualikan file tertentu bernama "Dokumen.docx rusak".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Langkah 3: Deteksi format setiap file

 Kami mengulang setiap file dalam daftar dan menggunakan`DetectFileFormat` metode`FileFormatUtil` kelas untuk mendeteksi format file. Kami juga menampilkan jenis dokumen yang terdeteksi.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Menampilkan jenis dokumen
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Tambahkan kasus untuk format dokumen lain yang didukung
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

Itu saja ! Anda telah berhasil mendeteksi format file dokumen yang berbeda menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk deteksi format file dengan Aspose.Words for .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Buat direktori jika belum ada.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Menampilkan jenis dokumen
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### FAQ untuk deteksi format file dokumen

#### Bagaimana cara mendeteksi format file dokumen menggunakan Aspose.Words untuk .NET?

 Untuk mendeteksi format file dokumen menggunakan Aspose.Words for .NET, Anda dapat mengikuti langkah-langkah yang disediakan dalam tutorial. Menggunakan`DetectFileFormat` metode`FileFormatUtil`kelas akan memungkinkan Anda mendeteksi format file dokumen. Ini akan memungkinkan Anda menentukan apakah itu dokumen Microsoft Word 97-2003, templat, dokumen Office Open XML WordprocessingML, atau format lain yang didukung. Kode yang diberikan dalam tutorial akan memandu Anda dalam mengimplementasikan fitur ini.

#### Format dokumen apa yang didukung Aspose.Words untuk .NET?

Aspose.Words untuk .NET mendukung berbagai format dokumen termasuk dokumen Microsoft Word 97-2003 (DOC), Templat (DOT), dokumen Office Open XML WordprocessingML (DOCX), dokumen Office Open XML WordprocessingML dengan makro (DOCM), Office Open Templat XML WordprocessingML tanpa makro (DOTX), Templat Office Open XML WordprocessingML dengan makro (DOTM), dokumen Flat OPC, dokumen RTF, dokumen Microsoft Word 2003 WordprocessingML, dokumen HTML, dokumen MHTML (arsip Web), dokumen OpenDocument Text (ODT), Templat OpenDocument Text (OTT), dokumen MS Word 6 atau Word 95, dan format dokumen yang tidak diketahui.

#### Bagaimana cara menangani file dokumen terenkripsi selama deteksi format?

 Saat mendeteksi format file dokumen, Anda dapat menggunakan`IsEncrypted` properti dari`FileFormatInfo` keberatan untuk memeriksa apakah file tersebut dienkripsi. Jika file dienkripsi, Anda dapat mengambil langkah tambahan untuk menangani kasus khusus ini, seperti menyalin file ke direktori yang didedikasikan untuk dokumen terenkripsi. Anda dapat menggunakan`File.Copy` metode untuk melakukan ini.

#### Tindakan apa yang harus diambil jika format dokumen tidak diketahui?

Jika format dokumen tidak diketahui, Anda dapat memutuskan untuk menanganinya dengan cara yang spesifik untuk aplikasi Anda. Dalam contoh yang diberikan dalam tutorial, dokumen disalin ke direktori tertentu yang didedikasikan untuk dokumen dengan format yang tidak diketahui. Anda dapat menyesuaikan tindakan ini agar sesuai dengan kebutuhan spesifik Anda.

#### Apakah ada fitur lain dari Aspose.Words untuk .NET yang dapat digunakan bersama dengan deteksi format dokumen?

Ya, Aspose.Words untuk .NET menawarkan banyak fitur lain untuk memproses dan memanipulasi dokumen Word. Misalnya, Anda bisa menggunakan perpustakaan untuk mengekstrak teks, gambar, atau metadata dari dokumen, menerapkan perubahan pemformatan, menggabungkan dokumen, mengonversi dokumen ke format berbeda, dan banyak lagi.