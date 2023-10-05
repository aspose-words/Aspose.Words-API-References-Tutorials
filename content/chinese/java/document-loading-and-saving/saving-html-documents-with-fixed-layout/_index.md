---
title: 在 Aspose.Words for Java 中保存具有固定布局的 HTML 文档
linktitle: 以固定布局保存 HTML 文档
second_title: Aspose.Words Java 文档处理 API
description: 了解如何在 Aspose.Words for Java 中保存具有固定布局的 HTML 文档。请按照我们的分步指南进行无缝文档格式设置。
type: docs
weight: 15
url: /zh/java/document-loading-and-saving/saving-html-documents-with-fixed-layout/
---

## 在 Aspose.Words for Java 中保存具有固定布局的 HTML 文档简介

在本综合指南中，我们将引导您完成使用 Aspose.Words for Java 保存具有固定布局的 HTML 文档的过程。通过分步说明和代码示例，您将学习如何无缝地实现这一目标。那么，让我们开始吧！

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

- Java开发环境搭建。
- 安装并配置了 Aspose.Words for Java 库。

## 第 1 步：加载文档

首先，我们需要加载要以 HTML 格式保存的文档。您可以这样做：

```java
Document doc = new Document("Your Directory Path" + "YourDocument.docx");
```

代替`"YourDocument.docx"`以及您的 Word 文档的路径。

## 步骤 2：配置 HTML 固定保存选项

要以固定布局保存文档，我们需要配置`HtmlFixedSaveOptions`班级。我们将设置`useTargetMachineFonts`财产给`true`确保 HTML 输出中使用目标计算机的字体：

```java
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
saveOptions.setUseTargetMachineFonts(true);
```

## 步骤 3：将文档另存为 HTML

现在，让我们使用之前配置的选项将文档保存为具有固定布局的 HTML：

```java
doc.save("Your Directory Path" + "FixedLayoutDocument.html", saveOptions);
```

代替`"FixedLayoutDocument.html"`以及您的 HTML 文件所需的名称。

## 在 Aspose.Words for Java 中保存具有固定布局的 HTML 文档的完整源代码

```java
        Document doc = new Document("Your Directory Path" + "Bullet points with alternative font.docx");
        HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
        {
            saveOptions.setUseTargetMachineFonts(true);
        }
        doc.save("Your Directory Path" + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
    }
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for Java 以固定布局保存 HTML 文档。通过执行这些简单的步骤，您可以确保文档在不同平台上保持一致的视觉结构。

## 常见问题解答

### 如何在我的项目中设置 Aspose.Words for Java？

设置 Aspose.Words for Java 非常简单。您可以从以下位置下载该库[这里](https://releases.aspose.com/words/java/)并按照文档中提供的安装说明进行操作[这里](https://reference.aspose.com/words/java/).

### 使用 Aspose.Words for Java 有任何许可要求吗？

是的，Aspose.Words for Java 需要有效的许可证才能在生产环境中使用。您可以从 Aspose 网站获取许可证。更多详细信息可以在文档中找到。

### 我可以进一步自定义 HTML 输出吗？

当然！ Aspose.Words for Java 提供了多种自定义 HTML 输出的选项，以满足您的特定要求。您可以浏览文档以获取有关自定义选项的详细信息。

### Aspose.Words for Java 是否与不同的 Java 版本兼容？

是的，Aspose.Words for Java 与各种版本的 Java 兼容。确保您使用与您的 Java 开发环境相匹配的 Aspose.Words for Java 兼容版本。