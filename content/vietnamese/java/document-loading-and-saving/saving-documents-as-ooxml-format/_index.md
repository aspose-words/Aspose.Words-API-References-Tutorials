---
title: Lưu tài liệu dưới định dạng OOXML trong Aspose.Words cho Java
linktitle: Lưu tài liệu dưới định dạng OOXML
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách lưu tài liệu ở định dạng OOXML bằng Aspose.Words cho Java. Bảo mật, tối ưu hóa và tùy chỉnh các tập tin của bạn một cách dễ dàng.
type: docs
weight: 20
url: /vi/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Giới thiệu về Lưu tài liệu dưới định dạng OOXML trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu tài liệu ở định dạng OOXML bằng Aspose.Words cho Java. OOXML (Office Open XML) là định dạng tệp được sử dụng bởi Microsoft Word và các ứng dụng văn phòng khác. Chúng tôi sẽ đề cập đến các tùy chọn và cài đặt khác nhau để lưu tài liệu ở định dạng OOXML.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Words for Java trong dự án của mình.

## Lưu tài liệu bằng mã hóa mật khẩu

Bạn có thể mã hóa tài liệu của mình bằng mật khẩu trong khi lưu nó ở định dạng OOXML. Đây là cách bạn có thể làm điều đó:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Tải tài liệu
Document doc = new Document("Document.docx");

// Tạo OoxmlSaveOptions và đặt mật khẩu
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Lưu tài liệu bằng mã hóa
doc.save("EncryptedDoc.docx", saveOptions);
```

## Thiết lập tuân thủ OOXML

Bạn có thể chỉ định mức độ tuân thủ OOXML khi lưu tài liệu. Ví dụ: bạn có thể đặt thành ISO 29500:2008 (Nghiêm ngặt). Đây là cách thực hiện:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Tải tài liệu
Document doc = new Document("Document.docx");

// Tối ưu hóa cho Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Tạo OoxmlSaveOptions và đặt mức độ tuân thủ
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Lưu tài liệu với cài đặt tuân thủ
doc.save("ComplianceDoc.docx", saveOptions);
```

## Cập nhật thuộc tính thời gian đã lưu lần cuối

Bạn có thể chọn cập nhật thuộc tính "Thời gian lưu lần cuối" của tài liệu khi lưu nó. Đây là cách thực hiện:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Tải tài liệu
Document doc = new Document("Document.docx");

// Tạo OoxmlSaveOptions và cho phép cập nhật thuộc tính Thời gian lưu lần cuối
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Lưu tài liệu với thuộc tính được cập nhật
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Giữ các ký tự kiểm soát kế thừa

Nếu tài liệu của bạn chứa các ký tự điều khiển kế thừa, bạn có thể chọn giữ chúng trong khi lưu. Đây là cách thực hiện:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Tải tài liệu có các ký tự điều khiển kế thừa
Document doc = new Document("LegacyControlChars.doc");

//Tạo OoxmlSaveOptions với định dạng FLAT_OPC và cho phép giữ các ký tự điều khiển kế thừa
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Lưu tài liệu với các ký tự điều khiển kế thừa
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Đặt mức nén

Bạn có thể điều chỉnh mức độ nén khi lưu tài liệu. Ví dụ: bạn có thể đặt thành SUPER_FAST để nén tối thiểu. Đây là cách thực hiện:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Tải tài liệu
Document doc = new Document("Document.docx");

// Tạo OoxmlSaveOptions và đặt mức nén
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Lưu tài liệu với mức nén được chỉ định
doc.save("FastCompressionDoc.docx", saveOptions);
```

Đây là một số tùy chọn và cài đặt chính mà bạn có thể sử dụng khi lưu tài liệu ở định dạng OOXML bằng Aspose.Words cho Java. Vui lòng khám phá thêm tùy chọn và tùy chỉnh quy trình lưu tài liệu của bạn nếu cần.

## Mã nguồn hoàn chỉnh để lưu tài liệu dưới định dạng OOXML trong Aspose.Words cho Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Phần kết luận

Trong hướng dẫn toàn diện này, chúng tôi đã khám phá cách lưu tài liệu ở định dạng OOXML bằng Aspose.Words cho Java. Cho dù bạn cần mã hóa tài liệu của mình bằng mật khẩu, đảm bảo tuân thủ các tiêu chuẩn OOXML cụ thể, cập nhật thuộc tính tài liệu, giữ nguyên các ký tự điều khiển cũ hay điều chỉnh mức độ nén, Aspose.Words đều cung cấp một bộ công cụ linh hoạt để đáp ứng yêu cầu của bạn.

## Câu hỏi thường gặp

### Làm cách nào để xóa bảo vệ bằng mật khẩu khỏi tài liệu được bảo vệ bằng mật khẩu?

Để xóa bảo vệ bằng mật khẩu khỏi tài liệu được bảo vệ bằng mật khẩu, bạn có thể mở tài liệu bằng mật khẩu chính xác rồi lưu nó mà không cần chỉ định mật khẩu trong tùy chọn lưu. Điều này sẽ lưu tài liệu mà không cần bảo vệ bằng mật khẩu.

### Tôi có thể đặt thuộc tính tùy chỉnh khi lưu tài liệu ở định dạng OOXML không?

 Có, bạn có thể đặt thuộc tính tùy chỉnh cho tài liệu trước khi lưu nó ở định dạng OOXML. Sử dụng`BuiltInDocumentProperties`Và`CustomDocumentProperties` các lớp để đặt các thuộc tính khác nhau như tác giả, tiêu đề, từ khóa và thuộc tính tùy chỉnh.

### Mức nén mặc định khi lưu tài liệu ở định dạng OOXML là bao nhiêu?

 Mức nén mặc định khi lưu tài liệu ở định dạng OOXML bằng Aspose.Words cho Java là`NORMAL` . Bạn có thể thay đổi mức độ nén thành`SUPER_FAST` hoặc`MAXIMUM` khi cần thiết.