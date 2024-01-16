---
title: 로드 옵션이 있는 글꼴 설정
linktitle: 로드 옵션이 있는 글꼴 설정
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 사용자 정의 로딩 옵션과 해당 글꼴 설정을 사용하여 Word 문서를 로드하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/font-settings-with-load-options/
---
이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 글꼴 설정과 함께 로딩 옵션을 사용하는 방법을 보여 드리겠습니다. 로드 옵션을 사용하면 문서를 로드할 때 글꼴 설정을 포함한 추가 설정을 지정할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 글꼴 설정으로 로딩 옵션 구성
 다음으로 인스턴스를 생성하겠습니다.`LoadOptions`새 인스턴스를 생성하여 글꼴 설정을 지정합니다.`FontSettings` 그리고 그것을 할당`loadOptions.FontSettings`.

```csharp
// 글꼴 설정으로 로딩 옵션 구성
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();
```

## 3단계: 로드 옵션을 사용하여 문서 로드
 이제 다음을 사용하여 문서를 로드하겠습니다.`LoadOptions` 구성한 로드 옵션을 지정합니다.

```csharp
// 로드 옵션을 사용하여 문서를 로드합니다.
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

### .NET용 Aspose.Words를 사용하여 로드 옵션이 있는 글꼴 설정에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 설정과 함께 로딩 옵션을 사용하는 방법을 살펴보았습니다. 로드 옵션을 사용하면 글꼴 설정을 포함한 추가 설정을 지정하여 문서 로드를 사용자 정의할 수 있습니다. 이 기능을 사용하여 특정 요구 사항에 맞게 문서 로드를 맞춤화할 수 있습니다.

### FAQ

#### Q: Aspose.Words에 문서를 로드할 때 기본 글꼴을 어떻게 지정합니까?

 A: Aspose.Words에서 문서를 로드할 때 기본 글꼴을 지정하려면`LoadOptions` 클래스를 설정하고`DefaultFontName` 속성을 원하는 글꼴 이름으로 설정합니다.

#### Q: Aspose.Words의 로딩 옵션으로 지정할 수 있는 다른 글꼴 설정은 무엇입니까?

A: 기본 글꼴을 지정하는 것 외에도 적절한 속성을 사용하여 기본 인코딩과 같은 다른 글꼴 설정을 지정할 수도 있습니다.`LoadOptions` 같은 수업`DefaultEncoding`.

#### Q: 문서를 로드할 때 지정된 기본 글꼴을 사용할 수 없으면 어떻게 됩니까?

A: 문서가 Aspose.Words에 로드될 때 지정된 기본 글꼴을 사용할 수 없는 경우 대체 글꼴이 문서의 텍스트를 표시하는 데 사용됩니다. 이로 인해 원본 글꼴과 모양이 약간 다를 수 있습니다.

#### Q: 업로드된 문서마다 다른 글꼴 설정을 지정할 수 있나요?

 A: 예, 별도의 인스턴스를 사용하여 로드된 각 문서에 대해 서로 다른 글꼴 설정을 지정할 수 있습니다.`LoadOptions` 클래스를 선택하고 각 인스턴스에 대해 원하는 글꼴 설정을 지정합니다. 이를 통해 각 문서의 글꼴 모양을 독립적으로 사용자 정의할 수 있습니다.