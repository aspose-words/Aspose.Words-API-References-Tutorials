---
title: 문서 작성기 없이 필드 포함 텍스트 삽입
linktitle: 문서 작성기 없이 FieldIncludeText 삽입
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words에서 DocumentBuilder를 사용하지 않고 FieldIncludeText를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-field-include-text-without-document-builder/
---
## 소개

문서 자동화 및 조작 분야에서 Aspose.Words for .NET은 강력한 도구입니다. 오늘은 DocumentBuilder를 사용하지 않고 FieldIncludeText를 삽입하는 방법에 대한 자세한 가이드를 살펴보겠습니다. 이 튜토리얼에서는 코드의 각 부분과 그 목적을 이해할 수 있도록 프로세스를 단계별로 안내합니다.

## 전제 조건

코드를 살펴보기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

1.  .NET용 Aspose.Words: 최신 버전이 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2. .NET 개발 환경: Visual Studio와 같은 .NET 호환 IDE.
3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Word 문서를 조작하는 데 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

이제 예제를 여러 단계로 나누어 보겠습니다. 각 단계는 명확성을 보장하기 위해 자세히 설명됩니다.

## 1단계: 디렉터리 경로 설정

첫 번째 단계는 문서 디렉터리의 경로를 정의하는 것입니다. 이곳은 귀하의 Word 문서가 저장되고 액세스되는 곳입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 단락 만들기

다음으로 새 문서를 만들고 해당 문서 내에 단락을 만듭니다. 이 단락에는 FieldIncludeText 필드가 포함됩니다.

```csharp
// 문서와 단락을 만듭니다.
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3단계: FieldIncludeText 필드 삽입

이제 FieldIncludeText 필드를 단락에 삽입합니다. 이 필드를 사용하면 다른 문서의 텍스트를 포함할 수 있습니다.

```csharp
// FieldIncludeText 필드를 삽입합니다.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

## 4단계: 필드 속성 설정

FieldIncludeText 필드의 속성을 지정해야 합니다. 여기에는 북마크 이름과 소스 문서의 전체 경로 설정이 포함됩니다.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = dataDir + "IncludeText.docx";
```

## 5단계: 문서에 단락 추가

필드가 설정되면 문서의 첫 번째 섹션 본문에 단락을 추가합니다.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 6단계: 필드 업데이트

문서를 저장하기 전에 FieldIncludeText를 업데이트하여 소스 문서에서 올바른 콘텐츠를 가져오도록 해야 합니다.

```csharp
fieldIncludeText.Update();
```

## 7단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

## 결론

그리고 거기에 있습니다! 다음 단계를 따르면 .NET용 Aspose.Words에서 DocumentBuilder를 사용하지 않고도 FieldIncludeText를 쉽게 삽입할 수 있습니다. 이 접근 방식은 한 문서의 콘텐츠를 다른 문서에 포함하는 효율적인 방법을 제공하므로 문서 자동화 작업이 훨씬 간단해집니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?  
Aspose.Words for .NET은 .NET 애플리케이션에서 Word 문서 작업을 위한 강력한 라이브러리입니다. 프로그래밍 방식으로 문서를 생성, 편집 및 변환할 수 있습니다.

### FieldIncludeText를 사용하는 이유는 무엇입니까?  
FieldIncludeText는 한 문서의 콘텐츠를 다른 문서에 동적으로 포함하여 보다 모듈화되고 유지 관리하기 쉬운 문서를 만드는 데 유용합니다.

### 이 방법을 사용하여 다른 파일 형식의 텍스트를 포함할 수 있습니까?  
FieldIncludeText는 특히 Word 문서에서 작동합니다. 다른 형식의 경우 Aspose.Words에서 제공하는 다른 메서드나 클래스가 필요할 수 있습니다.

### .NET용 Aspose.Words는 .NET Core와 호환됩니까?  
예, .NET용 Aspose.Words는 .NET Framework, .NET Core 및 .NET 5/6을 지원합니다.

### .NET용 Aspose.Words의 무료 평가판을 어떻게 받을 수 있나요?  
 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).