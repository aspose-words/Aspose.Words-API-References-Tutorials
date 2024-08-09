---
title: Sử dụng tùy chọn tải trong Aspose.Words cho Java
linktitle: Sử dụng tùy chọn tải
second_title: API xử lý tài liệu Java Aspose.Words
description: Làm chủ các tùy chọn tải trong Aspose.Words cho Java. Tùy chỉnh tải tài liệu, xử lý mã hóa, chuyển đổi hình dạng, đặt phiên bản Word, v.v. để xử lý tài liệu Java hiệu quả.
type: docs
weight: 11
url: /vi/java/document-loading-and-saving/using-load-options/
---

## Giới thiệu về Làm việc với các tùy chọn tải trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với Tùy chọn tải trong Aspose.Words cho Java. Tùy chọn tải cho phép bạn tùy chỉnh cách tải và xử lý tài liệu. Chúng tôi sẽ đề cập đến nhiều tình huống khác nhau, bao gồm cập nhật các trường bẩn, tải tài liệu được mã hóa, chuyển đổi hình dạng sang Office Math, đặt phiên bản MS Word, chỉ định thư mục tạm thời, xử lý cảnh báo và chuyển đổi siêu tệp sang PNG. Hãy đi sâu vào từng bước một.

## Cập nhật trường bẩn

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Đoạn mã này trình bày cách cập nhật các trường không chính xác trong tài liệu. các`setUpdateDirtyFields(true)` phương pháp được sử dụng để đảm bảo rằng các trường bẩn được cập nhật trong quá trình tải tài liệu.

## Tải tài liệu được mã hóa

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Ở đây, chúng tôi tải một tài liệu được mã hóa bằng mật khẩu. các`LoadOptions` hàm tạo chấp nhận mật khẩu tài liệu và bạn cũng có thể chỉ định mật khẩu mới khi lưu tài liệu bằng cách sử dụng`OdtSaveOptions`.

## Chuyển đổi hình dạng sang Office Math

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Mã này trình bày cách chuyển đổi hình dạng thành đối tượng Office Math trong quá trình tải tài liệu. các`setConvertShapeToOfficeMath(true)`phương pháp cho phép chuyển đổi này.

## Đặt phiên bản MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Bạn có thể chỉ định phiên bản MS Word để tải tài liệu. Trong ví dụ này, chúng tôi đặt phiên bản thành Microsoft Word 2010 bằng cách sử dụng`setMswVersion`.

## Sử dụng thư mục tạm thời

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Bằng cách đặt thư mục tạm thời bằng cách sử dụng`setTempFolder`, bạn có thể kiểm soát nơi lưu trữ các tệp tạm thời trong quá trình xử lý tài liệu.

## Cảnh báo gọi lại

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Xử lý các cảnh báo khi chúng phát sinh trong quá trình tải tài liệu.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Mã này trình bày cách thiết lập lệnh gọi lại cảnh báo để xử lý các cảnh báo trong quá trình tải tài liệu. Bạn có thể tùy chỉnh hành vi của ứng dụng khi cảnh báo xảy ra.

## Chuyển đổi siêu tập tin sang PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Để chuyển đổi siêu tập tin (ví dụ: WMF) sang hình ảnh PNG trong khi tải tài liệu, bạn có thể sử dụng`setConvertMetafilesToPng(true)` phương pháp.

## Mã nguồn hoàn chỉnh để làm việc với các tùy chọn tải trong Aspose.Words cho Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// Tạo đối tượng LoadOptions mới, mặc định sẽ tải tài liệu theo thông số MS Word 2019
	// và thay đổi phiên bản tải thành Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//In cảnh báo và thông tin chi tiết khi chúng phát sinh trong quá trình tải tài liệu.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã đi sâu vào các khía cạnh khác nhau khi làm việc với Tùy chọn tải trong Aspose.Words cho Java. Tùy chọn tải đóng một vai trò quan trọng trong việc tùy chỉnh cách tải và xử lý tài liệu, cho phép bạn điều chỉnh quá trình xử lý tài liệu theo nhu cầu cụ thể của mình. Hãy tóm tắt lại những điểm chính được đề cập trong hướng dẫn này:

## Câu hỏi thường gặp

### Làm cách nào để xử lý các cảnh báo trong quá trình tải tài liệu?

 Bạn có thể thiết lập cuộc gọi lại cảnh báo như trong`warningCallback()` phương pháp trên. Tùy chỉnh`DocumentLoadingWarningCallback` class để xử lý các cảnh báo theo yêu cầu của ứng dụng của bạn.

### Tôi có thể chuyển đổi hình dạng thành đối tượng Office Math khi tải tài liệu không?

 Có, bạn có thể chuyển đổi hình dạng thành đối tượng Office Math bằng cách sử dụng`loadOptions.setConvertShapeToOfficeMath(true)`.

### Làm cách nào để chỉ định phiên bản MS Word để tải tài liệu?

 Sử dụng`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` để chỉ định phiên bản MS Word để tải tài liệu.

###  Mục đích của việc này là gì`setTempFolder` method in Load Options?

 các`setTempFolder`phương pháp cho phép bạn chỉ định thư mục lưu trữ các tệp tạm thời trong quá trình xử lý tài liệu.