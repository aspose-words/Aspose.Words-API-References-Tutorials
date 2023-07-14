---
title: Lista de reinicios en cada sección
linktitle: Lista de reinicios en cada sección
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a restablecer una lista numerada en cada sección de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-list/restart-list-at-each-section/
---

En este tutorial paso a paso, le mostraremos cómo restablecer una lista numerada en cada sección de un documento de Word utilizando Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde el sitio oficial.

## Paso 1: crear el documento y la lista

Primero, cree un nuevo documento y agregue una lista numerada predeterminada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Paso 2: agregar elementos a la lista

 Luego usa un`DocumentBuilder` para agregar elementos a la lista. Puede usar un bucle para agregar varios elementos a la lista:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

En este ejemplo, estamos insertando un salto de sección después del decimoquinto elemento de la lista para ilustrar la renumeración.

## Paso 3: Guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Entonces ! Ha restablecido con éxito una lista numerada para cada sección en un documento de Word usando Aspose.Words para .NET.

### Ejemplo de código fuente para restablecer la lista en cada sección

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo para satisfacer sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo reiniciar una lista en cada sección de Aspose.Words?

 R: Para reiniciar una lista en cada sección de Aspose.Words, debe crear una instancia de la`List` class y asígnele una lista numerada. Entonces puedes usar el`List.IsRestartAtEachSection` propiedad para especificar que la numeración debe reiniciarse en cada sección. Puede asociar esta lista con una o más secciones de su documento para que la numeración se reinicie correctamente en cada sección.

#### P: ¿Puedo personalizar el formato de numeración de las listas en Aspose.Words?

 R: Sí, puede personalizar el formato de numeración de las listas en Aspose.Words. El`List` class ofrece varias propiedades para esto, como`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`etc. Puede usar estas propiedades para establecer el tipo de lista (numerada, con viñetas, etc.), el formato de numeración (números arábigos, números romanos, letras, etc.) y otras opciones de formato de numeración.

#### P: ¿Es posible agregar niveles adicionales a una lista numerada en Aspose.Words?

 R: Sí, es posible agregar niveles adicionales a una lista numerada en Aspose.Words. El`ListLevel` class le permite establecer propiedades de formato para cada nivel de la lista. Puede configurar opciones como prefijo, sufijo, alineación, sangría, etc. Esto le permite crear listas con múltiples niveles de jerarquía.