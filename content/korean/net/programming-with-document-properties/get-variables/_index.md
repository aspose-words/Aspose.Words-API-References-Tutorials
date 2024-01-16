---
title: 변수 가져오기
linktitle: 변수 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서 변수를 검색하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/get-variables/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서에서 변수를 검색하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서에 정의된 변수에 액세스할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 변수를 검색하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 변수 검색

이제 문서에 정의된 변수를 검색하겠습니다. 다음 코드를 사용하세요.

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

이 코드는 문서 변수의 각 키-값 쌍을 반복하고 각 변수의 이름과 값을 검색합니다. 그런 다음 변수를 연결하여 각 변수에 대한 정보를 표시합니다.

### .NET용 Aspose.Words를 사용하여 변수 가져오기에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 .NET용 Aspose.Words를 사용하여 문서에서 변수를 검색하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 문서에서 변수에 쉽게 액세스하고 볼 수 있습니다.