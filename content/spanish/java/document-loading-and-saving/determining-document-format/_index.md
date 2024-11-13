---
title: Cómo determinar el formato de un documento en Aspose.Words para Java
linktitle: Determinación del formato del documento
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a detectar formatos de documentos en Java con Aspose.Words. Identifique DOC, DOCX y más. Organice archivos de manera eficiente.
type: docs
weight: 25
url: /es/java/document-loading-and-saving/determining-document-format/
---

## Introducción a la determinación del formato de un documento en Aspose.Words para Java

Al trabajar con el procesamiento de documentos en Java, es fundamental determinar el formato de los archivos con los que se está trabajando. Aspose.Words para Java ofrece funciones potentes para identificar formatos de documentos y lo guiaremos a través del proceso.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- [Aspose.Words para Java](https://releases.aspose.com/words/java/)
- Kit de desarrollo de Java (JDK) instalado en su sistema
- Conocimientos básicos de programación Java

## Paso 1: Configuración del directorio

En primer lugar, debemos configurar los directorios necesarios para organizar nuestros archivos de forma eficaz. Crearemos directorios para distintos tipos de documentos.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Crea los directorios si aún no existen.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Hemos creado directorios para tipos de documentos compatibles, desconocidos, cifrados y anteriores a 1997.

## Paso 2: Detectar el formato del documento

Ahora, detectemos el formato de los documentos en nuestros directorios. Para ello, utilizaremos Aspose.Words para Java.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Mostrar el tipo de documento
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Agregue casos para otros formatos de documentos según sea necesario
    }

    // Manejar documentos encriptados
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Manejar otros tipos de documentos
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

En este fragmento de código, iteramos a través de los archivos, detectamos sus formatos y los organizamos en los directorios respectivos.

## Código fuente completo para determinar el formato de un documento en Aspose.Words para Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Crea los directorios si aún no existen.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Mostrar el tipo de documento
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Conclusión

La determinación de los formatos de documentos en Aspose.Words para Java es esencial para un procesamiento eficiente de los documentos. Con los pasos que se describen en esta guía, puede identificar los tipos de documentos y manejarlos en consecuencia en sus aplicaciones Java.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Words para Java?

 Puede descargar Aspose.Words para Java desde[aquí](https://releases.aspose.com/words/java/) siga las instrucciones de instalación proporcionadas.

### ¿Cuáles son los formatos de documentos admitidos?

Aspose.Words para Java admite varios formatos de documentos, incluidos DOC, DOCX, RTF, HTML y más. Puede consultar la documentación para obtener una lista completa.

### ¿Cómo puedo detectar documentos cifrados usando Aspose.Words para Java?

 Puedes utilizar el`FileFormatUtil.detectFileFormat()` método para detectar documentos cifrados, como se demuestra en esta guía.

### ¿Existen limitaciones al trabajar con formatos de documentos antiguos?

Los formatos de documentos más antiguos, como MS Word 6 o Word 95, pueden tener limitaciones en cuanto a funciones y compatibilidad con aplicaciones modernas. Considere actualizar o convertir estos documentos cuando sea necesario.

### ¿Puedo automatizar la detección del formato de documento en mi aplicación Java?

Sí, puedes automatizar la detección del formato de los documentos integrando el código proporcionado en tu aplicación Java. Esto te permite procesar los documentos en función de los formatos detectados.