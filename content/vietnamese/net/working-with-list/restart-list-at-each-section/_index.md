---
title: Danh sách khởi động lại ở mỗi phần
linktitle: Danh sách khởi động lại ở mỗi phần
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt lại danh sách được đánh số cho từng phần trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-list/restart-list-at-each-section/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách đặt lại danh sách được đánh số cho từng phần trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Tạo tài liệu và danh sách

Đầu tiên, tạo một tài liệu mới và thêm danh sách được đánh số mặc định:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Bước 2: Thêm mục vào danh sách

 Sau đó sử dụng một`DocumentBuilder` để thêm các mục vào danh sách. Bạn có thể sử dụng vòng lặp để thêm nhiều mục vào danh sách:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Trong ví dụ này, chúng tôi chèn dấu ngắt phần sau mục danh sách thứ 15 để minh họa việc đánh số lại.

## Bước 3: Lưu tài liệu đã sửa đổi

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Vì thế ! Bạn đã đặt lại thành công danh sách được đánh số cho từng phần trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn ví dụ để đặt lại danh sách ở mỗi phần

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó cho phù hợp với nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể khởi động lại danh sách ở mọi phần trong Aspose.Words?

 Trả lời: Để khởi động lại danh sách ở mọi phần trong Aspose.Words, bạn cần tạo một phiên bản của`List`lớp và gán một danh sách đánh số cho nó. Sau đó bạn có thể sử dụng`List.IsRestartAtEachSection` thuộc tính để chỉ định việc đánh số sẽ được khởi động lại ở mỗi phần. Bạn có thể liên kết danh sách này với một hoặc nhiều phần trong tài liệu của mình để việc đánh số được bắt đầu lại chính xác ở mỗi phần.

#### Câu hỏi: Tôi có thể tùy chỉnh định dạng đánh số của danh sách trong Aspose.Words không?

 Trả lời: Có, bạn có thể tùy chỉnh định dạng đánh số của danh sách trong Aspose.Words. Các`List` lớp cung cấp một số thuộc tính cho việc này, chẳng hạn như`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, v.v. Bạn có thể sử dụng các thuộc tính này để đặt loại danh sách (đánh số, đánh dấu đầu dòng, v.v.), định dạng đánh số (chữ số Ả Rập, chữ số La Mã, chữ cái, v.v.) và các tùy chọn định dạng đánh số khác.

#### Câu hỏi: Có thể thêm các cấp độ bổ sung vào danh sách được đánh số trong Aspose.Words không?

 Trả lời: Có, có thể thêm các cấp độ bổ sung vào danh sách được đánh số trong Aspose.Words. Các`ListLevel`class cho phép bạn đặt thuộc tính định dạng cho từng cấp độ của danh sách. Bạn có thể đặt các tùy chọn như tiền tố, hậu tố, căn chỉnh, thụt lề, v.v. Điều này cho phép bạn tạo danh sách với nhiều cấp độ phân cấp.