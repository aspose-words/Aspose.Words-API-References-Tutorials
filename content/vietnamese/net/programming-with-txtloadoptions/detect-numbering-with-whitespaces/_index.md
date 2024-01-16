---
title: Phát hiện đánh số bằng khoảng trắng
linktitle: Phát hiện đánh số bằng khoảng trắng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách phát hiện số danh sách có khoảng trắng trong Aspose.Words for .NET. Cải thiện cấu trúc tài liệu của bạn một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp cho tính năng "Phát hiện đánh số bằng khoảng trắng" với Aspose.Words for .NET. Tính năng này cho phép bạn phát hiện và tạo danh sách từ tài liệu văn bản chứa số danh sách theo sau là khoảng trắng.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Tạo tài liệu văn bản

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Trong bước này, chúng ta tạo một chuỗi văn bản mô phỏng một tài liệu văn bản chứa các số danh sách theo sau là khoảng trắng. Chúng tôi sử dụng các dấu phân cách danh sách khác nhau như dấu chấm, dấu ngoặc phải, ký hiệu dấu đầu dòng và khoảng trắng.

## Bước 3: Định cấu hình tùy chọn tải lên

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn tải tài liệu. Chúng tôi tạo ra một cái mới`TxtLoadOptions` đối tượng và thiết lập`DetectNumberingWithWhitespaces`tài sản để`true`. Điều này sẽ cho phép Aspose.Words phát hiện số danh sách ngay cả khi chúng được theo sau bởi khoảng trắng.

## Bước 4: Tải tài liệu và lưu

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Trong bước này, chúng tôi tải tài liệu bằng chuỗi văn bản đã chỉ định và các tùy chọn tải. Chúng tôi sử dụng một`MemoryStream` để chuyển đổi chuỗi văn bản thành luồng bộ nhớ. Sau đó, chúng tôi lưu tài liệu kết quả ở định dạng .docx.

### Mã nguồn mẫu cho tính năng Phát hiện đánh số khoảng trắng với Aspose.Words cho .NET.

```csharp

            
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Tạo một tài liệu văn bản gốc ở dạng một chuỗi với các phần có thể được hiểu là danh sách.
// Khi tải, ba danh sách đầu tiên sẽ luôn được Aspose.Words phát hiện,
// và các đối tượng List sẽ được tạo cho chúng sau khi tải.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Danh sách thứ tư, có khoảng trắng giữa số danh sách và nội dung mục danh sách,
// sẽ chỉ được phát hiện dưới dạng danh sách nếu "DetectNumberingWithWhitespaces" trong đối tượng LoadOptions được đặt thành true,
// để tránh các đoạn văn bắt đầu bằng số bị phát hiện nhầm là danh sách.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Tải tài liệu trong khi áp dụng LoadOptions làm tham số và xác minh kết quả.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Bây giờ bạn có thể chạy mã nguồn để tải tài liệu văn bản chứa số danh sách có khoảng trắng, sau đó tạo tài liệu .docx với các danh sách được phát hiện. Tệp đầu ra sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá tính năng phát hiện đánh số khoảng trắng trong Aspose.Words dành cho .NET. Chúng tôi đã học cách tạo danh sách từ một tài liệu văn bản chứa số danh sách theo sau là khoảng trắng.

Tính năng này cực kỳ hữu ích để xử lý các tài liệu chứa số danh sách được định dạng theo nhiều cách khác nhau. Bằng cách sử dụng các tùy chọn tải thích hợp, Aspose.Words có thể phát hiện các số danh sách này, ngay cả khi chúng được theo sau bởi khoảng trắng và chuyển đổi chúng thành danh sách có cấu trúc trong tài liệu cuối cùng.

Sử dụng tính năng này có thể giúp bạn tiết kiệm thời gian và cải thiện hiệu quả công việc của bạn. Bạn có thể dễ dàng trích xuất thông tin từ tài liệu văn bản và chuyển đổi chúng thành tài liệu có cấu trúc tốt với danh sách phù hợp.

Hãy nhớ xem xét các tùy chọn tải, chẳng hạn như định cấu hình phát hiện quay số khoảng trắng, để đạt được kết quả mong muốn.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Bằng cách khám phá sâu hơn các tài liệu và ví dụ do Aspose.Words cung cấp, bạn sẽ có thể khai thác triệt để các khả năng của thư viện mạnh mẽ này.

Vì vậy, đừng ngần ngại tích hợp tính năng phát hiện đánh số khoảng trắng vào các dự án Aspose.Words for .NET của bạn và tận dụng các lợi ích của nó để tạo các tài liệu có cấu trúc tốt và dễ đọc.


