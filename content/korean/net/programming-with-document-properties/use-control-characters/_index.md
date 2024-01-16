---
title: 제어 문자 사용
linktitle: 제어 문자 사용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 제어 문자를 사용하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/use-control-characters/
---

이 튜토리얼에서는 Aspose.Words for .NET에서 제어 문자를 사용하기 위한 C# 소스 코드를 안내합니다. 이 기능을 사용하면 텍스트의 제어 문자를 조작할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 제어 문자 사용

이 단계에서는 텍스트에 제어 문자를 사용하겠습니다. 다음 코드를 사용하세요.

```csharp
const string text = "test\r";
// 제어 문자 "\r"을 "\r\n"으로 바꿉니다.
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 이 코드는`text` 제어 문자 "\r"(개행)을 포함하는 문자열이며`Replace` 이를 제어 문자 "\r\n"(개행)으로 바꾸는 방법입니다. 줄 다음에 줄바꿈이 옵니다).

### .NET용 Aspose.Words를 사용하여 제어 문자 사용에 대한 예제 소스 코드

```csharp

	const string text = "test\r";
	// "\r" 제어 문자를 "\r\n"으로 바꾸십시오.
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 위의 코드를 자신의 프로젝트에서 교체하여 사용할 수 있습니다.`text` 제어 문자가 포함된 자신만의 텍스트로 문자열을 만듭니다.

이제 .NET용 Aspose.Words에서 제어 문자를 사용하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 애플리케이션에서 제어 문자를 쉽게 조작할 수 있습니다.