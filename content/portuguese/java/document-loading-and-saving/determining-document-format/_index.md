---
title: Determinando o formato do documento em Aspose.Words para Java
linktitle: Determinando o formato do documento
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como detectar formatos de documentos em Java com Aspose.Words. Identifique DOC, DOCX e muito mais. Organize arquivos com eficiência.
type: docs
weight: 25
url: /pt/java/document-loading-and-saving/determining-document-format/
---

## Introdução à determinação do formato do documento em Aspose.Words para Java

Ao trabalhar com processamento de documentos em Java, é crucial determinar o formato dos arquivos com os quais você está lidando. Aspose.Words for Java fornece recursos poderosos para identificar formatos de documentos e orientaremos você durante o processo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

- [Aspose.Words para Java](https://releases.aspose.com/words/java/)
- Kit de desenvolvimento Java (JDK) instalado em seu sistema
- Conhecimento básico de programação Java

## Etapa 1: configuração do diretório

Primeiro, precisamos configurar os diretórios necessários para organizar nossos arquivos de forma eficaz. Criaremos diretórios para diferentes tipos de documentos.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Crie os diretórios se eles ainda não existirem.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Criamos diretórios para tipos de documentos suportados, desconhecidos, criptografados e anteriores a 97.

## Passo 2: Detectando o Formato do Documento

Agora vamos detectar o formato dos documentos em nossos diretórios. Usaremos Aspose.Words for Java para conseguir isso.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Exibir o tipo de documento
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Adicione casos para outros formatos de documentos conforme necessário
    }

    // Lidar com documentos criptografados
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Lidar com outros tipos de documentos
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

Neste trecho de código, iteramos pelos arquivos, detectamos seus formatos e os organizamos nos respectivos diretórios.

## Código-fonte completo para determinar o formato do documento em Aspose.Words for Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Crie os diretórios se eles ainda não existirem.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Exibir o tipo de documento
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Conclusão

Determinar formatos de documentos em Aspose.Words for Java é essencial para o processamento eficiente de documentos. Com as etapas descritas neste guia, você pode identificar os tipos de documentos e tratá-los adequadamente em seus aplicativos Java.

## Perguntas frequentes

### Como faço para instalar o Aspose.Words para Java?

 Você pode baixar Aspose.Words para Java no[aqui](https://releases.aspose.com/words/java/) e siga as instruções de instalação fornecidas.

### Quais são os formatos de documento suportados?

Aspose.Words for Java oferece suporte a vários formatos de documentos, incluindo DOC, DOCX, RTF, HTML e muito mais. Você pode consultar a documentação para obter uma lista completa.

### Como posso detectar documentos criptografados usando Aspose.Words for Java?

 Você pode usar o`FileFormatUtil.detectFileFormat()` método para detectar documentos criptografados, conforme demonstrado neste guia.

### Há alguma limitação ao trabalhar com formatos de documentos mais antigos?

Formatos de documentos mais antigos, como MS Word 6 ou Word 95, podem ter limitações em termos de recursos e compatibilidade com aplicativos modernos. Considere atualizar ou converter esses documentos quando necessário.

### Posso automatizar a detecção de formato de documento em meu aplicativo Java?

Sim, você pode automatizar a detecção do formato do documento integrando o código fornecido ao seu aplicativo Java. Isso permite processar documentos com base nos formatos detectados.