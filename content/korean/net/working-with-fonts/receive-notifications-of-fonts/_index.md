---
title: 글꼴 알림 받기
linktitle: 글꼴 알림 받기
second_title: Aspose.Words 문서 처리 API
description: 자세한 가이드를 통해 .NET용 Aspose.Words에서 글꼴 대체 알림을 받는 방법을 알아보세요. 항상 문서가 올바르게 렌더링되는지 확인하세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/receive-notifications-of-fonts/
---


문서에서 글꼴이 올바르게 렌더링되지 않는 문제에 직면한 적이 있다면 혼자가 아닙니다. 글꼴 설정을 관리하고 글꼴 대체에 대한 알림을 받으면 많은 어려움을 겪을 수 있습니다. 이 포괄적인 가이드에서는 .NET용 Aspose.Words를 사용하여 글꼴 알림을 처리하여 문서가 항상 최상의 상태로 보이도록 하는 방법을 살펴보겠습니다.

## 전제조건

자세한 내용을 알아보기 전에 다음 사항이 있는지 확인하세요.

- C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 따라가는 데 도움이 됩니다.
-  .NET 라이브러리용 Aspose.Words: 다음에서 다운로드하여 설치하세요.[공식 다운로드 링크](https://releases.aspose.com/words/net/).
- 개발 환경: 코드를 작성하고 실행하기 위한 Visual Studio와 같은 설정입니다.
-  샘플 문서: 샘플 문서를 준비합니다(예:`Rendering.docx`) 글꼴 설정을 테스트할 준비가 되었습니다.

## 네임스페이스 가져오기

Aspose.Words 작업을 시작하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이를 통해 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
```

## 1단계: 문서 디렉터리 정의

먼저 문서가 저장된 디렉터리를 지정합니다. 이는 처리하려는 문서를 찾는 데 중요합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드

 문서를 Aspose.Words에 로드하세요.`Document` 물체. 이를 통해 프로그래밍 방식으로 문서를 조작할 수 있습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 글꼴 설정 구성

이제 필요한 글꼴을 찾을 수 없는 경우 Aspose.Words가 사용해야 하는 기본 글꼴을 지정하도록 글꼴 설정을 구성합니다.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";

// 존재하지 않는 폴더에서만 글꼴을 찾도록 Aspose.Words를 설정하세요.
fontSettings.SetFontsFolder(string.Empty, false);
```

## 4단계: 경고 콜백 설정

 글꼴 대체 경고를 캡처하고 처리하려면`IWarningCallback` 상호 작용. 이 클래스는 문서 처리 중에 발생하는 모든 경고를 기록합니다.

```csharp
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        // 우리는 대체되는 글꼴에만 관심이 있습니다.
        if (info.WarningType == WarningType.FontSubstitution)
        {
            Console.WriteLine("Font substitution: " + info.Description);
        }
    }
}
```

## 5단계: 문서에 콜백 및 글꼴 설정 할당

경고 콜백과 구성된 글꼴 설정을 문서에 할당합니다. 이렇게 하면 모든 글꼴 문제가 캡처되고 기록됩니다.

```csharp
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
```

## 6단계: 문서 저장

마지막으로 글꼴 설정을 적용하고 글꼴 대체를 처리한 후 문서를 저장합니다. 원하는 형식으로 저장하세요. 여기서는 PDF로 저장하겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

다음 단계에 따라 글꼴 대체를 적절하게 처리하고 대체가 발생할 때마다 알림을 받도록 애플리케이션을 구성했습니다.

## 결론

이제 Aspose.Words for .NET을 사용하여 글꼴 대체에 대한 알림을 받는 프로세스를 마스터했습니다. 이 기술은 필요한 글꼴을 사용할 수 없는 경우에도 문서가 항상 최상의 상태로 보이도록 하는 데 도움이 됩니다. Aspose.Words의 기능을 최대한 활용하려면 다양한 설정으로 계속 실험해 보세요.

## 자주 묻는 질문

### Q1: 여러 기본 글꼴을 지정할 수 있나요?

아니요. 대체할 기본 글꼴은 하나만 지정할 수 있습니다. 그러나 여러 대체 글꼴 소스를 구성할 수 있습니다.

### Q2: Aspose.Words for .NET 무료 평가판은 어디서 구할 수 있나요?

 다음에서 무료 평가판을 다운로드할 수 있습니다.[Aspose 무료 평가판 페이지](https://releases.aspose.com/).

###  Q3: 다른 유형의 경고를 처리할 수 있나요?`IWarningCallback`?

 예,`IWarningCallback` 인터페이스는 글꼴 대체뿐만 아니라 다양한 유형의 경고를 처리할 수 있습니다.

### Q4: Aspose.Words에 대한 지원은 어디서 찾을 수 있나요?

 방문하다[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8) 도움을 위해.

### Q5: Aspose.Words에 대한 임시 라이선스를 얻을 수 있나요?

 네, 임시 면허는 다음 기관에서 받으실 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).