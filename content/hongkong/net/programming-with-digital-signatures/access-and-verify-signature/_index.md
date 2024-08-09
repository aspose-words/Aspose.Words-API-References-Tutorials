---
title: 存取並驗證 Word 文件中的簽名
linktitle: 存取並驗證 Word 文件中的簽名
second_title: Aspose.Words 文件處理 API
description: 透過這份全面的逐步指南，使用 Aspose.Words for .NET 存取和驗證 Word 文件中的數位簽章。輕鬆確保文件真實性。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/access-and-verify-signature/
---
## 介紹

嘿，科技愛好者們！您是否曾經遇到過需要存取和驗證 Word 文件中的數位簽章但不知道從哪裡開始的情況？嗯，你很幸運！今天，我們將深入探討 Aspose.Words for .NET 的奇妙世界，這是一個功能強大的函式庫，讓處理 Word 文件變得輕而易舉。我們將逐步引導您完成整個過程，因此在本指南結束時，您將成為驗證 Word 文件中的數位簽章的專家。讓我們開始吧！

## 先決條件

在我們深入了解具體細節之前，您需要先做好以下幾件事：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。您將在此處編寫和運行程式碼。
2.  Aspose.Words for .NET：您需要安裝 Aspose.Words for .NET。你可以下載它[這裡](https://releases.aspose.com/words/net/)。不要忘記獲得免費試用[這裡](https://releases.aspose.com/)如果你還沒有！
3. 經過數位簽署的 Word 文件：擁有已經過數位簽署的 Word 文件。這是您將用來驗證簽名的文件。

## 導入命名空間

首先，讓我們導入必要的名稱空間。這些命名空間將允許您在專案中使用 Aspose.Words 功能。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.DigitalSignatures;
```

好吧，讓我們將其分解為可管理的步驟。每個步驟將指導您完成流程的特定部分。準備好？我們走吧！

## 第 1 步：設定您的項目

在驗證數位簽章之前，您需要在 Visual Studio 中設定專案。方法如下：

### 建立一個新項目

1. 打開視覺工作室。
2. 點擊建立新項目。
3. 根據您的偏好，選擇控制台應用程式 (.NET Core) 或控制台應用程式 (.NET Framework)。
4. 按一下“下一步”，為您的專案命名，然後按一下“建立”。

### 安裝 Aspose.Words for .NET

1. 在解決方案資源管理器中，以滑鼠右鍵按一下專案名稱並選擇管理 NuGet 套件。
2. 在 NuGet 套件管理器中，搜尋 Aspose.Words。
3. 點擊安裝將其添加到您的專案中。

## 第 2 步：載入經過數位簽署的 Word 文檔

現在您的專案已設定完畢，讓我們載入經過數位簽署的 Word 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。此程式碼片段初始化一個新的`Document`物件並載入您簽名的 Word 文件。

## 第 3 步：存取數位簽名

載入文件後，就可以存取數位簽章了。

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine("* Signature Found *");
    Console.WriteLine("Is valid: " + signature.IsValid);
    Console.WriteLine("Reason for signing: " + signature.Comments); 
    Console.WriteLine("Time of signing: " + signature.SignTime);
    Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
    Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
    Console.WriteLine();
}
```

此程式碼循環遍歷文件中的每個數位簽名，並列印出有關簽名的各種詳細資訊。讓我們分解一下每個部分的作用：

1. 找到簽名：表示已找到簽名。
2. 有效：檢查簽名是否有效。
3. 簽名原因：顯示簽名原因（如果有）。
4. 簽名時間：顯示文件簽名的時間戳記。
5. 主題名稱：從憑證中檢索主題名稱。
6. 頒發者名稱：從憑證中檢索頒發者名稱。

## 第 4 步：運行您的程式碼

一切設定完畢後，就可以運行程式碼並查看結果了。


1. 按 F5 或按一下 Visual Studio 中的「開始」按鈕來執行程式。
2. 如果您的文件經過數位簽名，您將在控制台中看到列印的簽名詳細資訊。

## 第 5 步：處理潛在錯誤

處理可能發生的任何潛在錯誤始終是個好主意。讓我們在程式碼中加入一些基本的錯誤處理。

```csharp
try
{
    //文檔目錄的路徑。
    string dataDir = "YOUR DOCUMENT DIRECTORY";
    Document doc = new Document(dataDir + "Digitally signed.docx");

    foreach (DigitalSignature signature in doc.DigitalSignatures)
    {
        Console.WriteLine("* Signature Found *");
        Console.WriteLine("Is valid: " + signature.IsValid);
        Console.WriteLine("Reason for signing: " + signature.Comments); 
        Console.WriteLine("Time of signing: " + signature.SignTime);
        Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
        Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
        Console.WriteLine();
    }
}
catch (Exception ex)
{
    Console.WriteLine("An error occurred: " + ex.Message);
}
```

這將捕獲可能發生的任何異常並列印錯誤訊息。

## 結論

現在你就得到它了！您已使用 Aspose.Words for .NET 成功存取並驗證了 Word 文件中的數位簽章。它並不像看起來那麼令人畏懼，對吧？透過這些步驟，您可以自信地處理 Word 文件中的數位簽名，確保其真實性和完整性。快樂編碼！

## 常見問題解答

### 我可以使用 Aspose.Words for .NET 將數位簽章新增至 Word 文件嗎？

是的，您可以使用 Aspose.Words for .NET 在 Word 文件中新增數位簽章。該庫提供了用於添加和驗證數位簽章的全面功能。

### Aspose.Words for .NET 可以驗證哪些類型的數位簽章？

Aspose.Words for .NET 可以驗證使用 X.509 憑證的 DOCX 檔案中的數位簽章。

### Aspose.Words for .NET 是否與所有版本的 Microsoft Word 相容？

Aspose.Words for .NET 支援所有版本的 Microsoft Word 文檔，包括 DOC、DOCX、RTF 等。

### 如何取得 Aspose.Words for .NET 的臨時授權？

您可以從以下位置取得 Aspose.Words for .NET 的臨時授權：[這裡](https://purchase.aspose.com/temporary-license/)。這使您可以不受任何限制地嘗試該庫的全部功能。

### 在哪裡可以找到有關 Aspose.Words for .NET 的更多文件？

您可以找到 Aspose.Words for .NET 的詳細文檔[這裡](https://reference.aspose.com/words/net/).