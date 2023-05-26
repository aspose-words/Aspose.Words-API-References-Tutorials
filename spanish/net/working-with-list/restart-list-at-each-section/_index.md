---
title: Lista de reinicios en cada sección
linktitle: Lista de reinicios en cada sección
second_title: Referencia de API de Aspose.Words para .NET
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
