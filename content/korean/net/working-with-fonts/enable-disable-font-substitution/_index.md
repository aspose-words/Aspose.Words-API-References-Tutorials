---
title: 글꼴 대체 비활성화 활성화
linktitle: 글꼴 대체 비활성화 활성화
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 글꼴 대체를 활성화하거나 비활성화하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/enable-disable-font-substitution/
---
이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서를 렌더링할 때 Word 문서에서 글꼴 대체를 활성화하거나 비활성화하는 방법을 안내합니다. 글꼴 대체를 활성화하거나 비활성화하면 누락된 글꼴을 기본 글꼴로 자동으로 바꿀지 여부를 제어할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리
- 글꼴 대체 여부에 관계없이 렌더링하려는 Word 문서

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 업로드 및 글꼴 설정 구성
 다음으로 렌더링하려는 Word 문서를 로드하고`FontSettings` 글꼴 설정을 처리하는 클래스입니다. 글꼴 이름을 지정하여 기본 글꼴 재정의를 설정하겠습니다.`DefaultFontName` 글꼴 정보 재정의를 비활성화합니다.`Enabled` 로 설정`false`.

```csharp
// 문서를 로드하세요
Document doc = new Document(dataDir + "Rendering.docx");

// 글꼴 설정 구성
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// 문서에 글꼴 설정 적용
doc.FontSettings = fontSettings;
```

## 3단계: 렌더링된 문서 저장
마지막으로 정의된 글꼴 재정의 설정을 준수하는 렌더링된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### .NET용 Aspose.Words를 사용하여 글꼴 대체 비활성화 활성화에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서를 렌더링할 때 Word 문서에서 글꼴 대체를 활성화하거나 비활성화하는 방법을 살펴보았습니다. 글꼴 대체를 제어하면 렌더링된 문서에서 누락된 글꼴을 처리하는 방법에 영향을 줄 수 있습니다. 주저하지 말고 이 기능을 사용하여 Word 문서의 글꼴 관리를 사용자 정의하세요.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서에서 글꼴 대체를 활성화하려면 어떻게 해야 합니까?

A: Aspose.Words를 사용하여 Word 문서에서 글꼴 대체를 활성화하려면 API를 사용하여 필요한 글꼴을 사용할 수 없을 때 사용할 대체 글꼴을 지정할 수 있습니다. 이렇게 하면 원본 글꼴이 없어도 일관된 텍스트 시각화가 보장됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서에서 글꼴 대체를 비활성화할 수 있습니까?

A: 예, Aspose.Words를 사용하면 Word 문서에서 글꼴 대체를 비활성화할 수 있습니다. API를 사용하면 Word에서 필요한 글꼴을 다른 글꼴로 대체하는 것을 방지하여 텍스트의 원래 모양을 유지할 수 있습니다.

#### Q: Word 문서에서 대체하는 동안 필요한 글꼴이 누락되면 어떻게 됩니까?

A: Word 문서에서 대체하는 동안 필요한 글꼴이 누락된 경우 Aspose.Words는 이 문제를 감지하고 해결 옵션을 제공할 수 있습니다. 누락된 글꼴을 대체 글꼴로 대체하거나 누락된 글꼴을 문서에 포함하여 올바르게 볼 수 있도록 선택할 수 있습니다.

#### Q: Word 문서를 Aspose.Words로 대체할 때 누락된 글꼴을 어떻게 처리할 수 있나요?

A: Word 문서에서 Aspose.Words로 대체할 때 누락된 글꼴을 처리하려면 API를 사용하여 누락된 글꼴을 감지하고 해결 옵션을 제공할 수 있습니다. 필요에 따라 누락된 글꼴을 대체 글꼴로 대체하거나 문서에 누락된 글꼴을 포함하도록 선택할 수 있습니다.

#### Q: Word 문서에서 글꼴 대체를 제어하는 것이 중요합니까?

A: 예, 텍스트의 시각적 무결성을 유지하려면 Word 문서에서 글꼴 대체를 제어하는 것이 중요합니다. Aspose.Words를 사용하여 글꼴 대체를 활성화하거나 비활성화하면 필요한 글꼴이 사용되는지 확인하고 누락되거나 대체된 글꼴 문제를 피할 수 있습니다.