---
title: Notas fiscais referenciadas para o Brasil
description: "Este tópico fornece uma visão geral de notas fiscais referenciadas usadas no Brasil."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FiscalDocument_BR, SalesEditLines, TmpFiscalReference_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 270224
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fe60c59392b6b053289f73be74b10b3b6fa65248
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="referenced-fiscal-documents-for-brazil"></a>Notas fiscais referenciadas para o Brasil

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral de notas fiscais referenciadas usadas no Brasil.

Em algumas situações, uma nota fiscal deve incluir informações de outra nota fiscal. Você pode anexar informações para uma nota fiscal referenciada de duas maneiras:

-   **Manual** – registre informações relacionadas quando a nota fiscal não estiver disponível. Todas as informações necessárias e a validação garantem que as informações atendem a requisitos fiscais.
-   **Automático** – selecione uma nota fiscal disponível.

### <a name="examples"></a>Exemplos

-   Caso tente fazer referência a uma nota fiscal que não esteja no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, todas as informações da nota fiscal deverão ser inseridas.
-   Quando você devolver um item a um fornecedor ou receber uma devolução de um cliente, uma referência ao documento original será adicionada.
-   Insira uma nota fiscal manual, modelo 01, no sistema. Você cria uma nota fiscal que faz referência à nota fiscal original.
-   Informe uma Ordem de Venda para Vendas de Varejo ou NF-e (modelo 55). A nota fiscal fará referência à nota fiscal de varejo original e à impressora fiscal.
-   Criar e lançar uma ordem de venda e lançar a fatura. Em seguida, crie uma ordem de devolução que faz referência à ordem anterior. O documento fiscal de devolução criará uma nota fiscal que faz referência à nota fiscal original.

## <a name="manual"></a>Manual
Quando uma nota fiscal não estiver disponível, você poderá anexar notas fiscais de cliente ou fornecedor como referências fiscais para uma nota fiscal. Também é possível exibir as referências fiscais associadas à nota fiscal lançada.

### <a name="fiscal-reference"></a>Referência fiscal

| Campo          | descrição                                                                                                                                                                                                                                             |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modelo do documento | O modelo de documento da nota fiscal. Se a opção **É para NF-e (federal)** for selecionada para o modelo do documento na página **Modelo de documento**, o campo **Chave de acesso** fica disponível e os campos **Número** e **Série** ficam indisponíveis. |
| Chave de acesso     | A chave de acesso da nota fiscal eletrônica (NF-e).                                                                                                                                                                                               |
| Número         | O número de identificação da nota fiscal.                                                                                                                                                                                                       |
| Série         | O número de série da nota fiscal.                                                                                                                                                                                                               |
| Data           | A data do documento da nota fiscal.                                                                                                                                                                                                               |
| Direção      | Selecione se a nota fiscal está relacionada a produtos ou serviços de entrada ou saída.                                                                                                                                                             |
| Emissor         | Selecione se a nota fiscal foi emitida pelo estabelecimento fiscal ou por um terceiro.                                                                                                                                                             |
| Tipo de conta   | Selecione **Cliente**, **Fornecedor** ou **Estabelecimento fiscal** como o tipo de conta.                                                                                                                                                                    |
| Conta        | Selecione a conta do cliente, a conta do fornecedor ou o estabelecimento fiscal que gerou a nota fiscal.                                                                                                                                                |
| ID do texto        | Selecione o texto de origem da nota fiscal para a nota fiscal mencionada.                                                                                                                                                                              |

## <a name="automatic"></a>Automático
Use o botão **Referência fiscal** para anexar o cliente, fornecedor ou notas fiscais de transferência existentes como referências fiscais para uma nota fiscal. Você pode fazer referência apenas às notas fiscais lançadas que são emitidas ou recebidas pelo mesmo estabelecimento fiscal que emite ou recebe a nota fiscal que será lançada. Também é possível exibir as referências fiscais associadas à nota fiscal lançada.

### <a name="fiscal-document"></a>Nota fiscal

| Campo         | descrição                                                                                                                                                           |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Número        | O número da nota fiscal do cliente, fornecedor, ou da nota fiscal de transferência.                                                                                      |
| Série        | O número de série da nota fiscal do cliente, fornecedor ou de transferência.                                                                                               |
| Data do documento | A data na qual a nota fiscal do cliente, fornecedor ou de transferência foi emitida.                                                                                           |
| Conta       | O número de identificação do cliente, fornecedor ou do estabelecimento fiscal.                                                                                           |
| Tipo de conta  | O tipo de conta. As opções são **Cliente**, **Fornecedor** ou **Estabelecimento fiscal**.                                                                           |
| Nome          | O nome do cliente, fornecedor ou estabelecimento fiscal.                                                                                                            |
| CNPJ      | O número de registro de contribuinte, ou Cadastro Nacional da Pessoa Jurídica (CNPJ)/Cadastro de Pessoas Físicas (CPF), do cliente, fornecedor ou do estabelecimento fiscal. |
| IE            | O número de registro estadual, ou Inscrição Estadual (IE), do cliente, fornecedor ou estabelecimento fiscal.                                                          |

### <a name="fiscal-reference-placeholders"></a>Espaços reservados de referência fiscal

Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Quando você criar um texto de origem do documento fiscal na página **Modelos de textos da nota fiscal**, você pode incluir espaços reservados no campo **ID do Texto**. Você também pode incluir espaços reservados no campo **Observação** quando associar um texto da nota fiscal para uma ordem de venda, ordem de compra ou fatura de texto livre. Quando você lança uma ordem de venda, ordem de compra ou fatura de texto livre que tem um texto de nota fiscal que inclui espaços reservados, os espaços reservados são substituídos pelos valores nas marcas predefinidas. A tabela a seguir descreve as marcas predefinidas que têm suporte para textos de nota fiscal para referências fiscais.

| Etiqueta                                   | descrição                                                                   |
|---------------------------------------|-------------------------------------------------------------------------------|
| %FiscalRef\_InvNoRef                  | O número da fatura de referência.                                          |
| %FiscalRef\_InvSeriesRef              | O número de série da fatura de referência.                                   |
| %FiscalRef\_InvDateRef                | A data da fatura de referência.                                            |
| %FiscalRef\_InvAccNameRef             | O nome da conta da fatura de referência.                                   |
| %FiscalRef\_InvAccAddressRef          | O endereço da fatura de referência.                                        |
| %FiscalRef\_InvAccIENumberRef         | O número de inscrição estadual (IE) da conta da fatura de referência.          |
| %FiscalRef\_InvAccCNPJCPFNumRef       | O número de registro do contribuinte (CNPJ/CPF) da conta da fatura de referência. |
| %FiscalRef\_FiscalPrinterSerialNumber | O número de série da impressora fiscal.                                      |
| %FiscalRef\_ECFNumber                 | O número de impressora fiscal na fábrica.                                |






