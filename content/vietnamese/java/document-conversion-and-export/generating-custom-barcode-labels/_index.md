---
title: Tạo nhãn mã vạch tùy chỉnh trong Aspose.Words cho Java
linktitle: Tạo nhãn mã vạch tùy chỉnh
second_title: API xử lý tài liệu Java Aspose.Words
description: Tạo Nhãn mã vạch tùy chỉnh trong Aspose.Words cho Java. Tìm hiểu cách tạo giải pháp mã vạch được cá nhân hóa bằng Aspose.Words cho Java trong hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Giới thiệu về Tạo Nhãn mã vạch tùy chỉnh trong Aspose.Words cho Java

Trong hướng dẫn toàn diện này, chúng tôi sẽ đi sâu vào quy trình tạo nhãn mã vạch tùy chỉnh bằng Aspose.Words cho Java. Aspose.Words cho Java là một API mạnh mẽ cho phép các nhà phát triển thao tác với các tài liệu Word theo chương trình. Một trong những tính năng đáng chú ý của nó là khả năng làm việc với nhãn mã vạch, khiến nó trở thành công cụ có giá trị cho các doanh nghiệp và tổ chức yêu cầu giải pháp mã vạch tùy chỉnh.

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết tạo nhãn mã vạch tùy chỉnh, hãy đảm bảo chúng ta có sẵn các điều kiện tiên quyết:

1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Java và Môi trường phát triển tích hợp (IDE) trên hệ thống của mình.

2.  Aspose.Words for Java: Tải xuống và cài đặt Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).

3. Kiến thức cơ bản về Java: Làm quen với lập trình Java sẽ hữu ích vì chúng ta sẽ viết mã Java để tạo nhãn mã vạch tùy chỉnh.

## Tạo nhãn mã vạch tùy chỉnh

Bây giờ, hãy bắt đầu tạo nhãn mã vạch tùy chỉnh bằng Aspose.Words cho Java. Chúng tôi sẽ chia quy trình thành các bước và cung cấp đoạn mã Java cho từng bước.

## Đặt chiều cao mã vạch

Để bắt đầu, chúng ta cần đặt chiều cao của mã vạch tính bằng twip (1/1440 inch). Sau đó chúng tôi sẽ chuyển đổi giá trị này thành milimét (mm). Đây là mã để thực hiện điều này:

