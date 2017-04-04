---
title: Notas fiscais referenciadas para O Brasil
description: "Este tópico fornece uma visão geral de notas fiscais referenciadas usados em O Brasil."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FiscalDocument_BR, SalesEditLines, TmpFiscalReference_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 270224
ms.assetid: 4ffb4fd8-2eb0-430e-b601-013a31c0d188
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 18585f2d38ca6dcd639708ee00d089a62478d9ff
ms.lasthandoff: 03/31/2017


---

# <a name="referenced-fiscal-documents-for-brazil"></a>Notas fiscais referenciadas para O Brasil

Este tópico fornece uma visão geral de notas fiscais referenciadas usados em O Brasil.

Em algumas situações, um documento fiscal deve incluir informações de outro documento fiscal. Você pode anexar informações para um documento fiscal referenciado de duas maneiras:

-   ** Manual ** – registrar informações relacionadas à nota fiscal não estará disponível. Todas as informações, é necessária a validação e garante informações que atendem a requisitos fiscais.
-   ** Automático ** – selecione um documento fiscal disponível.

### <a name="examples"></a>Exemplos

-   Se você tentar fazer referência a uma nota fiscal que não esteja no Microsoft Dynamics 365 para operações, as informações de documento deve ser inserida.
-   Quando você devolver um item a um fornecedor ou receber a devolução de um cliente, referência ao documento original será adicionada.
-   Insira um documento fiscal manual, modelo 01, o sistema. Você cria uma nota fiscal que um documento refere fiscal original.
-   Informe uma ordem de venda para vendas de varejo ou modelo NF-e (55). O documento fiscal fará referência do documento original e a impressora fiscal.
-   Crie uma ordem de venda, e lançar a nota fiscal. Crie uma ordem de devolução que o ordem refere anterior. A nota fiscal de devolução criará fiscal que um documento refere fiscal o documento original.

## <a name="manual"></a>Manual
Quando uma nota fiscal não estiver disponível, você pode anexar notas fiscais de cliente ou fornecedor como referências fiscais para um documento fiscal. Você também pode exibir as referências fiscais associadas a um documento fiscal lançada.

### <a name="fiscal-reference"></a>Referência fiscal

| Campo          | descrição                                                                                                                                                                                                                                             |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modelo do documento | O modelo de documento para a nota fiscal. ** Se for para o NF-e (federal) ** a opção for marcada para o modelo de documento ** ** modelo de documento na página, ** tecla de acesso ** o campo está disponível, e ** número ** e ** série ** os campos não estão disponíveis. |
| Chave de acesso     | A chave de acesso da nota fiscal eletrônico NF-e ().                                                                                                                                                                                               |
| Número         | A ID de nota fiscal.                                                                                                                                                                                                       |
| Série         | O número de série de documento fiscal.                                                                                                                                                                                                               |
| Data           | A data do documento de nota fiscal.                                                                                                                                                                                                               |
| Direção      | Selecione se a nota fiscal está relacionada a produtos de entrada ou de saída ou serviços.                                                                                                                                                             |
| Emissor         | Selecione se a nota fiscal foi emitido por estabelecimento fiscal ou por terceiros.                                                                                                                                                             |
| Tipo de conta   | Selecione ** ** ** cliente, fornecedor ou, ** ** estabelecimento fiscal ** como o tipo de conta.                                                                                                                                                                    |
| Conta        | Selecione a conta do cliente, conta de fornecedor, ou o estabelecimento fiscal que gerou a nota fiscal.                                                                                                                                                |
| ID do texto        | Selecione o texto fonte fiscal do documento de nota fiscal referenciada.                                                                                                                                                                              |

## <a name="automatic"></a>Automático
Use ** ** em referência fiscal para anexar o cliente existente, fornecedor, ou transferem-se notas fiscais como referências fiscais para um documento fiscal. Você poderá fazer referência apenas as notas fiscais lançadas que são emitidos pelo mesmo ou recebidos estabelecimento fiscal que emite ou receber a nota fiscal que será lançada. Você pode exibir as referências fiscais associadas a um documento fiscal lançada.

### <a name="fiscal-document"></a>Nota fiscal

| Campo         | descrição                                                                                                                                                           |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Número        | O número de documento fiscal de cliente, fornecedor, ou de documento fiscal para transferência.                                                                                      |
| Série        | O número de série do cliente, fornecedor, ou de documento fiscal para transferência.                                                                                               |
| Data do documento | A data em que o cliente, fornecedor, ou o documento fiscal para transferência foram emitidos.                                                                                           |
| Conta       | O número de identificação do cliente, do fornecedor ou, estabelecimento fiscal.                                                                                           |
| Tipo de conta  | O tipo de conta. As opções são ** ** ** cliente, fornecedor ou, ** ** ** estabelecimento fiscal.                                                                           |
| Nome          | O nome do cliente, do fornecedor ou, estabelecimento fiscal.                                                                                                            |
| CNPJ      | O número de registro do contribuinte, ou Cadastro Nacional da Pessoa Jurídica (/Cadastro) CNPJ de Pessoas Físicas (CPF), de cliente, do fornecedor ou, estabelecimento fiscal. |
| IE            | O número de registro do estado, ou Estadual (IE), registro de cliente, do fornecedor ou, estabelecimento fiscal.                                                          |

### <a name="fiscal-reference-placeholders"></a>Espaços reservados de referência fiscal

Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Quando você cria um texto a fonte de documento fiscal ** textos fontes fiscais ** de documento na página, você poderá incluir os espaços reservados de ID ** ** texto no campo. Também é possível incluir espaços reservados em nota ** ** campos quando você anexa um texto de documento fiscal para uma ordem de venda, a ordem de compra, ou uma nota fiscal de texto livre. Quando você lança uma ordem de venda, ordem de compra ou fatura de texto livre que tem um texto de nota fiscal que inclui espaços reservados, os espaços reservados são substituídos pelos valores nas marcas predefinidas. A tabela a seguir descreve etiquetas predefinidos que suportam textos do documento para referências fiscais.

| Etiqueta                                   | descrição                                                                   |
|---------------------------------------|-------------------------------------------------------------------------------|
| %FiscalRef\_InvNoRef                  | O número da fatura de referência.                                          |
| %FiscalRef\_InvSeriesRef              | O número de série da nota fiscal de referência.                                   |
| %FiscalRef\_InvDateRef                | A data da fatura de referência.                                            |
| %FiscalRef\_InvAccNameRef             | O nome da fatura de referência.                                   |
| %FiscalRef\_InvAccAddressRef          | O endereço para a fatura de referência.                                        |
| %FiscalRef\_InvAccIENumberRef         | O número de registro de IE estado () da conta de nota fiscal de referência.          |
| %FiscalRef\_InvAccCNPJCPFNumRef       | O número de registro do contribuinte (CNPJ/CPF) da conta de nota fiscal de referência. |
| %FiscalRef\_FiscalPrinterSerialNumber | O número de série da impressora fiscal.                                      |
| %FiscalRef\_ECFNumber                 | O número de impressora fiscal na fábrica.                                |




