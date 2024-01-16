---
title: Word 문서에서 서명 액세스 및 확인
linktitle: Word 문서에서 서명 액세스 및 확인
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 디지털 서명에 액세스하고 확인하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/access-and-verify-signature/
---
이 튜토리얼에서는 Aspose.Words for .NET의 액세스 및 서명 확인 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서의 디지털 서명에 액세스하여 유효성을 확인할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드 및 서명 액세스

디지털 서명이 포함된 문서를 업로드하여 시작하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## 2단계: 디지털 서명 찾아보기

루프를 사용하여 문서의 모든 디지털 서명을 반복합니다.

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// 서명 정보에 액세스
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// 이 속성은 MS Word 문서에서만 사용할 수 있습니다.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

필요에 따라 표시 메시지를 사용자 정의하십시오.

### .NET용 Aspose.Words를 사용하여 액세스 및 서명 확인을 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 액세스 및 서명 확인을 위한 전체 소스 코드입니다.

```csharp
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// 이 속성은 MS Word 문서에서만 사용할 수 있습니다.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서의 디지털 서명에 쉽게 액세스하고 확인할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 디지털 서명에 액세스하고 확인하는 기능을 살펴보았습니다. 제공된 단계를 따르면 쉽게 문서를 로드하고, 디지털 서명에 액세스하고, 유효성을 확인할 수 있습니다. 디지털 서명에 액세스하고 확인하는 기능은 Word 문서의 무결성과 신뢰성을 보장하는 방법을 제공합니다. Aspose.Words for .NET은 디지털 서명이 포함된 단어 처리를 위한 강력한 API를 제공하여 확인 프로세스를 자동화하고 문서 보안을 강화할 수 있습니다.

### FAQ

#### Q: Word 문서의 디지털 서명이란 무엇입니까?

A: Word 문서의 디지털 서명은 문서의 무결성과 원본을 인증하는 방법을 제공하는 전자 서명입니다. 이는 디지털 인증서와 암호화 알고리즘을 사용하여 생성되므로 수신자는 문서가 변경되지 않았는지, 해당 문서가 신뢰할 수 있는 소스에서 나온 것인지 확인할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 디지털 서명에 어떻게 액세스할 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서의 디지털 서명에 액세스하려면 다음 단계를 따르세요.
1.  다음을 사용하여 문서를 로드합니다.`Document` 클래스를 선택하고 문서 파일의 경로를 지정합니다.
2.  루프를 사용하여`DigitalSignatures` 문서 수집. 각 반복은 디지털 서명을 나타냅니다.

#### Q: Word 문서의 디지털 서명을 통해 어떤 정보에 액세스할 수 있나요?

A: Word 문서의 디지털 서명을 통해 다음과 같은 다양한 정보에 액세스할 수 있습니다.
- 유효성: 서명이 유효한지 확인합니다.
- 설명: 서명자가 지정한 서명 이유를 가져옵니다.
- 서명 시간: 문서에 서명된 시간을 가져옵니다.
- 주체 이름: 서명자 또는 인증서 주체의 이름을 검색합니다.
- 발급자 이름: 인증서 발급자의 이름을 가져옵니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 디지털 서명의 유효성을 확인할 수 있습니까?

 A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 디지털 서명의 유효성을 확인할 수 있습니다. 액세스하여`IsValid` 의 재산`DigitalSignature` 개체를 사용하면 서명이 유효한지 여부를 확인할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 디지털 서명의 유효성을 어떻게 확인할 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서에서 디지털 서명의 유효성을 확인하려면 다음 단계를 따르세요.
1.  액세스`DigitalSignatures` 문서 수집.
2.  각각을 반복`DigitalSignature` 컬렉션의 개체입니다.
3.  사용`IsValid` 의 재산`DigitalSignature` 서명이 유효한지 확인하는 개체입니다.

#### Q: Word 문서의 디지털 서명에서 서명자의 설명이나 서명 이유를 검색할 수 있나요?

A: 예, Word 문서의 디지털 서명에서 서명자의 설명이나 서명 이유를 검색할 수 있습니다. 그만큼`Comments` 의 재산`DigitalSignature` 개체는 서명 프로세스 중에 서명자가 지정한 설명에 대한 액세스를 제공합니다.

#### Q: Aspose.Words for .NET에서 서명 확인 기능은 어떤 유형의 문서를 지원합니까?

A: Aspose.Words for .NET의 서명 확인 기능은 DOCX 파일 형식을 사용하는 Word 문서의 디지털 서명 확인을 지원합니다. 이 기능을 사용하여 DOCX 파일의 서명을 확인할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 있는 디지털 서명의 인증서 세부 정보에 어떻게 액세스할 수 있나요?

 A: Aspose.Words for .NET을 사용하여 Word 문서에 있는 디지털 서명의 인증서 세부 정보에 액세스하려면`CertificateHolder` 의 재산`DigitalSignature` 물체. 로부터`CertificateHolder` 개체 이름, 발급자 이름 등 인증서의 다양한 세부 정보를 검색할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 디지털 서명의 표시 또는 처리를 사용자 정의할 수 있습니까?

 A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 디지털 서명의 표시 또는 처리를 사용자 정의할 수 있습니다. 속성과 메서드에 액세스하여`DigitalSignature` 개체를 사용하면 원하는 정보를 추출하거나, 추가 유효성 검사를 수행하거나, 서명 확인 프로세스를 애플리케이션의 작업 흐름에 통합할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 여러 디지털 서명을 확인할 수 있습니까?

 A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 여러 디지털 서명을 확인할 수 있습니다. 반복함으로써`DigitalSignatures` 문서를 수집하면 각 디지털 서명에 개별적으로 액세스하고 확인할 수 있습니다.

