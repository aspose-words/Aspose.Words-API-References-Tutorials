---
title: Listar estilos de destino de uso
linktitle: Listar estilos de destino de uso
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como juntar e anexar documentos do Word preservando os estilos de lista do documento de destino usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/list-use-destination-styles/
---

Este tutorial irá guiá-lo através do processo de uso do recurso List Use Destination Styles do Aspose.Words for .NET. Este recurso permite unir e anexar documentos do Word enquanto usa os estilos de lista do documento de destino.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Aspose.Words para .NET instalado. Você pode baixá-lo do site Aspose ou instalá-lo via NuGet.
2. Visual Studio ou qualquer outro ambiente de desenvolvimento C#.

## Etapa 1: inicializar os diretórios de documentos

 Primeiro, você precisa definir o caminho para o diretório do seu documento. Modifique o valor do`dataDir` variável para o caminho onde seus documentos estão localizados.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Carregar os Documentos de Origem e Destino

 Em seguida, você precisa carregar os documentos de origem e destino usando o Aspose.Words`Document` aula. Atualize os nomes dos arquivos no`Document` construtor de acordo com os nomes dos seus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Etapa 3: definir o documento de origem para continuar após o documento de destino

 Para garantir que o conteúdo do documento de origem continue após o final do documento de destino, você precisa definir o`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Etapa 4: lidar com a formatação da lista

Para lidar com a formatação da lista, você percorrerá cada parágrafo do documento de origem e verificará se é um item da lista. Se for, você comparará o ID da lista com as listas existentes no documento de destino. Se existir uma lista com o mesmo ID, você criará uma cópia da lista no documento de origem e atualizará o formato da lista do parágrafo para usar a lista copiada.

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

## Etapa 5: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.UseDestinationStyles` O parâmetro garante que os estilos de lista do documento de destino sejam usados durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Etapa 6: salve o documento final

Por fim, salve o documento mesclado com o recurso Listar estilos de destino de uso habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Exemplo de código-fonte para estilos de destino de uso de lista usando Aspose.Words para .NET 

Aqui está o código-fonte completo do recurso "List Use Destination Styles" em C# usando Aspose.Words for .NET:


```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Defina o documento de origem para continuar logo após o final do documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Acompanhe as listas que são criadas.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Verifique se o documento de destino já contém uma lista com este ID. Se isso acontecer, então isso pode
			// fazer com que as duas listas sejam executadas juntas. Crie uma cópia da lista no documento de origem.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Já existe uma lista recém-copiada para este ID, recupere a lista armazenada,
				// e use-o no parágrafo atual.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Adicione uma cópia desta lista ao documento e guarde-a para referência posterior.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Defina a lista deste parágrafo para a lista copiada.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Anexe o documento de origem ao final do documento de destino.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

É isso! Você implementou com sucesso o recurso List Use Destination Styles usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os estilos de lista do documento de destino.