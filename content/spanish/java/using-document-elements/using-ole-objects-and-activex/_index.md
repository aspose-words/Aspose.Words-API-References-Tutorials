---
title: Uso de objetos OLE y controles ActiveX en Aspose.Words para Java
linktitle: Uso de objetos OLE y controles ActiveX
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a utilizar objetos OLE y controles ActiveX en Aspose.Words para Java. Cree documentos interactivos con facilidad. ¡Empieza ahora!
type: docs
weight: 21
url: /es/java/using-document-elements/using-ole-objects-and-activex/
---
En este tutorial, exploraremos cómo trabajar con objetos OLE (vinculación e incrustación de objetos) y controles ActiveX en Aspose.Words para Java. Los objetos OLE y los controles ActiveX son herramientas poderosas que le permiten mejorar sus documentos incrustando o vinculando contenido externo, como hojas de cálculo, archivos multimedia o controles interactivos. Siga mientras profundizamos en los ejemplos de código y aprenda a utilizar estas funciones de forma eficaz.

### Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Words para Java: asegúrese de tener la biblioteca Aspose.Words instalada en su proyecto Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/java/).

2. Entorno de desarrollo Java: debe tener un entorno de desarrollo Java funcional configurado en su sistema.

### Insertar un objeto OLE

Comencemos insertando un objeto OLE en un documento de Word. Crearemos un documento de Word simple y luego insertaremos un objeto OLE que represente una página web.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", verdadero, verdadero, nulo);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

En este código, creamos un nuevo documento e insertamos un objeto OLE que muestra el sitio web de Aspose. Puede reemplazar la URL con el contenido deseado.

### Insertar un objeto OLE con OlePackage

A continuación, exploremos cómo insertar un objeto OLE usando un OlePackage. Esto le permite incrustar archivos externos como objetos OLE en su documento.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

En este ejemplo, insertamos un objeto OLE usando un OlePackage, lo que le permite incluir archivos externos como objetos incrustados.

### Insertar un objeto OLE como icono

Ahora veamos cómo insertar un objeto OLE como icono. Esto resulta útil cuando desea mostrar un icono que representa un archivo incrustado.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

En este código, insertamos un objeto OLE como icono, proporcionando una representación más atractiva visualmente del contenido incrustado.

### Lectura de propiedades de control ActiveX

Ahora, centrémonos en los controles ActiveX. Aprenderemos cómo leer las propiedades de los controles ActiveX dentro de un documento de Word.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

En este código, recorremos las formas en un documento de Word, identificamos controles ActiveX y recuperamos sus propiedades.

### Conclusión

¡Felicidades! Ha aprendido a trabajar con objetos OLE y controles ActiveX en Aspose.Words para Java. Estas características abren un mundo de posibilidades para crear documentos dinámicos e interactivos.

### Preguntas frecuentes

### ¿Cuál es el propósito de los objetos OLE en un documento de Word? 
   - Los objetos OLE le permiten incrustar o vincular contenido externo, como archivos o páginas web, dentro de un documento de Word.

### ¿Puedo personalizar la apariencia de los objetos OLE en mi documento? 
   - Sí, puede personalizar la apariencia de los objetos OLE, incluida la configuración de iconos y nombres de archivos.

### ¿Qué son los controles ActiveX y cómo pueden mejorar mis documentos? 
   - Los controles ActiveX son elementos interactivos que pueden agregar funcionalidad a sus documentos de Word, como controles de formulario o reproductores multimedia.

### ¿Aspose.Words para Java es adecuado para la automatización de documentos a nivel empresarial? 
   - Sí, Aspose.Words para Java es una poderosa biblioteca para automatizar la generación y manipulación de documentos en aplicaciones Java.

### ¿Dónde puedo obtener acceso a Aspose.Words para Java? 
   -  Puede descargar Aspose.Words para Java desde[aquí](https://releases.aspose.com/words/java/).

¡Comience hoy con Aspose.Words para Java y libere todo el potencial de la automatización y personalización de documentos!
