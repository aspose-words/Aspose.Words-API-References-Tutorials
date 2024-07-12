---
title: Mantenha a fonte unida
linktitle: Mantenha a fonte unida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mesclar documentos do Word usando Aspose.Words for .NET preservando a formatação. Este guia abrangente cobre tudo, desde a configuração até a execução.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/keep-source-together/
---
## Introdução

Na era digital de hoje, a manipulação programática de documentos do Word é essencial em vários setores. Aspose.Words for .NET capacita os desenvolvedores a automatizar tarefas de manuseio de documentos com eficiência. Este guia abrangente irá orientá-lo no processo de mesclagem de documentos, preservando a formatação de origem usando Aspose.Words for .NET.

## Pré-requisitos

Antes de mergulhar na fusão de documentos com Aspose.Words for .NET, certifique-se de ter o seguinte:

- Visual Studio: Ambiente de Desenvolvimento Integrado (IDE) para desenvolvimento .NET.
- Aspose.Words for .NET: instalado e configurado em seu ambiente de desenvolvimento.
- Familiaridade com C#: Compreensão básica da linguagem de programação C#.

## Importar namespaces

Para começar, importe os namespaces necessários:

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Etapa 1: carregar documentos

 Em primeiro lugar, carregue os documentos de origem e destino em Aspose.Words`Document` objetos.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

// Carregar documentos de origem e destino
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Etapa 2: definir o início da seção

Configure o início da seção para garantir que o conteúdo do documento de origem flua continuamente após o documento de destino.

```csharp
// Defina o documento de origem para aparecer logo após o conteúdo do documento de destino
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Etapa 3: mantenha os parágrafos juntos

Para manter a integridade da formatação, marque cada parágrafo no documento de origem para permanecer no próximo parágrafo.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Etapa 4: anexar documentos

 Mesclar os documentos usando o`AppendDocument` método, garantindo a manutenção da formatação do documento de origem.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: Salvar documento mesclado

Por fim, salve o documento mesclado no local desejado.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## Conclusão

Concluindo, Aspose.Words for .NET simplifica a tarefa de mesclar documentos do Word, preservando a formatação original perfeitamente. Esse recurso é crucial para aplicações que exigem processamento automatizado de documentos.

## Perguntas frequentes

### O Aspose.Words for .NET pode mesclar documentos de diferentes formatos?
Sim, pode mesclar documentos independente do formato, mantendo a formatação original.

### O Aspose.Words for .NET oferece suporte à mesclagem eficiente de documentos grandes?
Com certeza, ele lida com documentos grandes com desempenho ideal.

### Existe uma versão de teste disponível para Aspose.Words for .NET?
 Sim, você pode baixar uma versão de teste gratuita[aqui](https://releases.aspose.com/).

### Como posso obter suporte técnico para Aspose.Words for .NET?
 O suporte técnico está disponível através do[Fórum Aspose.Words](https://forum.aspose.com/c/words/8).

### Posso adquirir uma licença temporária do Aspose.Words for .NET?
 Sim, você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).