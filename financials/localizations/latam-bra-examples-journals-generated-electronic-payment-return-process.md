---
title: "Diários gerados durante o processo de devolução de pagamento eletrônico do Brasil"
description: "Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos. As linhas de pagamento aprovadas no arquivo de retorno podem ser lançadas em um diário ou em vários diários."
author: sndray
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 269174
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 010b5b941648633ec6bb0339a06ecdc512bfa9c0
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="journals-generated-during-the-electronic-payment-return-process-for-brazil"></a>Diários gerados durante o processo de devolução de pagamento eletrônico do Brasil

[!include[banner](../includes/banner.md)]


Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos. As linhas de pagamento aprovadas no arquivo de retorno podem ser lançadas em um diário ou em vários diários.

É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco. Primeiro, você gera e envia arquivos de remessa eletrônica para o banco. Depois, após o banco processar os arquivos exportados, é possível importar um arquivo de devolução do banco. O arquivo de devolução contém informações sobre a aceitação de uma fatura, junto com o número de pagamento fornecido pelo banco, ou informações sobre os pagamentos recebidos de um cliente ou pagos a um fornecedor. Ao importar um arquivo de devolução, o status dos pagamentos é atualizado no campo **Status de pagamento** na página **Transferências de pagamento**. O novo status depende do relacionamento entre os códigos de ocorrência de devolução bancária no arquivo de devolução e os códigos de ocorrência no Microsoft Dynamics 365 for Operations. Ao lançar os pagamentos para os quais o arquivo de devolução é importado, somente os pagamentos que possuem um status **Aprovado** são lançados. Esses pagamentos podem ser lançados para o mesmo diário de pagamento ou para vários diários de pagamento.

## <a name="approved-payment-lines-that-are-posted-to-the-same-payment-journal"></a>Linhas de pagamento aprovadas que são lançadas no mesmo diário de pagamento
É possível lançar todas as linhas de pagamento aprovadas que pertencem ao mesmo nome de diário em um diário de pagamento. Por exemplo, você importa um arquivo de devolução que contém seis linhas de pagamento. Três linhas de pagamento têm o status **Aprovado** e três têm o status **Rejeitado**. Duas das linhas de pagamento aprovadas para os números de diário 001 e 002, pertencem ao mesmo nome de diário, DP. A terceira linha de pagamento aprovada para o número de diário 100, pertence ao nome do diário Teste. A tabela a seguir contém informações sobre as linhas de pagamento no arquivo de devolução.

| Nome do diário | Número do diário | Linha de pagamento | Status   | Valor |
|--------------|----------------|--------------|----------|--------|
| DP           | 001            | 1            | Recebido | 1.000  |
| DP           | 001            | 2            | Aprovada | 2.000  |
| Testar         | 100            | 1            | Aprovada | 3.000  |
| Testar         | 100            | 2            | Rejeitada | 4.000  |
| DP           | 002            | 1            | Aprovada | 5.000  |
| DP           | 002            | 2            | Enviada     | 6,000  |

Quando você lança as linhas de pagamento, as duas linhas aprovadas do diário números 001 e 002 que pertencem ao nome de diário de DP são lançadas no mesmo diário de liquidação, 003. Entretanto, a linha de pagamento aprovada para o diário número 100 que pertence ao nome do teste é lançada no diário de pagamento 101. A tabela a seguir contém informações sobre os diários de pagamento que são criados quando você lança as linhas de pagamento aprovadas.

| Novo número do diário | A partir do número do diário | Linha de pagamento | Status   | Valor |
|--------------------|---------------------|--------------|----------|--------|
| 003                | 001                 | 2            | Aprovada | 2.000  |
|                    | 002                 | 1            | Aprovada | 5.000  |
| 101                | 100                 | 1            | Aprovada | 3.000  |

## <a name="approved-payment-lines-that-are-posted-to-multiple-payment-journals"></a>Linhas de pagamento aprovadas que são lançadas em vários diários de pagamento
Se a data da transação que é atualizada para as linhas de pagamento aprovadas for diferente de cada linha de pagamento em um arquivo de devolução, as linhas de pagamento serão lançadas em diários de pagamento diferentes. Por exemplo, você importa um arquivo de devolução que contém arquivos de pagamento aprovados que possuem três datas de transação diferentes. A tabela a seguir contém informações sobre as três linhas de pagamento aprovadas que possuem datas de transação diferentes.

| Número do diário | Linha de pagamento | Data da transação | Status   | Valor |
|----------------|--------------|------------------|----------|--------|
| 001            | 1            | 5 de janeiro, 2013  | Aprovada | 1.000  |
|                | 2            | 2 de janeiro, 2013  | Recebido | 2.000  |
|                | 3            | 1 de janeiro, 2013  | Aprovada | 3.000  |
|                | 4            | 3 de janeiro, 2013  | Aprovada | 4.000  |

Ao lançar as linhas de pagamento aprovadas, as três linhas de pagamento são lançadas em três diários diferentes. A tabela a seguir contém informações sobre os diários de pagamento que são criados quando você lança as linhas de pagamento aprovadas.

| Número do diário | Linha de pagamento | Data da transação | Status   | Valor |
|----------------|--------------|------------------|----------|--------|
| 002            | 1            | 5 de janeiro, 2013  | Aprovada | 1.000  |
| 003            | 1            | 1 de janeiro, 2013  | Aprovada | 3.000  |
| 004            | 1            | 3 de janeiro, 2013  | Aprovada | 4.000  |






