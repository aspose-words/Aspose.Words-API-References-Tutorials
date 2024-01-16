---
title: Ms Word 버전 설정
linktitle: Ms Word 버전 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 특정 버전의 MS Word로 문서를 로드하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-loadoptions/set-ms-word-version/
---
C# 애플리케이션에서 Word 문서로 단어를 처리하는 경우 문서를 로드할 때 사용할 Microsoft Word 버전을 지정해야 할 수도 있습니다. .NET용 Aspose.Words 라이브러리를 사용하면 LoadOptions를 사용하여 사용할 MS Word 버전을 쉽게 설정할 수 있습니다. 이 단계별 가이드에서는 .NET C# 소스 코드용 Aspose.Words를 사용하여 LoadOptions 로드 옵션을 사용하여 지정된 MS Word 버전으로 문서를 로드하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## 로드 옵션 구성

첫 번째 단계는 문서의 로드 옵션을 구성하는 것입니다. LoadOptions 클래스를 사용하여 로딩 매개변수를 지정합니다. 우리의 경우 MswVersion 속성을 원하는 MS Word 버전으로 설정해야 합니다. 예를 들어 Microsoft Word 2010 버전을 사용하고 있습니다. 수행 방법은 다음과 같습니다.

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

새 LoadOptions 개체를 만들고 MswVersion 속성을 MsWordVersion.Word2010으로 설정하여 MS Word 2010 버전을 지정합니다.

## 특정 버전의 MS Word로 문서 로딩

이제 로드 옵션을 구성했으므로 Document 클래스를 사용하여 문서를 로드하고 로드 옵션을 지정할 수 있습니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

이 예에서는 지정된 로드 옵션을 사용하여 문서 디렉터리에 있는 "Document.docx" 문서를 로드합니다.

### .NET용 Aspose.Words를 사용하여 "MS Word 버전 설정" 기능을 갖춘 LoadOptions의 예제 소스 코드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "MS Word 버전 설정" 기능으로 로드 옵션 구성
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// 지정된 버전의 MS Word가 포함된 문서를 로드합니다.
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// 문서 저장
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리를 사용하여 특정 MS Word 버전을 지정하는 문서를 업로드하는 방법을 설명했습니다. 제공된 단계를 수행하고 제공된 코드 C# 소스를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 특정 버전의 MS Word로 문서를 로드하면 응용 프로그램에서 문서의 적절한 호환성과 처리를 보장할 수 있습니다.


### FAQ

#### Q: C# 애플리케이션에서 문서를 로드할 때 MS Word 버전을 지정해야 하는 이유는 무엇입니까?

MS Word 버전을 지정하면 특히 버전마다 다를 수 있는 특정 형식이나 기능을 처리할 때 문서가 올바르게 로드되고 처리됩니다.

#### Q: Aspose.Words는 어떤 MS Word 버전을 지원합니까?

A: Aspose.Words for .NET은 Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 등을 포함한 다양한 버전의 MS Word를 지원합니다.

#### 질문: 내 시스템에 설치된 것과 다른 버전의 MS Word를 사용하여 문서를 로드할 수 있습니까?

A: 예, Aspose.Words를 사용하면 문서를 로드할 때 다른 버전의 MS Word를 지정할 수 있으므로 대상 시스템에 다른 MS Word 버전이 있어도 호환성이 보장됩니다.

#### Q: MS Word 버전을 설정하면 C# 애플리케이션에 어떤 이점이 있습니까?

답변: MS Word 버전을 설정하면 해당 특정 버전의 의도된 형식과 기능에 따라 문서가 처리되어 일관된 출력을 제공할 수 있습니다.

#### Q: Aspose.Words는 DOCX 문서만 처리하도록 제한되어 있나요?

A: 아니요, Aspose.Words는 DOC, RTF, HTML, PDF 등을 포함한 다양한 문서 형식을 지원하므로 다양한 유형의 문서를 처리하기 위한 다목적 도구입니다.