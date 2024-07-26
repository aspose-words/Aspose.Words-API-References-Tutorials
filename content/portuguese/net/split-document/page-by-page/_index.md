---
title: Dividir documento do Word por página
linktitle: Dividir documento do Word por página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como dividir um documento do Word em páginas individuais usando Aspose.Words for .NET. Esta poderosa API simplifica o processo de divisão de documentos, tornando-o eficiente e conveniente.
type: docs
weight: 10
url: /pt/net/split-document/page-by-page/
---

Neste tutorial, orientaremos você sobre como dividir um documento do Word em páginas individuais usando o recurso de processamento de documentos do Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e obter documentos separados para cada página.

## Passo 1: Carregando o documento

Para começar, especifique o diretório do seu documento e carregue-o em um objeto Document. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Etapa 2: divisão do documento por página

Agora iremos percorrer cada página do documento e dividi-lo em páginas individuais. Veja como:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Salve cada página como um documento separado.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Exemplo de código-fonte para página por página usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso Página por página do Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Salve cada página como um documento separado.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Com este código você poderá dividir um documento do Word em páginas individuais usando Aspose.Words for .NET. Você também pode mesclar documentos separados, se necessário.

## Conclusão

Parabéns! Você aprendeu como dividir um documento do Word em páginas individuais usando o recurso Página por página do Aspose.Words for .NET. Seguindo o código-fonte fornecido, você pode extrair cada página de um documento e salvá-las como documentos separados.

Dividir um documento por página pode ser útil quando você precisa trabalhar com páginas específicas ou distribuir conteúdo de maneira granular. Aspose.Words for .NET fornece uma API poderosa que simplifica o processo de divisão de documentos, tornando-o eficiente e conveniente.

Sinta-se à vontade para explorar outros recursos oferecidos pelo Aspose.Words for .NET para aprimorar seus recursos de processamento de documentos e agilizar seu fluxo de trabalho.

### Perguntas frequentes

#### Como posso dividir um documento em várias páginas usando Aspose.Words for .NET?

 Para dividir um documento em várias páginas, você pode usar o`ExtractPages` método da API Aspose.Words para obter o intervalo de páginas. Ao especificar a página inicial e o número de páginas a serem extraídas, você pode criar documentos separados para cada página.

#### Posso personalizar o formato de saída ao dividir um documento por página?

Sim, Aspose.Words for .NET suporta vários formatos de saída ao dividir um documento por página. Você pode salvar cada página como um documento separado em formatos como DOCX, PDF, HTML e muito mais, dependendo de suas necessidades.

#### Posso dividir um documento por um intervalo de páginas específico?

Absolutamente! Aspose.Words for .NET permite dividir um documento por um intervalo de páginas específico. Ajustando a página inicial e o número de páginas a serem extraídas, você pode definir com precisão o intervalo de páginas para dividir o documento.

#### É possível mesclar os documentos divididos em um único documento?

Sim, você pode mesclar os documentos divididos novamente em um único documento usando a funcionalidade de mesclagem fornecida pelo Aspose.Words for .NET. Ao combinar os documentos separados, você pode recriar o documento original ou criar um novo documento com uma estrutura diferente, conforme necessário.