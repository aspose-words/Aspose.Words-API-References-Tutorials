---
title: Protección de solo lectura en documentos de Word
linktitle: Protección de solo lectura en documentos de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a proteger sus documentos de Word de solo lectura con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/read-only-protection/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de protección de solo lectura de Aspose.Words para .NET. Esta función le permite hacer que un documento de Word sea de solo lectura para evitar modificaciones no autorizadas. Siga los pasos a continuación:

## Paso 1: Creación del documento y aplicación de la protección

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: escribir contenido en el documento
Utilice el objeto DocumentBuilder para escribir contenido en el documento:

```csharp
builder.Write("Open document as read-only");
```

## Paso 3: establezca la contraseña y haga que el documento sea de solo lectura

Establezca una contraseña para el documento utilizando la propiedad SetPassword() del objeto WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Asegúrese de reemplazar "MyPassword" con la contraseña real que desea usar.

## Paso 4: Aplicar documento de solo lectura

Haga que el documento sea de solo lectura configurando la propiedad ReadOnlyRecommended en verdadero:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Paso 5: aplique la protección de solo lectura y guarde el documento

Finalmente, aplique la protección de solo lectura utilizando el método Protect() del objeto Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento protegido.

### Ejemplo de código fuente para la protección de solo lectura con Aspose.Words para .NET

Aquí está el código fuente completo para la protección de solo lectura usando Aspose.Words para .NET:

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Introduzca una contraseña de hasta 15 caracteres.
doc.WriteProtection.SetPassword("MyPassword");

// Haga que el documento sea de solo lectura.
doc.WriteProtection.ReadOnlyRecommended = true;

// Aplique la protección contra escritura como de solo lectura.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Siguiendo estos pasos, puede proteger fácilmente sus documentos

## Conclusión

En este tutorial, exploramos la función de protección de solo lectura de Aspose.Words para .NET, que le permite hacer que los documentos de Word sean de solo lectura para evitar modificaciones no autorizadas. Siguiendo los pasos proporcionados, puede aplicar fácilmente la protección de solo lectura a sus documentos y mejorar su seguridad. La protección de solo lectura ayuda a garantizar la integridad y precisión del contenido de su documento al restringir las capacidades de edición. Aspose.Words para .NET proporciona una API potente y flexible para gestionar la protección de documentos y es compatible con otras funciones para personalizar y proteger sus documentos de Word.

### Preguntas frecuentes sobre protección de solo lectura en documentos de Word

#### P: ¿Qué es la protección de solo lectura en Aspose.Words para .NET?

R: La protección de solo lectura en Aspose.Words para .NET es una característica que le permite hacer que un documento de Word sea de solo lectura, evitando modificaciones no autorizadas. Cuando un documento está configurado como de solo lectura, los usuarios pueden abrir y ver el documento, pero no pueden realizar ningún cambio en su contenido.

#### P: ¿Cómo puedo aplicar la protección de solo lectura a un documento de Word usando Aspose.Words para .NET?

R: Para aplicar la protección de solo lectura a un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una instancia de la`Document` clase y un`DocumentBuilder` objeto.
2.  Utilizar el`DocumentBuilder` para escribir contenido en el documento.
3.  Establezca una contraseña para el documento mediante el`SetPassword` metodo de la`WriteProtection` objeto.
4.  Selecciona el`ReadOnlyRecommended` propiedad de la`WriteProtection` oponerse a`true` para recomendar abrir el documento como de solo lectura.
5.  Aplicar protección de solo lectura mediante el`Protect` metodo de la`Document` objeto, especificando el`ProtectionType` como`ReadOnly`.
6.  Guarde el documento protegido utilizando el`Save` metodo de la`Document` objeto.

#### P: ¿Puedo eliminar la protección de solo lectura de un documento de Word usando Aspose.Words para .NET?

R: Sí, puede quitar la protección de solo lectura de un documento de Word usando Aspose.Words para .NET. Para ello, puede utilizar el`Unprotect` metodo de la`Document` class, que elimina cualquier protección existente del documento.

#### P: ¿Puedo establecer una contraseña diferente para la protección de solo lectura en un documento de Word?

 R: No, la protección de solo lectura en Aspose.Words para .NET no le permite establecer una contraseña separada específicamente para la protección de solo lectura. La contraseña configurada mediante el`SetPassword` metodo de la`WriteProtection` El objeto se aplica a la protección general del documento, incluida la protección de solo lectura y de lectura y escritura.

#### P: ¿Pueden los usuarios omitir la protección de solo lectura en un documento de Word?

R: La protección de solo lectura en un documento de Word pretende desalentar y prevenir modificaciones accidentales o no autorizadas. Si bien proporciona un nivel de protección, los usuarios con suficientes conocimientos técnicos o permisos de edición pueden omitirlo. Sin embargo, la protección de solo lectura sirve como elemento disuasorio y ayuda a mantener la integridad del documento.