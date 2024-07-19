---
title: Định dạng số nhãn dữ liệu trong biểu đồ
linktitle: Định dạng số nhãn dữ liệu trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định dạng nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET với hướng dẫn từng bước này. Cải thiện tài liệu Word của bạn một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-charts/format-number-of-data-label/
---
## Giới thiệu

Việc tạo tài liệu hấp dẫn và giàu thông tin thường liên quan đến việc bao gồm các biểu đồ có nhãn dữ liệu được định dạng tốt. Nếu bạn là nhà phát triển .NET đang tìm cách nâng cao tài liệu Word của mình bằng các biểu đồ phức tạp thì Aspose.Words for .NET là một thư viện tuyệt vời giúp bạn đạt được điều đó. Hướng dẫn này sẽ hướng dẫn bạn quy trình định dạng nhãn số trong biểu đồ bằng Aspose.Words cho .NET, từng bước một.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, bạn cần phải có một số điều kiện tiên quyết:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words for .NET. Nếu bạn chưa cài đặt nó, bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Bạn nên thiết lập môi trường phát triển .NET. Visual Studio rất được khuyến khích.
- Kiến thức cơ bản về C#: Làm quen với lập trình C# là điều cần thiết vì hướng dẫn này liên quan đến việc viết và hiểu mã C#.
-  Giấy phép tạm thời: Để sử dụng Aspose.Words mà không có bất kỳ giới hạn nào, bạn có thể nhận được[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

Bây giờ, hãy đi sâu vào quy trình từng bước định dạng nhãn số trong biểu đồ.

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết để hoạt động với Aspose.Words cho .NET. Thêm các dòng sau vào đầu tệp C# của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước khi có thể bắt đầu thao tác với tài liệu Word của mình, bạn cần chỉ định thư mục nơi tài liệu của bạn sẽ được lưu. Điều này rất cần thiết cho thao tác lưu sau này.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Khởi tạo Document và DocumentBuilder

 Bước tiếp theo là khởi tạo một`Document` và một`DocumentBuilder` . Các`DocumentBuilder` là một lớp trợ giúp cho phép chúng ta xây dựng nội dung tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn biểu đồ vào tài liệu

 Bây giờ, hãy chèn biểu đồ vào tài liệu bằng cách sử dụng`DocumentBuilder`. Trong hướng dẫn này, chúng ta sẽ sử dụng biểu đồ Đường làm ví dụ.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Ở đây, chúng tôi chèn biểu đồ Đường có chiều rộng và chiều cao cụ thể, đồng thời đặt tiêu đề cho biểu đồ.

## Bước 4: Xóa chuỗi mặc định và thêm chuỗi mới

Theo mặc định, biểu đồ sẽ có một số chuỗi được tạo trước. Chúng ta cần xóa những thứ này và thêm chuỗi của riêng mình với các điểm dữ liệu cụ thể.

```csharp
// Xóa chuỗi được tạo mặc định.
chart.Series.Clear();

// Thêm chuỗi mới với các điểm dữ liệu tùy chỉnh.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Bước 5: Kích hoạt nhãn dữ liệu

Để hiển thị nhãn dữ liệu trên biểu đồ, chúng ta cần kích hoạt chúng cho chuỗi của mình.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Bước 6: Định dạng nhãn dữ liệu

Cốt lõi của hướng dẫn này là định dạng nhãn dữ liệu. Chúng ta có thể áp dụng các định dạng số khác nhau cho từng nhãn dữ liệu riêng lẻ.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Định dạng tiền tệ
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Định dạng ngày tháng
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Định dạng phần trăm
```

 Ngoài ra, bạn có thể liên kết định dạng của nhãn dữ liệu với ô nguồn. Khi được liên kết,`NumberFormat` sẽ được đặt lại về trạng thái chung và được kế thừa từ ô nguồn.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Bước 7: Lưu tài liệu

Cuối cùng, lưu tài liệu vào thư mục được chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Thao tác này sẽ lưu tài liệu của bạn với tên được chỉ định và đảm bảo biểu đồ của bạn có nhãn dữ liệu được định dạng được giữ nguyên.

## Phần kết luận

Định dạng nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET có thể nâng cao đáng kể khả năng đọc và tính chuyên nghiệp của tài liệu Word của bạn. Bằng cách làm theo hướng dẫn từng bước này, giờ đây bạn có thể tạo biểu đồ, thêm chuỗi dữ liệu và định dạng nhãn dữ liệu để đáp ứng nhu cầu của mình. Aspose.Words for .NET là một công cụ mạnh mẽ cho phép tùy chỉnh và tự động hóa rộng rãi các tài liệu Word, khiến nó trở thành tài sản vô giá đối với các nhà phát triển .NET.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, thao tác và chuyển đổi tài liệu Word theo chương trình bằng C#.

### Tôi có thể định dạng các loại biểu đồ khác bằng Aspose.Words cho .NET không?
Có, Aspose.Words for .NET hỗ trợ nhiều loại biểu đồ khác nhau, bao gồm thanh, cột, hình tròn, v.v.

### Làm cách nào để có được giấy phép tạm thời cho Aspose.Words cho .NET?
 Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Có thể liên kết nhãn dữ liệu với các ô nguồn trong Excel không?
Có, bạn có thể liên kết nhãn dữ liệu với các ô nguồn, cho phép kế thừa định dạng số từ ô nguồn.

### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/words/net/).
