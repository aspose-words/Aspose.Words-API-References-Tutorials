---
title: Estilos de destino de uso de lista
linktitle: Estilos de destino de uso de lista
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a unir y agregar documentos de Word mientras conserva los estilos de lista del documento de destino con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/list-use-destination-styles/
---

Este tutorial lo guiará a través del proceso de uso de la función List Use Destination Styles de Aspose.Words para .NET. Esta característica le permite unir y agregar documentos de Word mientras usa los estilos de lista del documento de destino.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicialice los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir`variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue los documentos de origen y destino

 A continuación, debe cargar los documentos de origen y destino utilizando Aspose.Words`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Paso 3: configure el documento de origen para continuar después del documento de destino

 Para asegurarse de que el contenido del documento de origen continúe después del final del documento de destino, debe configurar el`SectionStart` propiedad de la primera sección en el documento fuente para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Paso 4: Formateo de la lista de identificadores

Para manejar el formato de la lista, iterará a través de cada párrafo en el documento de origen y verificará si es un elemento de la lista. Si es así, comparará el ID de la lista con las listas existentes en el documento de destino. Si existe una lista con el mismo ID, creará una copia de la lista en el documento de origen y actualizará el formato de lista del párrafo para usar la lista copiada.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Paso 5: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`AppendDocument` metodo de la`Document` clase. El`ImportFormatMode.UseDestinationStyles` El parámetro garantiza que los estilos de lista del documento de destino se utilicen durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Paso 6: Guarde el documento final

 Finalmente, guarde el documento fusionado con la función Enumerar Usar estilos de destino habilitada usando el`Save` metodo de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Ejemplo de código fuente para List Use Destination Styles usando Aspose.Words para .NET 

Aquí está el código fuente completo para la función "List Use Destination Styles" en C# usando Aspose.Words para .NET:


```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Configure el documento de origen para que continúe inmediatamente después del final del documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Lleve un registro de las listas que se crean.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Compruebe si el documento de destino ya contiene una lista con este ID. Si lo hace, entonces esto puede
			//hacer que las dos listas se ejecuten juntas. En su lugar, cree una copia de la lista en el documento de origen.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Ya existe una lista recién copiada para este ID, recupere la lista almacenada,
				// y utilícelo en el párrafo actual.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Agregue una copia de esta lista al documento y guárdela para referencia posterior.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Establezca la lista de este párrafo en la lista copiada.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Agregue el documento de origen al final del documento de destino.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

¡Eso es todo! Ha implementado con éxito la función Estilos de destino de uso de lista mediante Aspose.Words para .NET. El documento final contendrá el contenido combinado con los estilos de lista del documento de destino.