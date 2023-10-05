---
title: Расширенные возможности сохранения HTML-документов с помощью Aspose.Words Java
linktitle: Сохранение HTML-документов с помощью
second_title: API обработки Java-документов Aspose.Words
description: В этом руководстве мы рассмотрели различные расширенные параметры сохранения HTML-документов с помощью Aspose.Words для Java. Эти параметры позволяют вам создавать высококачественный HTML.
type: docs
weight: 16
url: /ru/java/document-loading-and-saving/advance-html-documents-saving-options/
---

В этом уроке мы рассмотрим расширенные параметры сохранения HTML-документов, предоставляемые Aspose.Words для Java. Aspose.Words — это мощный Java API для работы с документами Word, предлагающий широкий спектр функций для манипулирования и преобразования документов.

## 1. Введение
Aspose.Words for Java позволяет программно работать с документами Word. В этом уроке мы сосредоточимся на расширенных параметрах сохранения HTML-документов, которые позволяют вам контролировать преобразование документов Word в HTML.

## 2. Экспорт информации о поездке туда и обратно.
`exportRoundtripInformation` Метод позволяет экспортировать документы Word в HTML, сохраняя при этом обратную информацию. Эта информация может быть полезна, если вы хотите преобразовать HTML обратно в формат Word без потери каких-либо деталей, относящихся к документу.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Экспортируйте шрифты в формате Base64.
 С`exportFontsAsBase64` метод, вы можете экспортировать шрифты, используемые в документе, как данные в кодировке Base64 в HTML. Это гарантирует, что представление HTML сохранит те же стили шрифта, что и исходный документ Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Экспорт ресурсов
`exportResources` Метод позволяет указать тип таблицы стилей CSS и экспортировать ресурсы шрифтов. Вы также можете установить папку ресурсов и псевдоним для ресурсов в HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Конвертируйте метафайлы в EMF или WMF.
`convertMetafilesToEmfOrWmf`Метод позволяет конвертировать метафайлы документа в формат EMF или WMF, обеспечивая совместимость и плавный рендеринг в HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 6. Конвертируйте метафайлы в SVG
 Использовать`convertMetafilesToSvg` метод преобразования метафайлов в формат SVG. Этот формат идеально подходит для отображения векторной графики в документах HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 7. Добавьте префикс имени класса CSS
 С`addCssClassNamePrefix` вы можете добавить префикс к именам классов CSS в экспортированном HTML. Это помогает предотвратить конфликты с существующими стилями.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Экспортируйте URL-адреса CID для ресурсов MHTML.
`exportCidUrlsForMhtmlResources` метод используется при сохранении документов в формате MHTML. Он позволяет экспортировать URL-адреса Content-ID для ресурсов.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 9. Разрешение названий шрифтов
`resolveFontNames` Метод помогает разрешать имена шрифтов при сохранении документов в формате HTML, обеспечивая единообразный рендеринг на разных платформах.

```java
@Test
public void resolveFontNames() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 10. Экспортировать поле формы ввода текста как текст.
`exportTextInputFormFieldAsText` Метод экспортирует поля формы в виде обычного текста в HTML, что делает их легко читаемыми и редактируемыми.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 11. Заключение
В этом руководстве мы рассмотрели расширенные возможности сохранения HTML-документов, предоставляемые Aspose.Words для Java. Эти параметры дают вам детальный контроль над процессом преобразования, позволяя создавать документы HTML, очень похожие на исходные документы Word.

## 12. Часто задаваемые вопросы
Вот некоторые часто задаваемые вопросы о работе с Aspose.Words for Java и опциях сохранения HTML-документов:

### Вопрос 1: Как преобразовать HTML обратно в формат Word с помощью Aspose.Words для Java?
 Чтобы преобразовать HTML обратно в формат Word, вы можете использовать API Aspose.Words.`load` метод для загрузки HTML-документа и последующего сохранения его в формате Word.

### Вопрос 2. Могу ли я настроить стили CSS при экспорте в HTML?
 Да, вы можете настраивать стили CSS, изменяя таблицы стилей, используемые в HTML, или используя`addCssClassNamePrefix` метод для добавления префикса к именам классов CSS.

### Вопрос 3. Есть ли способ оптимизировать вывод HTML для отображения в Интернете?
Да, вы можете оптимизировать вывод HTML для отображения в Интернете, настроив такие параметры, как экспорт шрифтов в формате Base64 и преобразование метафайлов в SVG.

### Вопрос 4. Существуют ли какие-либо ограничения при преобразовании сложных документов Word в HTML?
Хотя Aspose.Words for Java предоставляет мощные возможности преобразования, сложные документы Word со сложными макетами могут потребовать дополнительной постобработки для достижения желаемого вывода HTML.
