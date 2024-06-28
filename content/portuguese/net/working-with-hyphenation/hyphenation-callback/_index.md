---
title: Retorno de chamada de hifenização
linktitle: Retorno de chamada de hifenização
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a implementar o retorno de chamada de hifenização no Aspose.Words for .NET para aprimorar a formatação de documentos com este guia passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/working-with-hyphenation/hyphenation-callback/
---

## Introdução

Ei! Você já se viu envolvido nas complexidades da formatação de texto, especialmente ao lidar com idiomas que exigem hifenização? Você não está sozinho. A hifenização, embora crucial para o layout adequado do texto, pode ser uma dor de cabeça. Mas adivinhe? Aspose.Words for .NET está à sua volta. Esta poderosa biblioteca permite gerenciar a formatação de texto perfeitamente, incluindo o tratamento da hifenização por meio de um mecanismo de retorno de chamada. Intrigado? Vamos mergulhar nos detalhes de como você pode implementar um retorno de chamada de hifenização usando Aspose.Words for .NET.

## Pré-requisitos

Antes de sujarmos as mãos com o código, vamos ter certeza de que você tem tudo o que precisa:

1.  Aspose.Words for .NET: Certifique-se de ter a biblioteca. Você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. IDE: Um ambiente de desenvolvimento como o Visual Studio.
3. Conhecimento básico de C#: Compreensão de C# e .NET framework.
4. Dicionários de hifenização: dicionários de hifenização para os idiomas que você planeja usar.
5.  Licença Aspose: Uma licença Aspose válida. Você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) se você não tiver um.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso garante que nosso código tenha acesso a todas as classes e métodos que precisamos do Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Etapa 1: registrar o retorno de chamada de hifenização

Para começar, precisamos registrar nosso retorno de chamada de hifenização. É aqui que dizemos ao Aspose.Words para usar nossa lógica de hifenização personalizada.

```csharp
try
{
    // Registrar retorno de chamada de hifenização.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Aqui, estamos criando uma instância do nosso retorno de chamada personalizado e atribuindo-o a`Hyphenation.Callback`.

## Etapa 2: definir o caminho do documento

A seguir, precisamos definir o diretório onde nossos documentos serão armazenados. Isso é crucial porque carregaremos e salvaremos documentos deste caminho.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para seus documentos.

## Etapa 3: carregue o documento

Agora, vamos carregar o documento que requer hifenização.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 Aqui, estamos carregando um documento de texto em alemão. Você pode substituir`"German text.docx"` com o nome do arquivo do seu documento.

## Etapa 4: salve o documento

Após carregar o documento, salvamos ele em um novo arquivo, aplicando o callback de hifenização no processo.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Esta linha salva o documento como PDF com hifenização aplicada.

## Etapa 5: lidar com exceção de dicionário de hifenização ausente

Às vezes, você pode se deparar com um problema em que o dicionário de hifenização está faltando. Vamos cuidar disso.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

Neste bloco, capturamos a exceção específica relacionada aos dicionários ausentes e imprimimos a mensagem.

## Etapa 6: implementar a classe de retorno de chamada de hifenização personalizada

 Agora, vamos implementar o`CustomHyphenationCallback` classe que trata da solicitação de dicionários de hifenização.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Registre o dicionário para o idioma solicitado.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 Nesta aula, o`RequestDictionary` O método é chamado sempre que um dicionário de hifenização é necessário. Verifica o idioma e registra o dicionário apropriado.

## Conclusão

E aí está! Você acabou de aprender como implementar um retorno de chamada de hifenização no Aspose.Words for .NET. Seguindo essas etapas, você pode garantir que seus documentos sejam formatados de maneira bonita, independentemente do idioma. Esteja você lidando com inglês, alemão ou qualquer outro idioma, esse método permite lidar com a hifenização sem esforço.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de manipulação de documentos que permite aos desenvolvedores criar, modificar e converter documentos programaticamente.

### Por que a hifenização é importante na formatação de documentos?
A hifenização melhora o layout do texto, quebrando as palavras nos locais apropriados, garantindo um documento mais legível e visualmente atraente.

### Posso usar o Aspose.Words gratuitamente?
 Aspose.Words oferece um teste gratuito. Você pode conseguir isso[aqui](https://releases.aspose.com/).

### Como obtenho um dicionário de hifenização?
Você pode baixar dicionários de hifenização de vários recursos online ou criar os seus próprios, se necessário.

### O que acontece se faltar um dicionário de hifenização?
 Se faltar um dicionário, o`RequestDictionary` O método lança uma exceção, que você pode manipular para informar o usuário ou fornecer um substituto.