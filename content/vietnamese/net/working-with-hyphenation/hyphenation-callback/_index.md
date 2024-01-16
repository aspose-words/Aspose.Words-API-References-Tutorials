---
title: Gọi lại dấu gạch nối
linktitle: Gọi lại dấu gạch nối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng lệnh gọi lại dấu gạch nối trong Aspose.Words cho .NET để xử lý dấu gạch nối từ.
type: docs
weight: 10
url: /vi/net/working-with-hyphenation/hyphenation-callback/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách sử dụng tính năng gọi lại dấu gạch nối trong Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Lưu lời nhắc gạch nối

 Đầu tiên, chúng ta sẽ đăng ký lệnh gọi lại dấu gạch nối bằng cách sử dụng một tùy chỉnh`CustomHyphenationCallback` lớp học. Điều này sẽ cho phép chúng tôi xử lý việc gạch nối từ theo quy tắc riêng của chúng tôi:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Hãy chắc chắn rằng bạn đã triển khai`CustomHyphenationCallback` lớp học theo nhu cầu cụ thể của bạn.

## Bước 2: Tải tài liệu và áp dụng dấu gạch nối

Tiếp theo, tải tài liệu của bạn từ thư mục đã chỉ định và gạch nối các từ bằng Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Bước 3: Xử lý lỗi thiếu từ điển

Trong trường hợp thiếu từ điển gạch nối, chúng ta sẽ bắt ngoại lệ tương ứng và hiển thị thông báo lỗi:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Bước 4: Dọn dẹp và tắt lời nhắc gạch nối

Cuối cùng, để sạch sẽ và tắt lời nhắc gạch nối, hãy thực hiện các bước sau:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Thao tác này sẽ dọn sạch và tắt lời nhắc gạch nối sau khi xử lý xong.

Vì thế ! Bạn đã sử dụng thành công lệnh gọi lại dấu gạch nối trong Aspose.Words cho .NET.

### Mã nguồn mẫu cho lệnh gọi lại gạch nối với Aspose.Words cho .NET

```csharp
try
{
	 // Đăng ký gọi lại dấu gạch nối.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó cho phù hợp với nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Lời nhắc về âm tiết trong Aspose.Words là gì?

Trả lời: Lời nhắc về âm tiết trong Aspose.Words là một tính năng cho phép bạn tùy chỉnh cách các từ được âm tiết trong tài liệu của bạn. Bằng cách sử dụng lời nhắc về âm tiết, bạn có thể chỉ định các quy tắc tùy chỉnh cho âm tiết của từ, điều này có thể hữu ích cho các ngôn ngữ cụ thể hoặc các tình huống cụ thể trong đó âm tiết mặc định không mang lại kết quả mong muốn.

#### Hỏi: Làm cách nào để đặt lời nhắc về âm tiết trong Aspose.Words?

 Trả lời: Để xác định lệnh gọi lại dấu gạch nối trong Aspose.Words, bạn cần tạo một lớp triển khai`HyphenationCallback` giao diện và thực hiện các`HandleWord()` phương pháp. Phương pháp này sẽ được gọi cho mỗi từ gặp phải trong quá trình sắp xếp âm tiết. Bạn có thể áp dụng các quy tắc âm tiết tùy chỉnh cho nó và trả về từ có âm tiết. Sau đó, bạn có thể liên kết lệnh gọi lại dấu gạch nối của mình bằng cách sử dụng`Document.HyphenationCallback` thuộc tính của tài liệu của bạn.

#### Hỏi: Lợi ích của việc sử dụng lời nhắc về âm tiết trong Aspose.Words là gì?

Trả lời: Lợi ích của việc sử dụng lời nhắc về âm tiết trong Aspose.Words là khả năng tùy chỉnh cách các từ được sắp xếp âm tiết trong tài liệu của bạn. Điều này cho phép bạn kiểm soát nhiều hơn đối với cách sắp xếp âm tiết, đặc biệt đối với các ngôn ngữ hoặc tình huống cụ thể mà cách sắp xếp âm tiết mặc định không mang lại kết quả như mong muốn. Bạn có thể áp dụng các quy tắc cụ thể cho từng từ để có được âm tiết chính xác theo nhu cầu của mình.

#### Hỏi: Một số tình huống phổ biến mà việc sử dụng lời nhắc về âm tiết có thể hữu ích là gì?

Đáp: Việc sử dụng bộ tăng cường âm tiết có thể hữu ích trong một số trường hợp, chẳng hạn như:
- Âm tiết của các từ trong các ngôn ngữ cụ thể có quy tắc âm tiết cụ thể.
- Việc áp dụng các quy tắc âm tiết được cá nhân hóa cho các từ viết tắt hoặc từ kỹ thuật.
- Điều chỉnh âm tiết theo sở thích về văn phong hoặc tiêu chuẩn đánh máy.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra cách sắp xếp âm tiết tùy chỉnh bằng lời nhắc về cách sắp xếp âm tiết trong Aspose.Words?

 Trả lời: Để kiểm tra cách sắp xếp âm tiết tùy chỉnh bằng lời nhắc về cách sắp xếp âm tiết trong Aspose.Words, bạn có thể tạo một tài liệu kiểm tra chứa các từ mà bạn muốn áp dụng quy tắc sắp xếp âm tiết tùy chỉnh. Sau đó, bạn có thể đặt lệnh gọi lại âm tiết tùy chỉnh của mình, gọi`Document.Range.Replace()` phương pháp thay thế các từ trong tài liệu và sử dụng`Hyphenate()` phương pháp của`Hyphenation` lớp để có được âm tiết của các từ. Sau đó, bạn có thể định dạng các từ có âm tiết nếu cần, ví dụ bằng cách thêm dấu gạch nối giữa các âm tiết.