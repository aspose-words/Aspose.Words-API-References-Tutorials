---
title: Cargar Chm
linktitle: Cargar Chm
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a cargar archivos CHM con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/load-chm/
---

Cuando el procesamiento de textos con archivos de ayuda HTML (CHM) en una aplicación C#, es importante poder cargarlos correctamente. Con la biblioteca Aspose.Words para .NET, puede cargar fácilmente archivos CHM utilizando las opciones de carga adecuadas. En esta guía paso a paso, le mostraremos cómo usar Aspose.Words para el código fuente de .NET C# para cargar un archivo CHM usando las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de las opciones de carga

El primer paso es configurar las opciones de carga de nuestro archivo CHM. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, debemos establecer la propiedad Codificación en la codificación adecuada para los archivos CHM, normalmente "windows-1251". Aquí está cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Creamos un nuevo objeto LoadOptions y establecemos la propiedad Encoding en la codificación "windows-1251" para archivos CHM.

## Cargando archivo CHM

Ahora que hemos configurado las opciones de carga, podemos cargar el archivo CHM utilizando la clase Document y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

En este ejemplo, cargamos el archivo CHM "HTML help.chm" ubicado en el directorio de documentos utilizando las opciones de carga especificadas.

### Ejemplo de código fuente para LoadOptions con la funcionalidad "Load Chm" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuración de las opciones de carga con la función "Load Chm"
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Cargue el archivo CHM con las opciones especificadas
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Conclusión

En esta guía, explicamos cómo cargar un archivo CHM usando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. Cargar correctamente los archivos CHM es fundamental para poder manipularlos y convertirlos de manera eficiente con Aspose.Words.