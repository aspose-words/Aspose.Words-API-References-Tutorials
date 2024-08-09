---
title: Impresión de documentos en Aspose.Words para Java
linktitle: Imprimir documentos
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a imprimir documentos utilizando Aspose.Words para Java. Guía paso a paso para una impresión perfecta en sus aplicaciones Java.
type: docs
weight: 10
url: /es/java/printing-documents/printing-documents/
---

Si buscas imprimir documentos usando Aspose.Words para Java, estás en el lugar correcto. En esta guía paso a paso, lo guiaremos a través del proceso de impresión de documentos con Aspose.Words para Java utilizando el código fuente proporcionado.

## Introducción

Imprimir documentos es una tarea común en muchas aplicaciones. Aspose.Words para Java proporciona una potente API para trabajar con documentos de Word, incluida la capacidad de imprimirlos. En este tutorial, lo guiaremos a través del proceso de impresión de un documento de Word paso a paso.

## Configurando su entorno

Antes de profundizar en el código, asegúrese de cumplir con los siguientes requisitos previos:

- Kit de desarrollo Java (JDK) instalado
- Biblioteca Aspose.Words para Java descargada y agregada a su proyecto

## Cargando el documento

 Para comenzar, deberá cargar el documento de Word que desea imprimir. Reemplazar`"Your Document Directory"` con la ruta a su documento y`"Your Output Directory"` con el directorio de salida deseado.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Crear un trabajo de impresión

A continuación, crearemos un trabajo de impresión para imprimir nuestro documento cargado. El siguiente fragmento de código inicializa un trabajo de impresión y establece la configuración de impresora deseada.

```java
// Crea un trabajo de impresión para imprimir nuestro documento.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inicialice un conjunto de atributos con el número de páginas del documento.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Pase la configuración de la impresora junto con los demás parámetros al documento de impresión.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Imprimir el documento

Ahora que hemos configurado nuestro trabajo de impresión, es hora de imprimir el documento. El siguiente fragmento de código asocia el documento con el trabajo de impresión e inicia el proceso de impresión.

```java
// Pase el documento a imprimir mediante el trabajo de impresión.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Código fuente completo
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Crea un trabajo de impresión para imprimir nuestro documento.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inicialice un conjunto de atributos con el número de páginas del documento.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Pase la configuración de la impresora junto con los demás parámetros al documento de impresión.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Pase el documento a imprimir mediante el trabajo de impresión.
pj.setPrintable(awPrintDoc);
pj.print();
```
Código fuente de MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <resumen>
    /// El constructor de la clase PrintDocument personalizada.
    // / </summary>
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
        // Los índices de inicio y fin de página tal como se define en el conjunto de atributos.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Calcule el índice de la página que se representará a continuación.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Si el índice de la página es mayor que el rango total de páginas, entonces no hay nada
        // más para renderizar.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Calcule el tamaño de cada marcador de posición en miniatura en puntos.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Calcula el número de la primera página que se imprimirá en esta hoja de papel.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Seleccione el número de la última página que se imprimirá en esta hoja de papel.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Recorra las páginas seleccionadas desde la página actual almacenada hasta la página calculada.
        // última página.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Calcule los índices de columnas y filas.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Defina la ubicación de la miniatura en coordenadas mundiales (puntos en este caso).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Calcule las posiciones iniciales izquierda y superior.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Renderice la página del documento al objeto Gráficos usando coordenadas calculadas
                // y tamaño del marcador de posición de miniatura.
                // El valor de retorno útil es la escala a la que se representó la página.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Dibuje los bordes de la página (la miniatura de la página podría ser más pequeña que la miniatura)
                // tamaño del marcador de posición).
                if (mPrintPageBorders) {
                    // Obtenga el tamaño real 100% de la página en puntos.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Dibuja el borde alrededor de la página escalada usando el factor de escala conocido.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Dibuja el borde alrededor del marcador de posición de la miniatura.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Si se produce algún error durante el renderizado, no haga nada.
                // Esto dibujará una página en blanco si hay algún error durante el renderizado.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Defina el número de columnas y filas en la hoja para el
        //Papel orientado al paisaje.
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
        // Cambie el ancho y el alto si el papel está en orientación vertical.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Conclusión

¡Felicidades! Ha impreso correctamente un documento de Word utilizando Aspose.Words para Java. Esta guía paso a paso le ayudará a integrar la impresión de documentos en sus aplicaciones Java sin problemas.

## Preguntas frecuentes

### P1: ¿Puedo imprimir páginas específicas de un documento usando Aspose.Words para Java?

 Sí, puede especificar el rango de páginas al imprimir un documento. En el ejemplo de código, usamos`attributes.add(new PageRanges(1, doc.getPageCount()))` para imprimir todas las páginas. Puede ajustar el rango de páginas según sea necesario.

### P2: ¿Aspose.Words para Java es adecuado para la impresión por lotes?

¡Absolutamente! Aspose.Words para Java es ideal para tareas de impresión por lotes. Puede recorrer una lista de documentos e imprimirlos uno por uno usando un código similar.

### P3: ¿Cómo puedo manejar errores o excepciones de impresión?

Debe gestionar cualquier posible excepción que pueda ocurrir durante el proceso de impresión. Consulte la documentación de Aspose.Words para Java para obtener información sobre el manejo de excepciones.

### P4: ¿Puedo personalizar aún más la configuración de impresión?

Sí, puede personalizar la configuración de impresión para satisfacer sus requisitos específicos. Explore la documentación de Aspose.Words para Java para obtener más información sobre las opciones de impresión disponibles.

### P5: ¿Dónde puedo obtener más ayuda y soporte para Aspose.Words para Java?

 Para obtener soporte y asistencia adicional, puede visitar el[Foro de Aspose.Words para Java](https://forum.aspose.com/).

---

Ahora que ha aprendido con éxito cómo imprimir documentos usando Aspose.Words para Java, puede comenzar a implementar esta funcionalidad en sus aplicaciones Java. ¡Feliz codificación!