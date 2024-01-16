---
title: 하이픈 넣기 콜백
linktitle: 하이픈 넣기 콜백
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 하이픈 콜백을 사용하여 단어 하이픈을 처리하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-hyphenation/hyphenation-callback/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET의 하이픈 넣기 콜백 기능을 사용하는 방법을 보여줍니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 라이브러리를 다운로드하여 설치하세요.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 하이픈 연결 알림 저장

 먼저 사용자 정의를 사용하여 하이픈 넣기 콜백을 등록하겠습니다.`CustomHyphenationCallback` 수업. 이를 통해 자체 규칙에 따라 단어 하이픈 넣기를 처리할 수 있습니다.

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 다음을 구현했는지 확인하세요.`CustomHyphenationCallback` 귀하의 특정 요구에 따라 수업.

## 2단계: 문서 로드 및 하이픈 적용

다음으로, 지정된 디렉터리에서 문서를 로드하고 Aspose.Words를 사용하여 단어에 하이픈을 넣습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 3단계: 누락된 사전 오류 처리

하이픈 사전이 누락된 경우 해당 예외를 포착하고 오류 메시지를 표시합니다.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## 4단계: 하이픈 넣기 알림 정리 및 비활성화

마지막으로 청결을 유지하고 하이픈 넣기 알림을 끄려면 다음 단계를 수행하세요.

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

이렇게 하면 처리가 완료된 후 하이픈 넣기 알림이 정리되고 비활성화됩니다.

그래서 ! .NET용 Aspose.Words에서 하이픈 넣기 콜백을 성공적으로 사용했습니다.

### .NET용 Aspose.Words를 사용한 하이픈 넣기 콜백의 샘플 소스 코드

```csharp
try
{
	 // 하이픈 콜백을 등록합니다.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 맞게 수정하십시오.

### FAQ

#### Q: Aspose.Words의 음절 알림은 무엇입니까?

A: Aspose.Words의 음절 알림은 문서에서 단어의 음절을 사용자 정의할 수 있는 기능입니다. 음절 미리 알림을 사용하면 단어의 음절에 대한 사용자 정의 규칙을 지정할 수 있습니다. 이는 기본 음절이 원하는 결과를 생성하지 못하는 특정 언어나 특정 시나리오에 유용할 수 있습니다.

#### Q: Aspose.Words에서 음절 알림을 설정하는 방법은 무엇입니까?

 A: Aspose.Words에서 하이픈 넣기 콜백을 정의하려면 다음을 구현하는 클래스를 생성해야 합니다.`HyphenationCallback` 인터페이스를 구현하고`HandleWord()` 방법. 이 메서드는 음절을 구성하는 동안 나타나는 각 단어에 대해 호출됩니다. 여기에 사용자 정의 음절 규칙을 적용하고 음절 단어를 반환할 수 있습니다. 그런 다음 다음을 사용하여 하이픈 넣기 콜백을 바인딩할 수 있습니다.`Document.HyphenationCallback` 문서의 속성입니다.

#### Q: Aspose.Words에서 음절 미리 알림을 사용하면 어떤 이점이 있나요?

A: Aspose.Words에서 음절 미리 알림을 사용하면 문서에서 단어의 음절을 사용자 정의할 수 있다는 이점이 있습니다. 이를 통해 특히 기본 음절이 원하는 결과를 제공하지 않는 특정 언어나 시나리오의 경우 음절을 더 효과적으로 제어할 수 있습니다. 필요에 따라 정확한 음절을 얻기 위해 각 단어에 특정 규칙을 적용할 수 있습니다.

#### Q: 음절 미리 알림을 사용하는 것이 도움이 될 수 있는 일반적인 시나리오는 무엇입니까?

A: 음절 부스터를 사용하면 다음과 같은 여러 시나리오에서 유용할 수 있습니다.
- 특정 음절 규칙이 있는 특정 언어의 단어 음절입니다.
- 약어나 기술 단어에 대한 맞춤형 음절 규칙 적용.
- 스타일 선호도나 인쇄 기준에 따라 음절을 조정합니다.

#### Q: Aspose.Words의 음절 미리 알림을 사용하여 사용자 정의 음절을 어떻게 테스트할 수 있나요?

 A: Aspose.Words의 음절 미리 알림을 사용하여 사용자 정의 음절을 테스트하려면 사용자 정의 음절 규칙을 적용하려는 단어가 포함된 테스트 문서를 만들 수 있습니다. 그런 다음 사용자 정의 음절 콜백을 설정하고`Document.Range.Replace()` 문서의 단어를 바꾸는 방법과`Hyphenate()` 의 방법`Hyphenation` 단어의 음절을 알아내는 클래스입니다. 그런 다음 필요에 따라 음절 사이에 하이픈을 추가하여 음절 단어의 형식을 지정할 수 있습니다.