---
title: 글꼴 알림 받기
linktitle: 글꼴 알림 받기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용할 때 누락되거나 대체된 글꼴 알림을 받는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/receive-notifications-of-fonts/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하는 동안 글꼴 알림을 받는 방법을 안내합니다. 글꼴 알림을 사용하면 문서에서 누락되거나 대체된 글꼴을 감지하고 관리할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

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

## 2단계: 문서 로드 및 글꼴 설정 구성
 다음으로, 다음을 사용하여 문서를 로드하겠습니다.`Document` 클래스를 사용하여 글꼴 설정을 구성합니다.`FontSettings` 수업. 글꼴이 누락된 경우 사용할 기본 글꼴을 설정합니다.

```csharp
// 문서를 로드하고 글꼴 설정을 구성합니다.
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## 3단계: 알림 핸들러 설정
다음으로, 다음을 구현하여 알림 핸들러를 정의하겠습니다.`IWarningCallback` 상호 작용. 이를 통해 문서를 저장할 때 글꼴 경고를 수집할 수 있습니다.

```csharp
// 알림 핸들러 정의
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## 4단계: 글꼴 설정 적용 및 문서 저장
마지막으로 문서에 글꼴 설정을 적용하고 저장하겠습니다. 모든 글꼴 경고는 앞서 정의한 알림 처리기에 의해 캡처됩니다.

```csharp
// 글꼴 설정 적용 및 문서 저장
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### .NET용 Aspose.Words를 사용하여 글꼴 알림 수신에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// 누락된 글꼴이 있는 경우 사용할 기본 글꼴을 선택할 수 있습니다.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// 테스트를 위해 존재하지 않는 폴더에서만 글꼴을 찾도록 Aspose.Words를 설정합니다. Aspose.Words 이후로는 그렇지 않습니다.
// 지정된 디렉토리에서 글꼴을 찾으면 렌더링하는 동안 문서의 글꼴이 기본값으로 대체됩니다.
// FontSettings.DefaultFontName에 지정된 글꼴입니다. 우리는 콜백을 사용하여 이 제안을 선택할 수 있습니다.
fontSettings.SetFontsFolder(string.Empty, false);
//문서 저장 중에 생성된 경고를 수집하는 IWarningCallback을 구현하는 새 클래스를 만듭니다.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하는 동안 글꼴 알림을 받는 방법을 살펴보았습니다. 글꼴 알림을 사용하면 문서에서 누락되거나 대체된 글꼴을 감지하고 관리할 수 있습니다. 이 기능을 사용하면 문서의 글꼴 일관성을 보장하고 글꼴이 누락된 경우 적절한 조치를 취할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 누락된 글꼴에 대한 알림을 어떻게 받을 수 있나요?

 A: Aspose.Words에서 누락된 글꼴에 대한 알림을 받으려면 다음을 사용할 수 있습니다.`FontSettings` 수업과`FontSubstitutionCallback` 이벤트. 문서 처리 중 누락된 글꼴이 발견되면 알림을 받을 콜백 방법을 설정할 수 있습니다.

#### Q: Word 문서에서 누락된 글꼴을 처리하려면 어떻게 해야 합니까?

A: Word 문서에서 누락된 글꼴을 처리하려면 다양한 전략을 사용할 수 있습니다. Aspose.Words 애플리케이션을 실행하는 시스템에 누락된 글꼴을 설치하거나 누락된 글꼴을 사용 가능한 대체 글꼴로 대체할 수 있습니다.

#### Q: Aspose.Words에서 대체 글꼴 알림을 받을 수 있나요?

 A: 네, Aspose.Words에서 대체 글꼴 알림을 받을 수 있습니다. 문서 처리 중 글꼴이 대체되면 다음을 통해 알림을 받을 수 있습니다.`FontSubstitutionCallback` 이벤트를 확인하고 적절한 조치를 취하여 텍스트 모양을 조정합니다.

#### Q: Aspose.Words에서 글꼴을 대체할 때 텍스트 모양을 일관되게 유지하려면 어떻게 해야 합니까?

A: 글꼴을 대체할 때 텍스트 모양의 일관성을 유지하려면 글꼴 크기, 스타일, 색상과 같은 텍스트 서식 속성을 조정할 수 있습니다. 원래 글꼴과 시각적으로 유사한 대체 글꼴을 사용하는 것도 고려해 볼 수 있습니다.