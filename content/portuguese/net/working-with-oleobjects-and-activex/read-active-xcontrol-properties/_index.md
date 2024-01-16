---
title: Leia as propriedades ativas do XControl no arquivo Word
linktitle: Leia as propriedades ativas do XControl no arquivo Word
second_title: API de processamento de documentos Aspose.Words
description: Leia as propriedades dos controles ActiveX em um arquivo do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Neste guia passo a passo, mostraremos como ler propriedades de controles ActiveX em um arquivo Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Etapa 1: inicialização do documento

 O primeiro passo é inicializar o`Document` objeto carregando o documento do Word que contém os controles ActiveX. Certifique-se de substituir`MyDir` com o caminho real para o diretório que contém o documento.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Passo 2: Recuperar controles ActiveX

 Nesta etapa, iremos iterar através de cada`Shape` do documento para recuperar os controles ActiveX e ler suas propriedades.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Exemplo de código-fonte para leitura de propriedades ativas do XControl usando Aspose.Words for .NET

Aqui está o código-fonte completo para leitura de propriedades de controles ActiveX usando Aspose.Words for .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Conclusão

Este guia mostrou como ler propriedades de controles ActiveX em um arquivo Word usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode inicializar o documento, recuperar controles ActiveX e ler suas propriedades. Use o código de amostra fornecido como ponto de partida e personalize-o de acordo com suas necessidades específicas.

A leitura das propriedades dos controles ActiveX permite extrair informações importantes dos arquivos do Word que contêm esses controles. Aspose.Words for .NET oferece recursos poderosos para processamento de palavras com controles ActiveX e automatização do processamento de documentos.

### Perguntas frequentes

#### P: Qual é a primeira etapa para ler as propriedades dos controles ActiveX em um arquivo do Word?

 R: O primeiro passo é inicializar o`Document` objeto carregando o documento do Word que contém os controles ActiveX. Certifique-se de substituir`MyDir` com o caminho real para o diretório que contém o documento.

#### P: Como coloco controles ActiveX no documento?

 R: Para recuperar controles ActiveX, você precisa percorrer cada`Shape` do documento e verifique se é um controle ActiveX. Use o`OleFormat` propriedade de`Shape` para acessar o`OleControl` objeto e recupere as propriedades necessárias.

#### P: Quais propriedades dos controles ActiveX posso ler?

R: Você pode ler diversas propriedades de controles ActiveX, como legenda, valor, estado habilitado ou desabilitado, tipo e childNodes associados ao controle.

#### P: Como posso obter o número total de controles ActiveX no documento?

 R: Para obter o número total de controles ActiveX no documento, você pode usar o`GetChildNodes` método do`Document` objeto especificando o`NodeType.Shape` tipo e incluindo os nós filhos.