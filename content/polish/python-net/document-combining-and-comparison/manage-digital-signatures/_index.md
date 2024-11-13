---
title: Zarządzanie podpisami cyfrowymi i autentycznością
linktitle: Zarządzanie podpisami cyfrowymi i autentycznością
second_title: Aspose.Words API zarządzania dokumentami Python
description: Dowiedz się, jak zarządzać podpisami cyfrowymi i zapewnić autentyczność dokumentów za pomocą Aspose.Words dla Pythona. Przewodnik krok po kroku z kodem źródłowym.
type: docs
weight: 17
url: /pl/python-net/document-combining-and-comparison/manage-digital-signatures/
---

## Wprowadzenie do podpisów cyfrowych

Podpisy cyfrowe służą jako elektroniczne odpowiedniki podpisów odręcznych. Zapewniają sposób weryfikacji autentyczności, integralności i pochodzenia dokumentów elektronicznych. Gdy dokument jest podpisany cyfrowo, generowany jest skrót kryptograficzny na podstawie zawartości dokumentu. Ten skrót jest następnie szyfrowany przy użyciu klucza prywatnego sygnatariusza, tworząc podpis cyfrowy. Każdy, kto ma odpowiedni klucz publiczny, może zweryfikować podpis i ustalić autentyczność dokumentu.

## Konfigurowanie Aspose.Words dla Pythona

Aby rozpocząć zarządzanie podpisami cyfrowymi za pomocą Aspose.Words dla języka Python, wykonaj następujące kroki:

1. Zainstaluj Aspose.Words: Możesz zainstalować Aspose.Words dla języka Python za pomocą pip i następującego polecenia:
   
   ```python
   pip install aspose-words
   ```

2. Zaimportuj wymagane moduły: Zaimportuj niezbędne moduły do swojego skryptu Pythona:
   
   ```python
   import asposewords
   ```

## Ładowanie i dostęp do dokumentów

Przed dodaniem lub zweryfikowaniem podpisów cyfrowych należy załadować dokument za pomocą Aspose.Words:

```python
document = asposewords.Document("document.docx")
```

## Dodawanie podpisów cyfrowych do dokumentów

Aby dodać podpis cyfrowy do dokumentu, potrzebny jest certyfikat cyfrowy:

```python
certificate = asposewords.Certificate("certificate.pfx", "password")
```

Teraz podpisz dokument:

```python
digital_signature = asposewords.DigitalSignature()
digital_signature.certificate = certificate
document.digital_signatures.add(digital_signature)
document.save("signed_document.docx")
```

## Weryfikacja podpisów cyfrowych

Sprawdź autentyczność podpisanego dokumentu za pomocą Aspose.Words:

```python
for signature in document.digital_signatures:
    if signature.is_valid:
        print("Signature is valid.")
    else:
        print("Signature is invalid.")
```

## Usuwanie podpisów cyfrowych

Aby usunąć podpis cyfrowy z dokumentu:

```python
document.digital_signatures.clear()
document.save("unsigned_document.docx")
```

## Zapewnienie autentyczności dokumentów

Podpisy cyfrowe zapewniają autentyczność dokumentu poprzez potwierdzenie źródła i integralności dokumentu. Chronią przed manipulacją i nieautoryzowanymi modyfikacjami.

## Dostosowywanie wyglądu podpisu cyfrowego

Możesz dostosować wygląd podpisów cyfrowych:

```python
digital_signature.options.comments = "Approved by John Doe"
digital_signature.options.sign_date_time = datetime.now()
```

## Wniosek

Zarządzanie podpisami cyfrowymi i zapewnienie autentyczności dokumentów ma kluczowe znaczenie w dzisiejszym cyfrowym krajobrazie. Aspose.Words for Python upraszcza proces dodawania, weryfikowania i dostosowywania podpisów cyfrowych, umożliwiając programistom zwiększenie bezpieczeństwa i wiarygodności ich dokumentów.

## Najczęściej zadawane pytania

### Jak działają podpisy cyfrowe?

Podpisy cyfrowe wykorzystują kryptografię do generowania unikalnego skrótu na podstawie zawartości dokumentu, zaszyfrowanego kluczem prywatnym osoby podpisującej.

### Czy można manipulować dokumentem podpisanym cyfrowo?

Nie, ingerencja w cyfrowo podpisany dokument spowoduje unieważnienie podpisu, co może oznaczać możliwość nieautoryzowanych zmian.

### Czy do jednego dokumentu można dodać wiele podpisów?

Tak, do jednego dokumentu można dodać wiele podpisów cyfrowych, każdy od innego sygnatariusza.

### Jakie typy certyfikatów są kompatybilne?

Aspose.Words obsługuje certyfikaty X.509, w tym pliki PFX, które są powszechnie stosowane w przypadku podpisów cyfrowych.

### Czy podpisy cyfrowe są ważne pod względem prawnym?

Tak, podpisy cyfrowe są prawnie wiążące w wielu krajach i często uważa się je za równoważne podpisom odręcznym.