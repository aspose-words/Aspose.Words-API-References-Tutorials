---
title: Đánh dấu căn chỉnh nhãn nhiều dòng trong biểu đồ
linktitle: Đánh dấu căn chỉnh nhãn nhiều dòng trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách căn chỉnh các nhãn nhiều dòng trong trục biểu đồ bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/tick-multi-line-label-alignment/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để đặt căn chỉnh các nhãn nhiều dòng trong trục biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, truy cập trục và sửa đổi căn chỉnh nhãn đánh dấu.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng cách sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ.

 Tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ phân tán vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Bước 3: Đặt căn chỉnh nhãn đánh dấu

 Để đặt căn chỉnh các nhãn nhiều dòng, hãy truy cập vào`AxisX` thuộc tính của biểu đồ và thiết lập`TickLabelAlignment` thuộc tính theo sự căn chỉnh mong muốn. Trong ví dụ này, chúng tôi đặt căn chỉnh thành`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Điều này hoàn tất việc thực hiện thiết lập căn chỉnh nhãn nhiều dòng bằng cách sử dụng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Đánh dấu căn chỉnh nhãn nhiều dòng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Thuộc tính này chỉ có hiệu lực đối với nhãn nhiều dòng.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách thiết lập căn chỉnh các nhãn nhiều dòng đánh dấu trên trục biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ phân tán, truy cập trục biểu đồ và sửa đổi căn chỉnh nhãn đánh dấu.

Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để thao tác biểu đồ trong tài liệu Word. Đánh dấu nhãn nhiều dòng rất hữu ích khi nhãn trục chứa văn bản dài yêu cầu ngắt dòng hoặc tách thành nhiều dòng. Bằng cách đặt căn chỉnh nhãn đánh dấu, bạn có thể kiểm soát căn chỉnh theo chiều ngang của các nhãn nhiều dòng trong trục biểu đồ, đảm bảo khả năng trình bày và dễ đọc tối ưu.

Tùy chỉnh căn chỉnh nhãn nhiều dòng đánh dấu cho phép bạn tinh chỉnh giao diện biểu đồ của mình, đặc biệt khi xử lý các nhãn dài hoặc phức tạp. Bằng cách căn chỉnh các nhãn sang phải, trái, giữa hoặc căn đều, bạn có thể đạt được sự sắp xếp cân bằng và hấp dẫn về mặt trực quan của các nhãn đánh dấu dọc theo trục.

Với Aspose.Words for .NET, bạn có thể dễ dàng truy cập và sửa đổi thuộc tính căn chỉnh nhãn đánh dấu của trục biểu đồ, cung cấp cho bạn toàn quyền kiểm soát hình thức và bố cục của nhãn đánh dấu trong biểu đồ tài liệu Word của bạn.

### Câu hỏi thường gặp

#### Q1. Đánh dấu các nhãn nhiều dòng trong trục biểu đồ là gì?
Đánh dấu nhãn nhiều dòng trong trục biểu đồ đề cập đến các nhãn trục trải dài trên nhiều dòng khi văn bản nhãn dài hoặc yêu cầu ngắt dòng để vừa với không gian có sẵn. Thay vì cắt bớt văn bản nhãn hoặc gây lộn xộn về mặt hình ảnh, trục biểu đồ sẽ tự động chia nhãn thành nhiều dòng để đảm bảo khả năng đọc. Đánh dấu các nhãn nhiều dòng đặc biệt hữu ích khi xử lý các nhãn danh mục hoặc giá trị dài trong biểu đồ.

#### Q2. Tôi có thể tùy chỉnh căn chỉnh nhãn đánh dấu trong trục biểu đồ không?
 Có, bạn có thể tùy chỉnh căn chỉnh các nhãn đánh dấu trong trục biểu đồ bằng Aspose.Words for .NET. Bằng cách truy cập vào`TickLabelAlignment` tài sản của`ChartAxis` đối tượng, bạn có thể đặt căn chỉnh mong muốn cho nhãn đánh dấu. Các tùy chọn căn chỉnh bao gồm căn trái, phải, giữa hoặc căn đều. Việc điều chỉnh căn chỉnh cho phép bạn kiểm soát vị trí nằm ngang của nhãn đánh dấu dọc theo trục biểu đồ, đảm bảo khả năng đọc và trình bày trực quan phù hợp.

#### Q3. Khi nào tôi nên cân nhắc việc thay đổi căn chỉnh nhãn đánh dấu trong trục biểu đồ?
Việc thay đổi căn chỉnh nhãn đánh dấu trong trục biểu đồ sẽ có lợi khi bạn có nhãn dài hoặc nhiều dòng yêu cầu trình bày và dễ đọc tối ưu. Bằng cách điều chỉnh căn chỉnh, bạn có thể đảm bảo rằng các nhãn được căn chỉnh và giãn cách hợp lý, tránh chồng chéo hoặc cắt bớt. Hãy cân nhắc việc thay đổi căn chỉnh nhãn đánh dấu khi xử lý các biểu đồ có tên danh mục dài, nhãn giá trị dài dòng hoặc bất kỳ trường hợp nào khác mà căn chỉnh mặc định không mang lại hình thức trực quan như mong muốn.

#### Q4. Việc căn chỉnh nhãn đánh dấu có ảnh hưởng đến nhãn một dòng trong trục biểu đồ không?
Không, thuộc tính căn chỉnh nhãn đánh dấu không ảnh hưởng đến các nhãn một dòng trong trục biểu đồ. Nó được thiết kế đặc biệt cho các nhãn nhiều dòng yêu cầu bọc hoặc tách. Nhãn một dòng được căn chỉnh dựa trên cài đặt căn chỉnh mặc định của trục biểu đồ. Thuộc tính căn chỉnh nhãn đánh dấu chỉ áp dụng cho các nhãn trải dài trên nhiều dòng, cho phép bạn kiểm soát việc căn chỉnh từng dòng trong nhãn nhiều dòng.

#### Q5. Tôi có thể căn chỉnh các nhãn đánh dấu khác nhau cho trục X và trục Y trong biểu đồ không?
 Có, bạn có thể căn chỉnh các nhãn đánh dấu khác nhau cho trục X và trục Y trong biểu đồ bằng Aspose.Words for .NET. Thuộc tính căn chỉnh nhãn đánh dấu dành riêng cho từng trục biểu đồ. Bằng cách truy cập tương ứng`ChartAxis` đối tượng cho trục X hoặc trục Y, bạn có thể đặt căn chỉnh nhãn đánh dấu một cách độc lập thành các giá trị khác nhau. Điều này mang lại cho bạn sự linh hoạt để căn chỉnh các nhãn đánh dấu khác nhau dựa trên yêu cầu cụ thể của bạn đối với từng trục trong biểu đồ.