---
title: Java용 Aspose.Words에서 문서를 텍스트 파일로 저장하기
linktitle: 문서를 텍스트 파일로 저장
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 문서를 텍스트 파일로 저장하는 방법을 알아보세요. Java 코드 예제가 포함된 단계별 가이드를 따르세요.
type: docs
weight: 24
url: /ko/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Aspose.Words for Java에서 문서를 텍스트 파일로 저장하는 방법 소개

이 튜토리얼에서는 Aspose.Words for Java 라이브러리를 사용하여 문서를 텍스트 파일로 저장하는 방법을 살펴보겠습니다. Aspose.Words는 Word 문서 작업을 위한 강력한 Java API이며 일반 텍스트를 포함하여 다양한 형식으로 문서를 저장할 수 있는 다양한 옵션을 제공합니다. 이를 달성하기 위한 단계를 다루고 그 과정에서 샘플 Java 코드를 제공할 것입니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  프로젝트에 통합된 Java 라이브러리용 Aspose.Words. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).
- Java 프로그래밍에 대한 기본 지식.

## 1단계: 문서 만들기

문서를 텍스트 파일로 저장하려면 먼저 Aspose.Words를 사용하여 문서를 만들어야 합니다. 다음은 일부 콘텐츠가 포함된 문서를 생성하는 간단한 Java 코드 조각입니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

이 코드에서는 새 문서를 만들고 여기에 다양한 언어로 된 텍스트를 포함하여 일부 텍스트를 추가합니다.

## 2단계: 텍스트 저장 옵션 정의

다음으로 문서를 텍스트 파일로 저장하는 방법을 지정하는 텍스트 저장 옵션을 정의해야 합니다. bidi 표시 추가, 목록 들여쓰기 등과 같은 다양한 설정을 구성할 수 있습니다. 두 가지 예를 살펴보겠습니다.

### 예 1: Bidi 마크 추가

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 이 예에서는`TxtSaveOptions` 객체를 설정하고`AddBidiMarks`재산`true` 텍스트 출력에 bidi 표시를 포함합니다.

### 예 2: 목록 들여쓰기에 탭 문자 사용

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

여기서는 목록 들여쓰기에 탭 문자를 1개로 사용하도록 저장 옵션을 구성합니다.

## 3단계: 문서를 텍스트로 저장

이제 텍스트 저장 옵션을 정의했으므로 문서를 텍스트 파일로 저장할 수 있습니다. 다음 코드는 이를 수행하는 방법을 보여줍니다.

```java
doc.save("output.txt", saveOptions);
```

 바꾸다`"output.txt"` 텍스트 파일을 저장하려는 원하는 파일 경로를 사용하세요.

## Aspose.Words for Java에서 문서를 텍스트 파일로 저장하기 위한 완전한 소스 코드

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // 세 가지 수준의 들여쓰기로 목록을 만듭니다.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // 세 가지 수준의 들여쓰기로 목록을 만듭니다.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## 결론

이 튜토리얼에서는 Java용 Aspose.Words에서 문서를 텍스트 파일로 저장하는 방법을 배웠습니다. 문서를 만들고, 텍스트 저장 옵션을 정의하고, 문서를 텍스트 형식으로 저장하는 단계를 다루었습니다. Aspose.Words는 문서 저장과 관련하여 광범위한 유연성을 제공하므로 특정 요구 사항에 맞게 출력을 조정할 수 있습니다.

## FAQ

### 텍스트 출력에 bidi 표시를 어떻게 추가합니까?

 텍스트 출력에 bidi 표시를 추가하려면`AddBidiMarks` 의 자산`TxtSaveOptions` 에게`true`. 예를 들어:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### 목록 들여쓰기 문자를 사용자 정의할 수 있나요?

 예, 다음을 구성하여 목록 들여쓰기 문자를 사용자 정의할 수 있습니다.`ListIndentation` 의 자산`TxtSaveOptions`. 예를 들어 목록 들여쓰기에 탭 문자를 사용하려면 다음을 수행할 수 있습니다.

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java는 다국어 텍스트 처리에 적합합니까?

예, Aspose.Words for Java는 다국어 텍스트를 처리하는 데 적합합니다. 다양한 언어와 문자 인코딩을 지원하므로 다양한 언어로 된 문서 작업을 위한 다양한 선택이 가능합니다.

### Aspose.Words for Java에 대한 추가 문서와 리소스에 어떻게 액세스할 수 있나요?

 Aspose 설명서 웹사이트에서 Java용 Aspose.Words에 대한 포괄적인 설명서와 리소스를 찾을 수 있습니다.[Aspose.Words for Java 문서](https://reference.aspose.com/words/java/).

### Java용 Aspose.Words를 어디서 다운로드할 수 있나요?

 Aspose 웹사이트에서 Java용 Aspose.Words 라이브러리를 다운로드할 수 있습니다.[Java용 Aspose.Words 다운로드](https://releases.aspose.com/words/java/).