---
title: Phát hiện định dạng tệp tài liệu
linktitle: Phát hiện định dạng tệp tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước phát hiện định dạng tệp tài liệu với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-fileformat/detect-file-format/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng phát hiện định dạng tệp tài liệu với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách phát hiện định dạng của các tệp tài liệu khác nhau.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục

 Để bắt đầu, bạn cần xác định các thư mục nơi bạn muốn lưu trữ các tệp theo định dạng của chúng. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn. Chúng tôi tạo các thư mục "Được hỗ trợ", "Không xác định", "Được mã hóa" và "Pre97" nếu chúng chưa tồn tại.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Tạo các thư mục nếu chúng chưa tồn tại.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Bước 2: Duyệt tập tin

 Sau đó chúng tôi sử dụng`GetFiles` phương pháp của`Directory` class để lấy danh sách các tập tin trong thư mục được chỉ định. Chúng tôi cũng sử dụng một`Where`mệnh đề để loại trừ một tệp cụ thể có tên "Tài liệu bị hỏng.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Bước 3: Dò tìm định dạng của từng file

 Chúng tôi lặp qua từng tệp trong danh sách và sử dụng`DetectFileFormat` phương pháp của`FileFormatUtil` class để phát hiện định dạng của tệp. Chúng tôi cũng hiển thị loại tài liệu được phát hiện.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Hiển thị loại tài liệu
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
// ... Thêm trường hợp cho các định dạng tài liệu được hỗ trợ khác
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

Đó là tất cả ! Bạn đã phát hiện thành công định dạng của các tệp tài liệu khác nhau bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ để phát hiện định dạng tệp với Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Tạo các thư mục nếu chúng chưa tồn tại.
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

		// Hiển thị loại tài liệu
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

### Câu hỏi thường gặp về phát hiện định dạng tệp tài liệu

#### Làm cách nào để phát hiện định dạng của tệp tài liệu bằng Aspose.Words cho .NET?

 Để phát hiện định dạng của tệp tài liệu bằng Aspose.Words cho .NET, bạn có thể làm theo các bước được cung cấp trong hướng dẫn. Sử dụng`DetectFileFormat` phương pháp của`FileFormatUtil`class sẽ cho phép bạn phát hiện định dạng của tệp tài liệu. Điều này sẽ cho phép bạn xác định xem đó là tài liệu Microsoft Word 97-2003, mẫu, tài liệu Office Open XML WordprocessingML hay các định dạng được hỗ trợ khác. Mã được cung cấp trong hướng dẫn sẽ hướng dẫn bạn triển khai tính năng này.

#### Aspose.Words for .NET hỗ trợ những định dạng tài liệu nào?

Aspose.Words for .NET hỗ trợ nhiều định dạng tài liệu bao gồm tài liệu Microsoft Word 97-2003 (DOC), Mẫu (DOT), tài liệu Office Open XML WordprocessingML (DOCX), tài liệu Office Open XML WordprocessingML có macro (DOCM), Office Open Các mẫu XML WordprocessingML không có macro (DOTX), các mẫu Office Open XML WordprocessingML có macro (DOTM), tài liệu OPC phẳng, tài liệu RTF, tài liệu Microsoft Word 2003 WordprocessingML, tài liệu HTML, tài liệu MHTML (Web archive), tài liệu Văn bản OpenDocument (ODT), Các mẫu Văn bản OpenDocument (OTT), tài liệu MS Word 6 hoặc Word 95 và các định dạng tài liệu không xác định.

#### Làm cách nào để xử lý các tập tin tài liệu được mã hóa trong quá trình phát hiện định dạng?

 Khi phát hiện định dạng của tệp tài liệu, bạn có thể sử dụng`IsEncrypted` tài sản của`FileFormatInfo` đối tượng để kiểm tra xem tập tin có được mã hóa hay không. Nếu tệp được mã hóa, bạn có thể thực hiện các bước bổ sung để xử lý trường hợp cụ thể này, chẳng hạn như sao chép tệp vào thư mục dành riêng cho tài liệu được mã hóa. Bạn có thể dùng`File.Copy` phương pháp để làm điều này.

#### Cần thực hiện những hành động nào khi không xác định được định dạng của tài liệu?

Khi không xác định được định dạng của tài liệu, bạn có thể quyết định xử lý nó theo cách cụ thể cho ứng dụng của mình. Trong ví dụ được cung cấp trong hướng dẫn, tài liệu được sao chép vào một thư mục cụ thể dành riêng cho các tài liệu có định dạng không xác định. Bạn có thể tùy chỉnh hành động này cho phù hợp với nhu cầu cụ thể của mình.

#### Có bất kỳ tính năng nào khác của Aspose.Words dành cho .NET có thể được sử dụng cùng với tính năng phát hiện định dạng tài liệu không?

Có, Aspose.Words for .NET cung cấp nhiều tính năng khác để xử lý và thao tác với tài liệu Word. Ví dụ: bạn có thể sử dụng thư viện để trích xuất văn bản, hình ảnh hoặc siêu dữ liệu từ tài liệu, áp dụng các thay đổi định dạng, hợp nhất tài liệu, chuyển đổi tài liệu sang các định dạng khác nhau, v.v.