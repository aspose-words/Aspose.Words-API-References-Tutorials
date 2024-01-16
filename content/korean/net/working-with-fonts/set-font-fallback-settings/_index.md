---
title: 글꼴 대체 설정 지정
linktitle: 글꼴 대체 설정 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 글꼴 대체 설정을 지정하고 Word 문서에서 글꼴 대체를 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-font-fallback-settings/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 대체 설정을 지정하는 방법을 보여줍니다. 글꼴 대체 설정을 사용하면 지정된 글꼴을 사용할 수 없을 때 사용할 대체 글꼴을 지정할 수 있습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
 Word 문서 위치에 대한 디렉터리 경로를 설정하여 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 글꼴 대체 설정 로드
 인스턴스를 생성합니다.`FontSettings` 클래스를 사용하고`Load` XML 파일에서 글꼴 재정의 설정을 로드하는 방법입니다. 지정된 XML 파일에는 사용할 글꼴 대체 규칙이 포함되어 있어야 합니다.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## 3단계: 글꼴 대체 설정 적용
 문서의 글꼴 대체 설정을 할당하여 문서와 글꼴 대체 설정을 연결합니다.`FontSettings` 재산.

```csharp
doc.FontSettings = fontSettings;
```

## 4단계: 문서 저장
 다음을 사용하여 문서를 저장합니다.`Save` 의 방법`Document` 적절한 경로와 파일 이름을 사용하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### .NET용 Aspose.Words를 사용하여 글꼴 대체 설정 설정에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 대체 설정을 지정하는 방법을 배웠습니다. 지정된 글꼴을 사용할 수 없는 경우에도 문서가 일관되게 보이도록 다양한 글꼴 대체 규칙을 실험해 보세요.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서에서 글꼴 대체 설정을 어떻게 지정할 수 있나요?

A: Aspose.Words를 사용하여 Word 문서에서 글꼴 대체 설정을 지정하려면 API를 사용하여 필요한 글꼴을 사용할 수 없을 때 사용할 대체 글꼴을 지정할 수 있습니다. 이를 통해 원본 글꼴이 없어도 일관된 텍스트 시각화가 보장됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서를 재정의할 때 대체 글꼴을 처리할 수 있나요?

A: 예, Aspose.Words를 사용하면 Word 문서에서 대체할 때 대체 글꼴을 관리할 수 있습니다. API를 사용하면 누락된 글꼴을 감지하고 적절한 대체 글꼴을 지정하여 글꼴이 대체되는 경우에도 일관된 텍스트 모양을 유지할 수 있습니다.

#### Q: Word 문서에서 글꼴 대체 설정을 올바르게 구성하는 것이 왜 중요한가요?

A: 텍스트의 시각적 무결성을 유지하려면 Word 문서에서 글꼴 대체 설정을 올바르게 구성하는 것이 중요합니다. Aspose.Words를 사용하여 적절한 대체 글꼴을 설정하면 필요한 글꼴을 사용할 수 없는 경우에도 텍스트가 일관되게 표시됩니다.

#### Q: Word 문서를 Aspose.Words로 대체할 때 누락된 글꼴을 어떻게 감지할 수 있나요?

A: Aspose.Words를 사용하면 API를 사용하여 Word 문서에서 대체하는 동안 누락된 글꼴을 감지할 수 있습니다. Aspose.Words에서 제공하는 방법을 사용하여 필요한 글꼴의 가용성을 확인하고 글꼴이 누락된 경우 적절한 조치를 취할 수 있습니다.

#### Q: 글꼴 대체가 내 Word 문서의 레이아웃에 영향을 줍니까?

A: 대체 글꼴이 원래 글꼴과 크기가 다른 경우 글꼴 대체가 Word 문서의 레이아웃에 영향을 미칠 수 있습니다. 그러나 대체 글꼴을 현명하게 선택하고 Aspose.Words로 글꼴 대체 설정을 구성하면 레이아웃에 미치는 영향을 최소화할 수 있습니다.