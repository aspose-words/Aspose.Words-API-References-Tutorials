---
title: Печать документов в Aspose.Words для Java
linktitle: Печать документов
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как печатать документы с помощью Aspose.Words для Java. Пошаговое руководство по бесперебойной печати в ваших Java-приложениях.
type: docs
weight: 10
url: /ru/java/printing-documents/printing-documents/
---

Если вы хотите распечатать документы с помощью Aspose.Words for Java, вы попали по адресу. В этом пошаговом руководстве мы покажем вам процесс печати документов с помощью Aspose.Words for Java с использованием предоставленного исходного кода.

## Введение

Печать документов — обычная задача во многих приложениях. Aspose.Words for Java предоставляет мощный API для работы с документами Word, включая возможность их печати. В этом уроке мы шаг за шагом проведем вас через процесс печати документа Word.

## Настройка вашей среды

Прежде чем мы углубимся в код, убедитесь, что у вас есть следующие предварительные условия:

- Установлен пакет разработки Java (JDK).
- Библиотека Aspose.Words for Java загружена и добавлена в ваш проект.

## Загрузка документа

 Чтобы начать, вам нужно загрузить документ Word, который вы хотите распечатать. Заменять`"Your Document Directory"` с путем к вашему документу и`"Your Output Directory"` с желаемым выходным каталогом.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Создание задания на печать

Далее мы создадим задание на печать для печати загруженного документа. Приведенный ниже фрагмент кода инициализирует задание печати и устанавливает нужные настройки принтера.

```java
// Создайте задание на печать для печати нашего документа.
PrinterJob pj = PrinterJob.getPrinterJob();
//Инициализируйте набор атрибутов количеством страниц в документе.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Передайте настройки принтера вместе с другими параметрами в документ для печати.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Печать документа

Теперь, когда мы настроили задание на печать, пришло время распечатать документ. Следующий фрагмент кода связывает документ с заданием на печать и запускает процесс печати.

```java
// Передайте документ на печать, используя задание печати.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Полный исходный код
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Создайте задание на печать для печати нашего документа.
PrinterJob pj = PrinterJob.getPrinterJob();
//Инициализируйте набор атрибутов количеством страниц в документе.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Передайте настройки принтера вместе с другими параметрами в документ для печати.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Передайте документ на печать, используя задание печати.
pj.setPrintable(awPrintDoc);
pj.print();
```
Исходный код MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <сводка>
    /// Конструктор пользовательского класса PrintDocument.
    // / </сводка>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // Индексы начала и конца страницы, определенные в наборе атрибутов.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Рассчитайте индекс страницы, которая будет отображаться следующей.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Если индекс страницы превышает общий диапазон страниц, то ничего не происходит.
        // больше рендерить.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Рассчитайте размер каждого заполнителя миниатюры в пунктах.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Вычислите количество первой страницы, которая будет напечатана на этом листе бумаги.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Выберите номер последней страницы, которая будет напечатана на этом листе бумаги.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Перебирать выбранные страницы от сохраненной текущей страницы до расчетной.
        // последняя страница.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Вычислите индексы столбца и строки.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Определите местоположение миниатюры в мировых координатах (в данном случае точек).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Рассчитайте левую и верхнюю стартовые позиции.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Отобразите страницу документа в объекте Graphics, используя вычисленные координаты.
                // и размер заполнителя миниатюры.
                // Полезное возвращаемое значение — это масштаб, в котором была отображена страница.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Нарисуйте границы страницы (миниатюра страницы может быть меньше миниатюры
                // размер заполнителя).
                if (mPrintPageBorders) {
                    // Получите реальный 100% размер страницы в пунктах.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Нарисуйте рамку вокруг масштабированной страницы, используя известный масштабный коэффициент.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Нарисуйте рамку вокруг заполнителя миниатюры.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Если во время рендеринга возникают какие-либо ошибки, ничего не делайте.
                // При этом будет нарисована пустая страница, если во время рендеринга возникнут какие-либо ошибки.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Определите количество столбцов и строк на листе для
        //Бумага альбомного типа.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // Поменяйте местами ширину и высоту, если бумага имеет книжную ориентацию.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Заключение

Поздравляем! Вы успешно распечатали документ Word с помощью Aspose.Words для Java. Это пошаговое руководство поможет вам легко интегрировать печать документов в ваши приложения Java.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я распечатать определенные страницы документа с помощью Aspose.Words для Java?

 Да, вы можете указать диапазон страниц при печати документа. В примере кода мы использовали`attributes.add(new PageRanges(1, doc.getPageCount()))` распечатать все страницы. При необходимости вы можете настроить диапазон страниц.

### Вопрос 2. Подходит ли Aspose.Words для Java для пакетной печати?

Абсолютно! Aspose.Words for Java хорошо подходит для задач пакетной печати. Вы можете перебирать список документов и распечатывать их один за другим, используя аналогичный код.

### Вопрос 3. Как справиться с ошибками печати или исключениями?

Вам следует обрабатывать любые потенциальные исключения, которые могут возникнуть в процессе печати. Обратитесь к документации Aspose.Words for Java для получения информации об обработке исключений.

### Вопрос 4: Могу ли я дополнительно настроить параметры печати?

Да, вы можете настроить параметры печати в соответствии с вашими конкретными требованиями. Изучите документацию Aspose.Words for Java, чтобы узнать больше о доступных параметрах печати.

### Вопрос 5: Где я могу получить дополнительную помощь и поддержку по Aspose.Words для Java?

 Для получения дополнительной поддержки и помощи вы можете посетить[Форум Aspose.Words для Java](https://forum.aspose.com/).

---

Теперь, когда вы успешно научились печатать документы с помощью Aspose.Words for Java, вы можете приступить к реализации этой функции в своих приложениях Java. Приятного кодирования!