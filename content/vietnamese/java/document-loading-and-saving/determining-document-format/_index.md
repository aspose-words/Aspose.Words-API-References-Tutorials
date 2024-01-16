---
title: Xác định định dạng tài liệu trong Aspose.Words cho Java
linktitle: Xác định định dạng tài liệu
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách phát hiện các định dạng tài liệu trong Java bằng Aspose.Words. Xác định DOC, DOCX, v.v. Sắp xếp tập tin hiệu quả.
type: docs
weight: 25
url: /vi/java/document-loading-and-saving/determining-document-format/
---

## Giới thiệu về Xác định định dạng tài liệu trong Aspose.Words cho Java

Khi làm việc với việc xử lý tài liệu trong Java, điều quan trọng là phải xác định định dạng của tệp bạn đang xử lý. Aspose.Words for Java cung cấp các tính năng mạnh mẽ để xác định các định dạng tài liệu và chúng tôi sẽ hướng dẫn bạn thực hiện quy trình này.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- [Aspose.Words cho Java](https://releases.aspose.com/words/java/)
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn
- Kiến thức cơ bản về lập trình Java

## Bước 1: Thiết lập thư mục

Đầu tiên, chúng ta cần thiết lập các thư mục cần thiết để sắp xếp các tập tin của mình một cách hiệu quả. Chúng tôi sẽ tạo thư mục cho các loại tài liệu khác nhau.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Tạo các thư mục nếu chúng chưa tồn tại.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Chúng tôi đã tạo các thư mục cho các loại tài liệu được hỗ trợ, không xác định, được mã hóa và trước 97.

## Bước 2: Phát hiện định dạng tài liệu

Bây giờ, hãy phát hiện định dạng của tài liệu trong thư mục của chúng tôi. Chúng tôi sẽ sử dụng Aspose.Words for Java để đạt được điều này.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Hiển thị loại tài liệu
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Thêm trường hợp cho các định dạng tài liệu khác nếu cần
    }

    // Xử lý tài liệu được mã hóa
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Xử lý các loại tài liệu khác
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

Trong đoạn mã này, chúng tôi lặp qua các tệp, phát hiện định dạng của chúng và sắp xếp chúng vào các thư mục tương ứng.

## Mã nguồn hoàn chỉnh để xác định định dạng tài liệu trong Aspose.Words cho Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Tạo các thư mục nếu chúng chưa tồn tại.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Hiển thị loại tài liệu
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Phần kết luận

Xác định định dạng tài liệu trong Aspose.Words cho Java là điều cần thiết để xử lý tài liệu hiệu quả. Với các bước được nêu trong hướng dẫn này, bạn có thể xác định các loại tài liệu và xử lý chúng phù hợp trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm cách nào để cài đặt Aspose.Words cho Java?

 Bạn có thể tải xuống Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/) và làm theo hướng dẫn cài đặt được cung cấp.

### Các định dạng tài liệu được hỗ trợ là gì?

Aspose.Words for Java hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm DOC, DOCX, RTF, HTML, v.v. Bạn có thể tham khảo tài liệu để có danh sách đầy đủ.

### Làm cách nào tôi có thể phát hiện các tài liệu được mã hóa bằng Aspose.Words cho Java?

 Bạn có thể dùng`FileFormatUtil.detectFileFormat()` phương pháp phát hiện tài liệu được mã hóa, như được trình bày trong hướng dẫn này.

### Có bất kỳ hạn chế nào khi làm việc với các định dạng tài liệu cũ hơn không?

Các định dạng tài liệu cũ hơn, chẳng hạn như MS Word 6 hoặc Word 95, có thể có những hạn chế về tính năng và khả năng tương thích với các ứng dụng hiện đại. Hãy xem xét nâng cấp hoặc chuyển đổi các tài liệu này khi cần thiết.

### Tôi có thể tự động phát hiện định dạng tài liệu trong ứng dụng Java của mình không?

Có, bạn có thể tự động phát hiện định dạng tài liệu bằng cách tích hợp mã được cung cấp vào ứng dụng Java của mình. Điều này cho phép bạn xử lý tài liệu dựa trên các định dạng được phát hiện của chúng.