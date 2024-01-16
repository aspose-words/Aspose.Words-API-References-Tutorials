---
title: 트루타입 글꼴 폴더 설정
linktitle: 트루타입 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 트루타입 글꼴 폴더 설정에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-true-type-fonts-folder/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 트루타입 글꼴 폴더를 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 사용할 트루타입 글꼴이 포함된 사용자 정의 폴더를 지정하는 방법을 알게 됩니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집된 렌더링 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 렌더링할 문서 로드
 다음으로 렌더링할 문서를 로드해야 합니다.`Document` 수업. 올바른 문서 경로를 지정하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 트루타입 글꼴 폴더 설정
이제 인스턴스를 생성하여 렌더링할 때 사용할 트루타입 글꼴 폴더를 지정할 수 있습니다.`FontSettings` 수업과 사용`SetFontsFolder()` 글꼴 폴더를 설정하는 방법. 트루타입 글꼴이 포함된 사용자 정의 폴더를 지정할 수 있습니다. 두 번째 매개변수는`SetFontsFolder()` 지정된 폴더의 하위 폴더도 검색할지 여부를 나타냅니다.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 4단계: 렌더링된 문서 저장
 마지막으로 다음을 사용하여 렌더링된 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document` 수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### .NET용 Aspose.Words를 사용하여 트루타입 글꼴 폴더 설정에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// 이 설정은 기본적으로 검색되는 모든 기본 글꼴 소스를 재정의합니다. 이제 이 폴더만 검색됩니다.
// 글꼴을 렌더링하거나 포함할 때 글꼴. 시스템 글꼴 소스를 유지하면서 추가 글꼴 소스를 추가하려면 FontSettings.GetFontSources와
// 대신 FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// 글꼴 설정 지정
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 트루타입 글꼴 폴더를 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 문서를 렌더링할 때 사용할 트루타입 글꼴이 포함된 사용자 정의 폴더를 쉽게 지정할 수 있습니다. Aspose.Words는 문서의 글꼴을 사용한 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 문서를 특정 요구에 맞게 렌더링할 때 사용되는 글꼴을 제어하고 사용자 정의할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 트루타입 글꼴 폴더를 어떻게 구성할 수 있나요?

 A: Aspose.Words에서 트루타입 글꼴 폴더를 구성하려면 다음을 사용할 수 있습니다.`SetTrueTypeFontsFolder` 의 방법`Fonts` 트루타입 글꼴이 포함된 폴더의 위치를 지정하는 클래스입니다.

#### Q: 트루타입 글꼴로 간주되는 글꼴 유형은 무엇입니까?

A: 트루타입 글꼴은 널리 사용되는 글꼴 형식입니다. Word 문서에서 자주 사용되며 파일 확장자는 .ttf 또는 .ttc입니다.

#### Q: Aspose.Words에서 여러 트루타입 글꼴 폴더를 지정할 수 있나요?

A: 예, Aspose.Words에서 여러 트루타입 글꼴 폴더를 지정할 수 있습니다.`SetTrueTypeFontsFolder` 의 방법`Fonts` 폴더 위치 목록이 있는 클래스입니다.

#### Q: Aspose.Words에 구성된 트루타입 글꼴 폴더를 어떻게 확인할 수 있나요?

 A: Aspose.Words에 구성된 TrueType Fonts 폴더를 확인하려면 다음을 사용할 수 있습니다.`GetTrueTypeFontsFolder` 의 방법`Fonts` 클래스를 사용하여 구성된 TrueType 글꼴 폴더의 위치를 가져옵니다.

#### Q: Aspose.Words에서 트루타입 글꼴 폴더를 구성하는 것이 왜 중요한가요?

A: Aspose.Words에서 트루타입 글꼴 폴더를 설정하는 것은 Aspose.Words가 Word 문서를 처리할 때 필요한 글꼴을 찾는 데 도움이 되기 때문에 중요합니다. 이를 통해 서로 다른 시스템에서도 문서 형식 및 모양의 일관성이 보장됩니다.