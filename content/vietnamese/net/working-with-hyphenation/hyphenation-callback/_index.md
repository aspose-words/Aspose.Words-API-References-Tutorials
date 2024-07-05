---
title: Gọi lại dấu gạch nối
linktitle: Gọi lại dấu gạch nối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách triển khai gọi lại dấu gạch nối trong Aspose.Words cho .NET để nâng cao định dạng tài liệu bằng hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/working-with-hyphenation/hyphenation-callback/
---

## Giới thiệu

Này! Bạn đã bao giờ thấy mình vướng vào sự phức tạp của việc định dạng văn bản, đặc biệt là khi xử lý các ngôn ngữ yêu cầu dấu gạch nối chưa? Bạn không cô đơn. Dấu gạch nối, mặc dù rất quan trọng để có bố cục văn bản phù hợp, nhưng có thể hơi đau đầu. Nhưng đoán xem? Aspose.Words for .NET đã hỗ trợ bạn. Thư viện mạnh mẽ này cho phép bạn quản lý định dạng văn bản một cách liền mạch, bao gồm cả việc xử lý dấu gạch nối thông qua cơ chế gọi lại. Có mưu đồ? Hãy cùng tìm hiểu chi tiết về cách bạn có thể triển khai lệnh gọi lại dấu gạch nối bằng cách sử dụng Aspose.Words cho .NET.

## Điều kiện tiên quyết

Trước khi bắt tay vào viết mã, hãy đảm bảo rằng bạn có mọi thứ mình cần:

1.  Aspose.Words for .NET: Đảm bảo bạn có thư viện. Bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
2. IDE: Môi trường phát triển như Visual Studio.
3. Kiến thức cơ bản về C#: Hiểu biết về C# và .NET framework.
4. Từ điển gạch nối: Từ điển gạch nối cho các ngôn ngữ bạn dự định sử dụng.
5.  Giấy phép Aspose: Giấy phép Aspose hợp lệ. Bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) nếu bạn không có.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này đảm bảo mã của chúng tôi có quyền truy cập vào tất cả các lớp và phương thức chúng tôi cần từ Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Bước 1: Đăng ký gọi lại dấu gạch nối

Để bắt đầu, chúng ta cần đăng ký lệnh gọi lại dấu gạch nối. Đây là nơi chúng tôi yêu cầu Aspose.Words sử dụng logic gạch nối tùy chỉnh của chúng tôi.

```csharp
try
{
    // Đăng ký gọi lại dấu gạch nối.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Ở đây, chúng tôi đang tạo một phiên bản gọi lại tùy chỉnh của mình và gán nó cho`Hyphenation.Callback`.

## Bước 2: Xác định đường dẫn tài liệu

Tiếp theo, chúng ta cần xác định thư mục nơi tài liệu của chúng ta được lưu trữ. Điều này rất quan trọng vì chúng tôi sẽ tải và lưu tài liệu từ đường dẫn này.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

## Bước 3: Tải tài liệu

Bây giờ, hãy tải tài liệu yêu cầu gạch nối.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 Ở đây, chúng tôi đang tải một tài liệu văn bản tiếng Đức. Bạn có thể thay thế`"German text.docx"` với tên tệp tài liệu của bạn.

## Bước 4: Lưu tài liệu

Sau khi tải tài liệu, chúng tôi lưu nó vào một tệp mới, áp dụng lệnh gọi lại dấu gạch nối trong quy trình.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Dòng này lưu tài liệu dưới dạng PDF có áp dụng dấu gạch nối.

## Bước 5: Xử lý ngoại lệ từ điển thiếu dấu gạch nối

Đôi khi, bạn có thể gặp phải vấn đề thiếu từ điển gạch nối. Hãy xử lý việc đó.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

Trong khối này, chúng tôi nắm bắt ngoại lệ cụ thể liên quan đến từ điển bị thiếu và in thông báo.

## Bước 6: Triển khai lớp gọi lại dấu gạch nối tùy chỉnh

 Bây giờ chúng ta hãy thực hiện`CustomHyphenationCallback` lớp xử lý yêu cầu về từ điển gạch nối.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Đăng ký từ điển cho ngôn ngữ được yêu cầu.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 Trong lớp này,`RequestDictionary` phương thức này được gọi bất cứ khi nào cần một từ điển gạch nối. Nó kiểm tra ngôn ngữ và đăng ký từ điển thích hợp.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn vừa học cách triển khai lệnh gọi lại dấu gạch nối trong Aspose.Words cho .NET. Bằng cách làm theo các bước này, bạn có thể đảm bảo tài liệu của mình được định dạng đẹp mắt, bất kể ngôn ngữ. Cho dù bạn đang làm việc với tiếng Anh, tiếng Đức hay bất kỳ ngôn ngữ nào khác, phương pháp này cho phép bạn xử lý dấu gạch nối một cách dễ dàng.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện thao tác tài liệu mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu theo chương trình.

### Tại sao gạch nối lại quan trọng trong định dạng tài liệu?
Dấu gạch nối cải thiện bố cục văn bản bằng cách ngắt các từ ở những vị trí thích hợp, đảm bảo tài liệu dễ đọc và hấp dẫn hơn về mặt hình ảnh.

### Tôi có thể sử dụng Aspose.Words miễn phí không?
 Aspose.Words cung cấp bản dùng thử miễn phí. Bạn có thể lấy nó[đây](https://releases.aspose.com/).

### Làm cách nào để có được từ điển gạch nối?
Bạn có thể tải xuống từ điển gạch nối từ nhiều nguồn trực tuyến khác nhau hoặc tự tạo từ điển nếu cần.

### Điều gì xảy ra nếu thiếu từ điển gạch nối?
 Nếu thiếu từ điển,`RequestDictionary` phương thức này sẽ đưa ra một ngoại lệ mà bạn có thể xử lý để thông báo cho người dùng hoặc cung cấp phương án dự phòng.