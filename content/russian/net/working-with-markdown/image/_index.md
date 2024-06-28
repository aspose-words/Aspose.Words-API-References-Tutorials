---
title: Изображение
linktitle: Изображение
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять и настраивать изображения с помощью Aspose.Words for .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/image/
---

В этом примере мы объясним, как использовать функцию изображения с Aspose.Words для .NET. Картинки позволяют вставлять в документ иллюстрации и графику.

## Шаг 1. Использование генератора документов

Сначала мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Вставка изображения

 Мы можем вставить изображение, используя`Shape` class и указывая тип изображения, здесь`ShapeType.Image` . Мы также установили тип переноса изображения на`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Шаг 3. Настройка изображения

 Настраиваем изображение, указав его полный путь, например`"/attachment/1456/pic001.png"`и добавьте заголовок к изображению.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Пример исходного кода для изображений с помощью Aspose.Words для .NET

```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// Вставить изображение.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Поздравляем! Теперь вы узнали, как использовать функцию изображений в Aspose.Words для .NET.


### Часто задаваемые вопросы

#### Вопрос: Как вставить изображение из локального файла в Aspose.Words?

 О: Чтобы вставить изображение из локального файла в Aspose.Words, вы можете использовать команду`Shape` класс и`InsertImage` метод.

#### Вопрос: Могу ли я вставить изображение по URL-адресу в Aspose.Words?

 О: Да, вы можете вставить изображение по URL-адресу в Aspose.Words. Вы можете использовать тот же`InsertImage`и укажите URL-адрес изображения вместо пути к локальному файлу.

#### Вопрос: Как изменить размер изображения в Aspose.Words?

 О: Чтобы изменить размер изображения в Aspose.Words, вы можете использовать`Width` и`Height` свойства`Shape` Объект Object.

#### Вопрос: Могу ли я применять фильтры к изображениям в Aspose.Words?

 О: Да, вы можете применять фильтры к изображениям в Aspose.Words. Например, вы можете применить к изображению фильтр размытия, используя`ApplyGaussianBlur` метод`Shape` Объект Object.

#### Вопрос: Как заменить одно изображение другим в Aspose.Words?

 О: Чтобы заменить одно изображение другим в Aspose.Words, вы можете использовать команду`Replace` метод`Shape` класс. Этот метод принимает в качестве параметра`Shape` объект изображения, подлежащего замене, и`Shape` объект нового изображения.