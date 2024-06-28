---
title: Direção do texto do documento
linktitle: Direção do texto do documento
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como especificar a direção do texto em seus documentos com Aspose.Words for .NET. Melhore a exibição de idiomas escritos da direita para a esquerda.
type: docs
weight: 10
url: /pt/net/programming-with-txtloadoptions/document-text-direction/
---

Neste tutorial, exploraremos o código-fonte C# fornecido para o recurso "Direção do texto do documento" com Aspose.Words for .NET. Este recurso permite especificar a direção do texto em um documento, o que é especialmente útil para idiomas escritos da direita para a esquerda, como hebraico ou árabe.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Etapa 2: configurar opções de upload

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Nesta etapa, configuramos as opções de carregamento do documento. Criamos um novo`TxtLoadOptions` objeto e definir o`DocumentDirection`propriedade para`DocumentDirection.Auto`. Este valor diz ao Aspose.Words para determinar automaticamente a direção do texto com base no conteúdo do documento.

## Passo 3: Carregando o documento

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo de texto a ser carregado. Também usamos as opções de carregamento especificadas.

## Etapa 4: manipular o parágrafo e exibir a direção do texto

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Nesta etapa, acessamos o primeiro parágrafo do documento utilizando o`FirstSection` e`Body` propriedades. A seguir, acessamos o`ParagraphFormat.Bidi` propriedade para obter a direção do texto do parágrafo. Em seguida, exibimos esse valor no console.

## Etapa 5: salve o documento

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Nesta última etapa, salvamos o documento resultante no formato .docx usando o`Save` método e passando o caminho para o arquivo de saída.

Agora você pode executar o código-fonte para carregar o documento de texto e determinar a direção do texto. O documento resultante será salvo no diretório especificado com o nome "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Exemplo de código-fonte para funcionalidade de direção de texto de documento com Aspose.Words for .NET.


```csharp

            
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusão

Neste tutorial, exploramos o recurso de direção de texto do documento em Aspose.Words for .NET. Aprendemos como especificar a direção do texto em um documento, especialmente para idiomas escritos da direita para a esquerda, como hebraico ou árabe.

Este recurso é essencial para garantir que o texto seja exibido corretamente em documentos multilíngues. Ao usar as opções de carregamento apropriadas, o Aspose.Words pode detectar automaticamente a direção do texto e aplicá-lo ao documento.

Com Aspose.Words, você pode manipular facilmente a direção do texto em seus documentos, proporcionando uma experiência de leitura suave e intuitiva para os usuários.

É importante observar que esse recurso é especialmente útil no processamento de palavras com idiomas que exigem direção de texto específica. Aspose.Words facilita essa tarefa, fornecendo ferramentas poderosas para gerenciar a direção do texto em seus documentos.

Lembre-se de usar as opções de carregamento apropriadas, como definir a direção automática do texto, para obter os resultados desejados em seus documentos.

Aspose.Words for .NET oferece muitos recursos avançados para manipulação e geração de documentos. Explorando ainda mais a documentação e os exemplos fornecidos por Aspose.Words, você poderá explorar totalmente os recursos desta poderosa biblioteca.

Portanto, não hesite em integrar a direção do texto do documento em seus projetos Aspose.Words for .NET e aproveitar seus benefícios para criar documentos multilíngues atraentes e de alta qualidade.