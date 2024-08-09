---
title: 管理數位簽章和真實性
linktitle: 管理數位簽章和真實性
second_title: Aspose.Words Python 文件管理 API
description: 了解如何使用 Aspose.Words for Python 管理數位簽章並確保文件真實性。帶有原始程式碼的分步指南。
type: docs
weight: 17
url: /zh-hant/python-net/document-combining-and-comparison/manage-digital-signatures/
---

## 數位簽名簡介

數位簽名相當於手寫簽名的電子版本。它們提供了一種驗證電子文件的真實性、完整性和來源的方法。對文件進行數位簽章時，會根據文件的內容產生加密哈希。然後使用簽署者的私鑰對該哈希值進行加密，從而創建數位簽章。任何擁有相應公鑰的人都可以驗證簽名並確定文件的真實性。

## 為 Python 設定 Aspose.Words

若要開始使用 Aspose.Words for Python 管理數位簽名，請依照下列步驟操作：

1. 安裝 Aspose.Words：您可以透過以下命令使用 pip 安裝 Aspose.Words for Python：
   
   ```python
   pip install aspose-words
   ```

2. 導入所需的模組：在 Python 腳本中導入必要的模組：
   
   ```python
   import asposewords
   ```

## 載入和存取文檔

在新增或驗證數位簽章之前，您需要使用Aspose.Words載入文件：

```python
document = asposewords.Document("document.docx")
```

## 在文件中添加數位簽名

要為文件添加數位簽名，您需要數位證書：

```python
certificate = asposewords.Certificate("certificate.pfx", "password")
```

現在，簽署文件：

```python
digital_signature = asposewords.DigitalSignature()
digital_signature.certificate = certificate
document.digital_signatures.add(digital_signature)
document.save("signed_document.docx")
```

## 驗證數位簽名

使用 Aspose.Words 驗證簽名文件的真實性：

```python
for signature in document.digital_signatures:
    if signature.is_valid:
        print("Signature is valid.")
    else:
        print("Signature is invalid.")
```

## 刪除數位簽名

若要從文件中刪除數位簽章：

```python
document.digital_signatures.clear()
document.save("unsigned_document.docx")
```

## 確保文件真實性

數位簽章透過確認文件的來源和完整性來確保文件的真實性。它們可以防止篡改和未經授權的修改。

## 自訂數位簽名外觀

您可以自訂數位簽章的外觀：

```python
digital_signature.options.comments = "Approved by John Doe"
digital_signature.options.sign_date_time = datetime.now()
```

## 結論

在當今的數位環境中，管理數位簽章和確保文件真實性至關重要。 Aspose.Words for Python 簡化了新增、驗證和自訂數位簽章的過程，使開發人員能夠增強文件的安全性和可信度。

## 常見問題解答

### 數位簽名如何運作？

數位簽章使用加密技術根據文件內容產生唯一的雜湊值，並使用簽署者的私鑰進行加密。

### 數位簽章的文檔可以被竄改嗎？

不可以，篡改數位簽章的文件會使簽章無效，這表示可能存在未經授權的變更。

### 可以將多個簽名新增到單一文件嗎？

是的，您可以將多個數位簽章新增至單一文件中，每個簽章都來自不同的簽章者。

### 相容於哪些類型的憑證？

Aspose.Words支援X.509證書，包括通常用於數位簽章的PFX檔。

### 數位簽章具有法律效力嗎？

是的，數位簽名在許多國家/地區具有法律效力，並且通常被認為等同於手寫簽名。