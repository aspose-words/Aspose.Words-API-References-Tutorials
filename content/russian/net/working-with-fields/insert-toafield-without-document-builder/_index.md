---
title: Вставить поле TOA без построителя документов
linktitle: Вставить поле TOA без построителя документов
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по вставке поля TOA без Document Builder с использованием Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-toafield-without-document-builder/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставка поля TOA» Aspose.Words для .NET. Внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание документа и абзаца

Начнем с создания нового документа и инициализации абзаца.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Шаг 3. Вставка поля ТА

Мы используем класс FieldTA для вставки поля TA в абзац.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Шаг 4. Добавление абзаца в тело документа.

Добавляем абзац, содержащий поле TA, в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Шаг 5. Создание абзаца для поля TOA.

Мы создаем новый абзац для поля TOA.

```csharp
para = new Paragraph(doc);
```

## Шаг 6. Вставка поля TOA

Мы используем класс FieldToa для вставки поля TOA в абзац.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Шаг 7. Добавление абзаца в тело документа.

Добавляем абзац, содержащий поле TOA, в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Шаг 8. Обновите поле TOA.

 Наконец, мы вызываем`Update()` метод обновления поля TOA.

```csharp
fieldToa.Update();
```

### Пример исходного кода для вставки поля TOA без Document Builder с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Мы хотим вставить поля TA и TOA следующим образом:
// { TA \c 1 \l "Значение 0" }
// { ТОА \c 1 }

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

### Часто задаваемые вопросы

#### Вопрос: Как настроить внешний вид поля TOA, вставленного в документ Word, с помощью Aspose.Words for .NET?

О: Вы можете настроить внешний вид вставленного поля TOA, используя свойства поля TOA.`FieldTOA` объект для указания параметров форматирования.

#### Вопрос: Могу ли я добавить несколько полей TOA в один документ Word, используя Aspose.Words для .NET?

О: Да, вы можете добавить несколько полей TOA в один документ Word, используя Aspose.Words для .NET. Просто повторите шаги вставки для каждого поля.

#### Вопрос: Как я могу проверить, было ли поле TOA успешно вставлено в документ Word с помощью Aspose.Words for .NET?

О: Чтобы проверить, было ли поле TOA успешно вставлено, вы можете просмотреть содержимое документа и выполнить поиск экземпляров поля TOA.

#### Вопрос: Влияет ли вставка поля TOA без использования DocumentBuilder на форматирование документов Word с помощью Aspose.Words для .NET?

О: Вставка поля TOA без использования DocumentBuilder не влияет напрямую на форматирование документа Word. Однако параметры форматирования поля TOA могут повлиять на общее форматирование документа.