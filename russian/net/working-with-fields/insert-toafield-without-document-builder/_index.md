---
title: Вставить поле TOA без построителя документов
linktitle: Вставить поле TOA без построителя документов
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по вставке поля TOA без Document Builder с использованием Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-toafield-without-document-builder/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставка поля TOA» Aspose.Words для .NET. Внимательно выполняйте каждый шаг, чтобы получить желаемый результат.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и абзаца

Начнем с создания нового документа и инициализации абзаца.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Шаг 3: Вставка поля TA

Мы используем класс FieldTA, чтобы вставить поле TA в абзац.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Шаг 4: Добавление абзаца в тело документа

Добавляем абзац, содержащий поле TA, в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Шаг 5: Создание абзаца для поля TOA

Мы создаем новый абзац для поля TOA.

```csharp
para = new Paragraph(doc);
```

## Шаг 6: Вставка поля TOA

Мы используем класс FieldToa для вставки поля TOA в абзац.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Шаг 7: Добавление абзаца в тело документа

Мы добавляем абзац, содержащий поле TOA, в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Шаг 8: Обновите поле TOA

 Наконец, мы вызываем`Update()` способ обновления поля TOA.

```csharp
fieldToa.Update();
```

### Пример исходного кода для вставки поля TOA без Document Builder с Aspose.Words для .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Мы хотим вставить поля TA и TOA следующим образом:
// { TA \c 1 \l "Значение 0" }
// {ТОА \с 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```
