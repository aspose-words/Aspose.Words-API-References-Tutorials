---
title: 작은 메타파일을 압축하지 마세요
linktitle: 작은 메타파일을 압축하지 마세요
second_title: Aspose.Words 문서 처리 API
description: 문서를 저장할 때 작은 메타파일 압축 안 함 기능을 활성화하기 위해 .NET용 Aspose.Words를 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

문서의 메타데이터를 압축하는 것은 C# 애플리케이션에서 파일을 단어 처리할 때 일반적인 기능입니다. 그러나 품질을 유지하기 위해 작은 파일의 메타데이터를 압축하지 않아도 될 수 있습니다. 이 단계별 가이드에서는 .NET용 Aspose.Words의 C# 소스 코드를 사용하여 문서 저장 옵션에서 "작은 메타파일 압축 안 함" 기능을 활성화하는 방법을 보여줍니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## 1단계: 문서 디렉터리 설정

첫 번째 단계는 문서를 저장할 디렉터리를 정의하는 것입니다. 전체 디렉터리 경로를 지정해야 합니다. 예를 들어 :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 2단계: 섹션 및 텍스트 삽입

그런 다음 문서에 섹션과 텍스트를 삽입할 수 있습니다. Aspose.Words에서 제공하는 DocumentBuilder 클래스를 사용하여 문서 콘텐츠를 빌드하세요. 다음은 간단한 예입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

이 예에서는 새 빈 문서를 만든 다음 DocumentBuilder를 사용하여 텍스트 줄을 추가합니다.

## 3단계: 설정 옵션

'등록

이제 문서의 저장 옵션을 구성해 보겠습니다. DocSaveOptions 클래스를 사용하여 저장 설정을 지정합니다. 예를 들어 :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

이 예에서는 저장 옵션을 설정하기 위해 새 DocSaveOptions 개체를 만듭니다.

## 4단계: "작은 메타파일을 압축하지 않음" 기능 활성화

 "작은 메타파일을 압축하지 않음" 기능을 활성화하려면 다음을 설정해야 합니다.`Compliance` DocSaveOptions 개체의 속성을 값으로`PdfCompliance.PdfA1a`. 방법은 다음과 같습니다.

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

이 구성을 사용하면 문서를 저장할 때 작은 파일 메타데이터가 압축되지 않습니다.

## 5단계: 문서 저장

마지막으로 다음을 사용하여 문서를 저장할 수 있습니다.`Save` Document 클래스의 메소드 파일의 전체 경로와 원하는 파일 이름을 지정합니다. 예를 들어 :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

"dataDir"을 문서 디렉토리 경로로 바꾸십시오.

### .NET용 Aspose.Words를 사용하여 작은 메타파일을 압축하지 않음 기능을 갖춘 DocSaveOptions의 예제 소스 코드

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 일부 텍스트가 포함된 두 섹션을 삽입합니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// "작은 메타파일을 압축하지 않음" 기능으로 저장 옵션 구성
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// 지정된 옵션으로 문서를 저장합니다.
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## 결론

이 가이드에서는 문서를 저장할 때 "작은 메타파일을 압축하지 않음" 기능을 활성화하기 위해 .NET용 Aspose.Words 라이브러리를 사용하는 방법을 설명했습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 압축되지 않은 작은 파일 메타데이터를 보존하는 것은 문서 품질과 무결성을 유지하는 데 중요할 수 있습니다.