```java
	// Giá trị đầu vào là 1/1440 inch (twps)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Chuyển đổi sang mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Chuyển đổi màu hình ảnh mã vạch

Tiếp theo, chúng ta sẽ chuyển đổi màu hình ảnh mã vạch từ Word sang Aspose.BarCode. Màu đầu vào phải ở định dạng "0xRRGGBB" (thập lục phân). Đây là mã cho việc chuyển đổi:

```java
/// <tóm tắt>
/// Chuyển đổi màu hình ảnh mã vạch từ Word sang Aspose.BarCode.
/// </tóm tắt>
/// <param name="inputColor"></param>
/// <returns></returns>
private static Color convertColor(String inputColor) throws Exception {
	// Đầu vào phải từ "0x000000" đến "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Chuyển đổi hệ số tỷ lệ mã vạch

Bây giờ, chúng tôi sẽ chuyển đổi hệ số tỷ lệ mã vạch từ phần trăm sang giá trị nổi. Hệ số tỷ lệ này xác định kích thước của mã vạch. Đây là mã cho việc chuyển đổi:

```java
/// <tóm tắt>
/// Chuyển đổi hệ số tỷ lệ mã vạch từ phần trăm sang float.
/// </tóm tắt>
/// <param name="scalingFactor"></param>
/// <returns></returns>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## Triển khai phương thức GetBarCodeImage()

 Ở bước này, chúng ta sẽ triển khai`getBarcodeImage` phương pháp tạo ra hình ảnh mã vạch dựa trên các thông số được cung cấp. Chúng tôi sẽ xử lý các loại mã vạch khác nhau, đặt màu, điều chỉnh kích thước, v.v. Đây là mã cho phương pháp này:

```java
/// <tóm tắt>
/// Triển khai phương thức GetBarCodeImage() cho giao diện IBarCodeGenerator.
/// </tóm tắt>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Kiểm tra xem loại và giá trị mã vạch có được cung cấp không
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Tạo Trình tạo mã vạch dựa trên loại mã vạch
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Xử lý các loại mã vạch khác tại đây
	}
	
	// Đặt văn bản mã vạch
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Đặt màu mã vạch
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Đặt chiều cao và kích thước biểu tượng
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Tùy chỉnh vị trí văn bản mã
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Điều chỉnh bổ sung cho mã QR
	final float SCALE = 2.4f; // Hệ số tỷ lệ theo kinh nghiệm để chuyển đổi mã vạch Word sang Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Áp dụng hệ số tỷ lệ
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Tạo và trả lại hình ảnh mã vạch
	return generator.generateBarCodeImage();
}
```

## Triển khai phương thức GetOldBarcodeImage()

 Ở bước này, chúng ta sẽ triển khai`getOldBarcodeImage` phương pháp tạo ra hình ảnh mã vạch cho mã vạch kiểu cũ. Ở đây, chúng tôi sẽ xử lý một loại mã vạch cụ thể, chẳng hạn như POSTNET. Đây là mã cho phương pháp này:

```java
/// <tóm tắt>
/// Triển khai phương thức GetOldBarcodeImage() cho giao diện IBarCodeGenerator.
/// </tóm tắt>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Loại mã cứng dành cho mã vạch lỗi thời
	return generator.generateBarCodeImage();
}
```

## Phần kết luận

Trong bài viết này, chúng tôi đã khám phá quy trình tạo nhãn mã vạch tùy chỉnh bằng Aspose.Words cho Java. Chúng tôi đã đề cập đến các bước thiết yếu, từ việc đặt chiều cao mã vạch đến triển khai các phương pháp tạo mã vạch. Aspose.Words for Java trao quyền cho các nhà phát triển tạo nhãn mã vạch động và tùy chỉnh, biến nó thành một công cụ có giá trị cho các ngành khác nhau.

## Câu hỏi thường gặp

### Làm cách nào để điều chỉnh kích thước của mã vạch được tạo?

Bạn có thể điều chỉnh kích thước của mã vạch được tạo bằng cách đặt chiều cao ký hiệu và hệ số tỷ lệ của mã vạch trong đoạn mã được cung cấp. Các thông số này cho phép bạn kiểm soát kích thước của mã vạch theo yêu cầu của bạn.

### Tôi có thể thay đổi màu sắc của mã vạch không?

Có, bạn có thể thay đổi màu của mã vạch bằng cách chỉ định màu nền trước và màu nền trong mã. Tùy chỉnh này cho phép bạn làm cho hình thức của mã vạch phù hợp với thiết kế tài liệu của bạn.

### Những loại mã vạch nào được Aspose.Words cho Java hỗ trợ?

Aspose.Words for Java hỗ trợ nhiều loại mã vạch khác nhau, bao gồm mã QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14, v.v. Bạn có thể chọn loại mã vạch phù hợp với nhu cầu ứng dụng của mình.

### Làm cách nào để tích hợp mã vạch được tạo vào tài liệu Word của tôi?

Để tích hợp mã vạch được tạo vào tài liệu Word của bạn, bạn có thể sử dụng Aspose.Words cho khả năng thao tác tài liệu của Java. Bạn có thể chèn hình ảnh mã vạch vào tài liệu của mình tại vị trí mong muốn.

### Có mã mẫu nào có sẵn để tùy chỉnh thêm không?

 Có, bạn có thể tìm thấy các đoạn mã mẫu và tài liệu bổ sung trên trang web tham khảo của Aspose.Words dành cho Java:[Aspose.Words để tham khảo API Java](https://reference.aspose.com/words/java/).