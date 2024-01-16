---
title: 將 Docx 轉換為 Mhtml 並發送電子郵件
linktitle: 將 Docx 轉換為 Mhtml 並發送電子郵件
second_title: Aspose.Words 文件處理 API
description: 了解如何將 Word 文件從 Docx 轉換為 MHTML，並使用 Aspose.Words 和 Aspose.Email 將其作為電子郵件發送。分步教程。
type: docs
weight: 10
url: /zh-hant/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

在本逐步教學中，我們將指導您如何使用 Aspose.Words for .NET 將 Docx 格式的 Word 文件轉換為 MHTML，並使用 Aspose.Email 將其作為電子郵件發送。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET 和 Aspose.Email 程式庫。如果您還沒有這樣做，請從以下位置下載並安裝庫：[Aspose. 發布](https://releases.aspose.com/words/net/).

## 第 1 步：初始化文檔對象

首先，初始化`Document`對象，其中包含 Docx 格式的來源文件的路徑：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 步驟 2：將文件儲存為 MHTML 格式

接下來，將文檔儲存到`Stream`MHTML 格式的物件：

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## 第 3 步：倒帶流

由於 Aspose.Email 需要從頭開始讀取流，因此將流倒回到開頭：

```csharp
stream.Position = 0;
```

## 步驟 4：建立 Aspose.Email MIME 訊息

創建一個`MailMessage`使用流中的對象`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

您可以隨意自訂訊息屬性，例如寄件者、收件者和主題。

## 第 5 步：發送電子郵件

使用 Aspose.Email 的`SmtpClient`發送電子郵件：

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

確保您提供正確的 SMTP 伺服器主機位址。

就是這樣！您已成功將 Docx 格式的 Word 文件轉換為 MHTML，並使用 Aspose.Words for .NET 和 Aspose.Email 將其作為電子郵件發送。

### Docx 轉 Mhtml 並使用 Aspose.Words for .NET 發送電子郵件的範例原始程式碼

```csharp

	//文檔 doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//將流倒回到開頭，以便 Aspose.Email 可以讀取它。
	stream.Position = 0;

	//從串流建立 Aspose.Email MIME 電子郵件。
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	//使用 Aspose.Email 發送訊息。
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

請隨意在您自己的專案中使用此程式碼，並根據您的特定要求進行修改。

### 常見問題解答

#### 如何將 DOCX 檔案轉換為 MHTML？

若要將 DOCX 檔案轉換為 MHTML，您可以使用提供此功能的軟體工具或程式庫。 Aspose.Words for .NET 是這種轉換的可靠選擇。您可以使用庫 API 載入 DOCX 檔案並將其儲存為 MHTML 格式。

#### 如何發送帶有 MHTML 文件附件的電子郵件？

若要傳送帶有 MHTML 檔案作為附件的電子郵件，您可以使用特定於電子郵件傳送的程式庫或工具，例如 .NET 中的 System.Net.Mail。您必須建立電子郵件，指定收件者、主題和內容，然後將 MHTML 檔案作為附件新增至郵件中，然後再傳送。

#### 電子郵件轉換和發送過程有哪些限制？

電子郵件轉換和發送過程的限制取決於您使用的特定工具。某些工具可能具有與檔案大小、安全設定或支援的電子郵件協定相關的限制。選擇適合您需求的工具並在實施時考慮這些限制非常重要。

#### Aspose 是 DOCX 到 MHTML 轉換和電子郵件發送的可靠工具嗎？

是的，Aspose.Words for .NET 是 DOCX 到 MHTML 轉換和電子郵件發送的可靠工具。它因其性能和品質而被開發人員和專業人士廣泛使用。該工具提供全面的文件、高級功能和專門的技術支持，使其成為執行這些任務的建議選擇。