---
title: Вставить TCField
linktitle: Вставить TCField
second_title: API обработки документов Aspose.Words
description: Из этого пошагового руководства вы узнаете, как вставлять TCFields и управлять ими в документах Word с помощью C# и Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-tcfield/
---

В этом примере мы проведем вас через процесс использования функции Insert TCField в Aspose.Words для .NET. TCField представляет запись оглавления в документе Word. Мы предоставим пошаговое объяснение исходного кода C# вместе с ожидаемым результатом в формате уценки. Давайте начнем!

## Шаг 1: Инициализация документа и построителя документов

Для начала нам нужно инициализировать документ и конструктор документов. Конструктор документов — это мощный инструмент, предоставляемый Aspose.Words для .NET, который позволяет нам программно создавать документы Word и управлять ими. Вот как это сделать:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Вставка TCField

 Далее мы вставим TCField в документ, используя`InsertField` метод. TCField представляет запись оглавления с указанным текстом записи. Вот пример:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

Приведенный выше код вставит в документ TCField с текстом записи «Entry Text».

## Шаг 3: Сохранение документа

 После вставки TCField мы можем сохранить документ в определенном месте, используя`Save` метод. Обязательно укажите желаемый путь и имя файла для выходного документа. Вот пример:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Приведенный выше код сохранит документ с TCField в указанный каталог.

## Выходные форматы уценки

Когда код выполнен успешно, выходной документ будет содержать запись оглавления с указанным текстом записи. TCField представлен как поле в документе Word, и результирующий формат уценки будет зависеть от того, как обрабатывается документ.

Обратите внимание, что выходной документ находится не в формате уценки, а в формате Word. Однако, когда вы конвертируете документ Word в уценку с помощью соответствующих инструментов или библиотек, TCField будет обрабатываться соответствующим образом.

### Пример исходного кода для вставки TCField с использованием Aspose.Words для .NET

Вот полный пример исходного кода для вставки TCField с помощью Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("TC \"Entry Text\" \\f t");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Не стесняйтесь изменять код в соответствии с вашими требованиями и исследовать другие функции, предоставляемые Aspose.Words для .NET.

Вот и все! Вы успешно научились вставлять TCField с помощью Aspose.Words для .NET.

