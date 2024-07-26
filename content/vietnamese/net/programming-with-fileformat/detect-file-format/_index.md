---
title: Phát hiện định dạng tệp tài liệu
linktitle: Phát hiện định dạng tệp tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách phát hiện các định dạng tệp tài liệu bằng Aspose.Words cho .NET với hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/programming-with-fileformat/detect-file-format/
---
## Giới thiệu

Trong thế giới kỹ thuật số ngày nay, việc quản lý các định dạng tài liệu khác nhau một cách hiệu quả là rất quan trọng. Cho dù bạn đang xử lý Word, PDF, HTML hay các định dạng khác, việc có thể phát hiện và xử lý các tệp này một cách chính xác có thể giúp bạn tiết kiệm rất nhiều thời gian và công sức. Trong hướng dẫn này, chúng ta sẽ khám phá cách phát hiện các định dạng tệp tài liệu bằng Aspose.Words cho .NET. Hướng dẫn này sẽ hướng dẫn bạn mọi điều bạn cần biết, từ điều kiện tiên quyết đến hướng dẫn chi tiết từng bước.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ mình cần:

-  Aspose.Words for .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/) . Hãy chắc chắn rằng bạn có giấy phép hợp lệ. Nếu không, bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
- Visual Studio: Mọi phiên bản gần đây đều hoạt động tốt.
- .NET Framework: Đảm bảo bạn đã cài đặt đúng phiên bản.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết trong dự án của mình:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Hãy chia ví dụ thành nhiều bước để dễ theo dõi hơn.

## Bước 1: Thiết lập thư mục

Đầu tiên, chúng ta cần thiết lập các thư mục nơi các tệp sẽ được sắp xếp dựa trên định dạng của chúng.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Tạo các thư mục nếu chúng chưa tồn tại.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Bước 2: Lấy danh sách các tập tin

Tiếp theo, chúng ta sẽ nhận được danh sách các tệp từ thư mục, ngoại trừ mọi tài liệu bị hỏng.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Bước 3: Phát hiện định dạng tệp

Bây giờ, chúng tôi lặp qua từng tệp và phát hiện định dạng của nó bằng Aspose.Words.

```csharp
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

## Phần kết luận

Phát hiện các định dạng tệp tài liệu bằng Aspose.Words cho .NET là một quá trình đơn giản. Bằng cách thiết lập các thư mục, lấy danh sách tệp và sử dụng Aspose.Words để phát hiện các định dạng tệp, bạn có thể sắp xếp và quản lý tài liệu của mình một cách hiệu quả. Cách tiếp cận này không chỉ tiết kiệm thời gian mà còn đảm bảo rằng bạn xử lý chính xác các định dạng tài liệu khác nhau.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu Word theo chương trình. Nó cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu ở nhiều định dạng khác nhau.

### Aspose.Words có thể phát hiện tài liệu được mã hóa không?
Có, Aspose.Words có thể phát hiện xem tài liệu có được mã hóa hay không và bạn có thể xử lý các tài liệu đó một cách phù hợp.

### Aspose.Words có thể phát hiện những định dạng nào?
Aspose.Words có thể phát hiện nhiều định dạng bao gồm DOC, DOCX, RTF, HTML, MHTML, ODT, v.v.

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Words?
 Bạn có thể nhận được giấy phép tạm thời từ[Quyết định mua hàng](https://purchase.aspose.com/temporary-license/) trang.

### Tôi có thể tìm tài liệu về Aspose.Words ở đâu?
 Tài liệu về Aspose.Words có thể được tìm thấy[đây](https://reference.aspose.com/words/net/).
