---
title: Вставить дополнительное поле без построителя документов
linktitle: Вставить дополнительное поле без построителя документов
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить расширенное поле в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Расширенная вставка полей без DocumentBuilder» Aspose.Words для .NET. Обязательно внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание документа и абзаца

Мы начинаем с создания нового документа и получения первого абзаца.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Шаг 3. Вставка расширенного поля

 Мы используем`AppendField()` метод для вставки расширенного поля в абзац.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Затем мы настраиваем различные свойства расширенного поля, указывая нужные значения.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Наконец, мы вызываем`Update()` метод обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки расширенного поля без DocumentBuilder с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Вставьте расширенное поле.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

В этом примере мы создали новый документ, вставили расширенное поле без использования DocumentBuilder, настроили различные свойства поля и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить расширенное поле без DocumentBuilder» в Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Что такое расширенное поле в Aspose.Words?

О: Расширенное поле в Aspose.Words — это особый тип поля, который позволяет вам выполнять вычисления, включать условия и выполнять сложные операции в документе Word. Он предлагает большую гибкость для создания динамических и настраиваемых полей.

#### Вопрос: Как вставить расширенное поле в документ Word без использования Document Builder в Aspose.Words?

О: Чтобы вставить расширенное поле в документ Word без использования Document Builder в Aspose.Words, вы можете выполнить следующие действия:

1. Импортируйте класс документа и поля из пространства имен Aspose.Words.Fields.
2. Создайте экземпляр Document, загрузив существующий документ.
3. Используйте метод InsertField, чтобы вставить расширенное поле, указав код расширенного поля.
4. Сохраните документ.

#### Вопрос: Как получить результат расширенного поля в документе Word?

О: Чтобы получить результат расширенного поля в документе Word, вы можете использовать свойство Result, доступное в классе Field. Это свойство возвращает вычисленный результат поля.

#### Вопрос: Могу ли я изменить формулу расширенного поля после вставки его в документ Word?

О: Да, вы можете редактировать формулу расширенного поля после вставки его в документ Word. Это можно сделать, обратившись к свойству FieldCode класса Field и обновив формулу, изменив текст формулы.