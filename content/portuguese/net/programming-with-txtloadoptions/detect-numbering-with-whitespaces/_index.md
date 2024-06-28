---
title: Detectar numeração com espaços em branco
linktitle: Detectar numeração com espaços em branco
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como detectar números de lista com espaços em branco no Aspose.Words for .NET. Melhore a estrutura dos seus documentos com facilidade.
type: docs
weight: 10
url: /pt/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Neste tutorial, exploraremos o código-fonte C# fornecido para o recurso "Detecção de numeração com espaços em branco" com Aspose.Words for .NET. Este recurso permite detectar e criar listas a partir de um documento de texto contendo números de lista seguidos de espaços em branco.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Etapa 2: Criando o documento de texto

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Nesta etapa, criamos uma string de texto que simula um documento de texto contendo números de lista seguidos de espaços em branco. Usamos diferentes delimitadores de lista, como ponto final, colchete direito, símbolo de marcador e espaços em branco.

## Etapa 3: configurar opções de upload

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Nesta etapa, configuramos as opções de carregamento do documento. Criamos um novo`TxtLoadOptions` objeto e definir o`DetectNumberingWithWhitespaces`propriedade para`true`. Isso permitirá que o Aspose.Words detecte números de lista mesmo que sejam seguidos por espaços em branco.

## Etapa 4: Carregar o documento e salvar

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Nesta etapa, carregamos o documento usando a sequência de texto especificada e as opções de carregamento. Usamos um`MemoryStream` para converter a string de texto em um fluxo de memória. Em seguida, salvamos o documento resultante no formato .docx.

### Exemplo de código-fonte para o recurso de detecção de numeração de espaço em branco com Aspose.Words para .NET.

```csharp

            
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Crie um documento de texto simples na forma de uma string com partes que podem ser interpretadas como listas.
// Ao carregar, as três primeiras listas serão sempre detectadas pelo Aspose.Words,
// e os objetos List serão criados para eles após o carregamento.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// A quarta lista, com espaços em branco entre o número da lista e o conteúdo do item da lista,
// só será detectado como uma lista se "DetectNumberingWithWhitespaces" em um objeto LoadOptions estiver definido como verdadeiro,
// para evitar que parágrafos que começam com números sejam erroneamente detectados como listas.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Carregue o documento aplicando LoadOptions como parâmetro e verifique o resultado.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Agora você pode executar o código-fonte para carregar o documento de texto contendo números de lista com espaços em branco e, em seguida, criar um documento .docx com as listas detectadas. O arquivo de saída será salvo no diretório especificado com o nome "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusão
Neste tutorial, exploramos o recurso de detecção de numeração de espaços em branco no Aspose.Words for .NET. Aprendemos como criar listas a partir de um documento de texto contendo números de lista seguidos de espaços em branco.

Este recurso é extremamente útil para processar documentos contendo números de listas formatados de diferentes maneiras. Ao usar as opções de carregamento apropriadas, Aspose.Words é capaz de detectar esses números de lista, mesmo que sejam seguidos de espaços em branco, e convertê-los em listas estruturadas no documento final.

Usar esse recurso pode economizar tempo e melhorar a eficiência do fluxo de trabalho. Você pode extrair facilmente informações de documentos de texto e convertê-los em documentos bem estruturados com listas adequadas.

Lembre-se de considerar opções de carregamento, como configurar a detecção de discagem por espaço em branco, para obter os resultados desejados.

Aspose.Words for .NET oferece muitos recursos avançados para manipulação e geração de documentos. Explorando ainda mais a documentação e os exemplos fornecidos por Aspose.Words, você poderá explorar totalmente os recursos desta poderosa biblioteca.

Portanto, não hesite em integrar a detecção de numeração de espaços em branco em seus projetos Aspose.Words for .NET e aproveitar seus benefícios para criar documentos bem estruturados e legíveis.


