---
title: "Espaços reservados de Texto de nota fiscal para O Brasil"
description: "Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Você poderá incluir os espaços <strong>Texto </strong>reservados do <strong>Textos fontes fiscais de documento </strong>campo na página criar um texto a fonte de documento fiscal."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 268684
ms.assetid: b949485b-6f02-4f4b-9599-d35864c4b574
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 7ee712437711ea58dfa5e1fcc44c1114539e5d64
ms.lasthandoff: 03/31/2017


---

# <a name="fiscal-document-text-placeholders-for-brazil"></a>Espaços reservados de Texto de nota fiscal para O Brasil

Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Você poderá incluir os espaços <strong>Texto </strong>reservados do <strong>Textos fontes fiscais de documento </strong>campo na página criar um texto a fonte de documento fiscal.

Também é possível incluir espaços reservados ** ** no campo nota ** Textos de notas fiscais em ** página quando você anexa um texto de documento fiscal para uma ordem de venda, a ordem de compra, ou uma nota fiscal de texto livre. Quando você lança uma ordem de venda, ordem de compra ou fatura de texto livre que tem um texto de nota fiscal que inclui espaços reservados, os espaços reservados são substituídos pelos valores nas marcas predefinidas.

As tabelas a seguir contêm etiquetas predefinidos que suportam o texto de documento fiscal e o seu valor.
Etiqueta que suportam o texto de documento fiscal para processos referenciados
---------------------------------------------------------------

| Marca predefinida                  | Alíquota                                 |
|---------------------------------|---------------------------------------|
| %RefProcess\_TaxAuthorityName   | O nome da autoridade do imposto.        |
| %RefProcess\_TaxAuthorityAgency | A agência da autoridade do imposto.      |
| %RefProcess\_RefProcessNumber   | O número do processo mencionado. |

## <a name="tag-that-supports-fiscal-document-text-for-suframa"></a>Marque que texto fiscal de documentos de suporte à SUFRAMA
| Marca predefinida       | Alíquota                        |
|----------------------|------------------------------|
| %Suframa\_CustNumber | O número de cliente da SUFRAMA. |

## <a name="tags-that-support-fiscal-document-text-for-taxes"></a>Etiqueta que suportam o texto de documento fiscal de imposto
| Marca predefinida | Alíquota                                                                                    |
|----------------|------------------------------------------------------------------------------------------|
| %ICMS          | O valor do ICMS (Imposto Sobre Circulação de Mercadorias e Serviços).                |
| %PIS           | O valor da contribuição do PIS (Programa de Integração Social).                             |
| %COFINS        | O valor da contribuição de COFINS (Contribuição para Financiamento da Seguridade Social). |

## <a name="tags-that-support-fiscal-document-text-for-fiscal-references"></a>Etiqueta que suportam o texto de documento fiscal para referências fiscais
| Marca predefinida                  | Alíquota                                                                                                               |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------|
| %FiscalRef\_InvNoRef            | O número da fatura de referência.                                                                                |
| %FiscalRef\_InvSeriesRef        | A série da fatura de referência.                                                                                |
| %FiscalRef\_InvDateRef          | A data da fatura de referência.                                                                                  |
| %FiscalRef\_InvAccNameRef       | O nome da conta da fatura de referência.                                                                          |
| %FiscalRef\_InvAccAddressRef    | O endereço da fatura de referência.                                                                               |
| %FiscalRef\_InvAccIENumberRef   | A IE (Inscrição Estadual), ou número de inscrição do estado, da conta de fatura de referência.                        |
| %FiscalRef\_InvAccCNPJCPFNumRef | O CNPJ (Cadastro Nacional da Pessoa Jurídica), ou número de inscrição do contribuinte, da conta de fatura de referência. |

## <a name="tags-that-support-fiscal-document-text-that-involve-vendor-information"></a>Etiqueta que suportam o texto de documento fiscal envolvendo informações de fornecedor
| Marca predefinida     | Alíquota                                                                                                                              |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------|
| nome de %Vendor\_      | O nome do fornecedor.                                                                                                            |
| %Vendor\_\_CNPJ CPF | O CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas), ou número de inscrição do contribuinte, do fornecedor. |
| IE de %Vendor\_        | A IE do fornecedor.                                                                                                              |
| endereço de %Vendor\_   | O endereço do fornecedor.                                                                                                         |

## <a name="tags-that-support-fiscal-document-text-that-involve-customer-information"></a>Etiqueta que suportam o texto de nota fiscal que envolve as informações do cliente
| Marca predefinida       | Alíquota                         |
|----------------------|-------------------------------|
| nome de %Customer\_      | O nome do cliente.     |
| %Customer\_\_CNPJ CPF | O CNPJ/CPF do cliente. |
| IE de %Vendor\_          | A IE do cliente.       |
| endereço de %Vendor\_     | O endereço do cliente.  |

## <a name="tags-that-support-fiscal-document-text-for-withholding-taxes"></a>Etiqueta que suportam o texto de documento fiscal para retenção de imposto
| Marca predefinida       | Alíquota                          |
|----------------------|--------------------------------|
| código de %TaxWithhold\_   | O código de imposto retido na fonte.      |
| valor de %TaxWithhold\_  | A taxa de imposto retido na fonte.   |
| valor de %TaxWithhold\_ | O valor do imposto retido na fonte. |

## <a name="tags-that-support-fiscal-document-text-for-imports"></a>Etiqueta que suportam texto fiscal de documento de importação
| Marca predefinida | Alíquota                                                                    |
|----------------|--------------------------------------------------------------------------|
| Número de %DI\_    | O identificador do documento da declaração de importação.                       |
| Data de %DI\_      | A data que o documento da declaração de importação foi emitido.                |
| %ImportTax     | O valor do imposto sobre importação.                                                   |
| %Freight       | O valor de frete para a importação.                                       |
| %Insurance     | O valor de seguro para a importação.                                     |
| %Siscomex      | O valor de encargo para Siscomex (Sistema Integrado de Comércio Exterior). |
| %ExchRate      | A taxa de câmbio usada na importação.                            |

## <a name="tags-for-icmsdif-final-consumer"></a>Etiqueta para o consumo de ICMSDIF final
| Marca predefinida           | Alíquota                                                                          |
|--------------------------|--------------------------------------------------------------------------------|
| %DifICMS o\_mais vBCUFDest      | Valor da base de imposto usado para o tipo de imposto ICMS-DIF.                                    |
| %DifICMS o\_mais pICMSUFDest    | Valor do imposto do estado federal destinatário.                                         |
| pICMSInter de %DifICMS\_     | Valor do imposto para a transação de um estado para outro.                                          |
| pICMSInterPart de %DifICMS\_ | Porcentagem definida para estado federal destinatário (baseado no ano fiscal de documento). |
| %DifICMS o\_mais vICMSUFDest    | Valor do imposto do estado destinatário.                                                |
| vICMSUFRemet de %DifICMS\_   | Valor do imposto do estado de emissor.                                                   |




