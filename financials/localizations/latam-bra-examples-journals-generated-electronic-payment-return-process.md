---
title: "Exemplos - diários gerados durante o processo de pagamento eletrônico para O Brasil"
description: "Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos. Linhas aprovadas de pagamento no arquivo de retorno podem ser lançadas alguém a um diário ou a diários de varejo."
author: ShylaThompson
manager: AnnBe
ms.date: 2017-02-03 16 - 41 - 43
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269174
ms.assetid: 41afdcbd-d53f-4034-a664-1e859195b672
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: a8ec7a2bdb0efe79cab21c2493ef9397bdb6a2b8
ms.lasthandoff: 03/31/2017


---

# <a name="examples----journals-generated-during-the-electronic-payment-return-process-for-brazil"></a>Exemplos - diários gerados durante o processo de pagamento eletrônico para O Brasil

Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos. Linhas aprovadas de pagamento no arquivo de retorno podem ser lançadas alguém a um diário ou a diários de varejo.

É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco. Primeiro, você gera e eletrônicos enviar arquivos de remessa para o banco. Em, depois que o banco processa arquivos exportados, você importa um arquivo de retorno do banco. O arquivo de retorno contém informações sobre a aceitação de uma nota fiscal, com o número de pagamento que é fornecido pelo banco, ou informações sobre os pagamentos recebidos de um cliente ou pago a um fornecedor. Quando você importa um arquivo de retorno, o status de pagamento é atualizado ** status de pagamento no campo ** ** transferências de pagamento ** na página. O novo status depende o relacionamento entre os códigos de ocorrência de devolução de banco no arquivo de retorno e códigos de devolução de ocorrência no Microsoft Dynamics 365 para as operações. Ao lançar pagamentos que o arquivo de retorno for importado para, somente pagamentos que possui o status aprovado ** ** são lançados. Esses pagamentos podem ser lançados alguém os mesmos diários de pagamento de diário ou do múltiplo de pagamento.

## <a name="approved-payment-lines-that-are-posted-to-the-same-payment-journal"></a>Linhas aprovadas de pagamento lançadas em um diário de pagamento
É possível lançar todas as linhas de pagamento aprovadas que pertencem ao mesmo nome de diário em um diário de pagamento. Por exemplo, você importa um arquivo de devolução que contém seis linhas de pagamento. Três linhas de pagamento tiverem um status de aprovado ** **, e três linhas de pagamento tiverem um status de rejeitadas ** **. Duas das linhas de pagamento aprovadas para os números de diário 001 e 002, pertencem ao mesmo nome de diário, DP. A terceira aprovada linha de pagamento, para o diário pertence número 100, o nome do teste. A tabela a seguir contém informações sobre as linhas de pagamento no arquivo de devolução.

| Nome do diário | Número do diário | Linha de pagamento | Status   | Valor |
|--------------|----------------|--------------|----------|--------|
| DP           | 001            | 1            | Recebido | 1.000  |
| DP           | 001            | 2            | Aprovada | 2.000  |
| Testar         | 100            | 1            | Aprovada | 3.000  |
| Testar         | 100            | 2            | Rejeitada | 4.000  |
| DP           | 002            | 1            | Aprovada | 5.000  |
| DP           | 002            | 2            | Enviada     | 6,000  |

Quando você lança as linhas de pagamento, as duas linhas aprovadas do diário o número 001 e 002 que pertencem ao nome de diário de DP são lançados ao mesmo diário de liquidação, 003. Entretanto aprovada, a linha do diário número 100 que pertence ao nome do teste é lançada na tabela do diário após 101.The de pagamento contém informações sobre os diários de pagamento criadas quando você lança as linhas aprovadas de pagamento.

| Novo número do diário | A partir do número do diário | Linha de pagamento | Status   | Valor |
|--------------------|---------------------|--------------|----------|--------|
| 003                | 001                 | 2            | Aprovada | 2.000  |
|                    | 002                 | 1            | Aprovada | 5.000  |
| 101                | 100                 | 1            | Aprovada | 3.000  |

## <a name="approved-payment-lines-that-are-posted-to-multiple-payment-journals"></a>Linhas aprovadas de pagamento lançadas ao pagamento mais diários
Se a data da transação que é atualizada para as linhas de pagamento são aprovadas para cada linha de pagamento em um arquivo de retorno, linhas de pagamento serão lançadas em diários de pagamento diferentes. Por exemplo, você importa um arquivo de devolução que contém arquivos de pagamento aprovados que possuem três datas de transação diferentes. A tabela a seguir contém informações sobre as três linhas de pagamento aprovadas que possuem datas de transação diferentes.

| Número do diário | Linha de pagamento | Data da transação | Status   | Valor |
|----------------|--------------|------------------|----------|--------|
| 001            | 1            | 5 de janeiro de 2013  | Aprovada | 1.000  |
|                | 2            | 2 de janeiro de 2013  | Recebido | 2.000  |
|                | 3            | 1º de janeiro de 2013  | Aprovada | 3.000  |
|                | 4            | 3 de janeiro de 2013  | Aprovada | 4.000  |

Ao lançar as linhas de pagamento aprovadas, as três linhas de pagamento são lançadas em três diários diferentes. A tabela a seguir contém informações sobre os diários de pagamento criadas quando você lança as linhas aprovadas de pagamento.

| Número do diário | Linha de pagamento | Data da transação | Status   | Valor |
|----------------|--------------|------------------|----------|--------|
| 002            | 1            | 5 de janeiro de 2013  | Aprovada | 1.000  |
| 003            | 1            | 1º de janeiro de 2013  | Aprovada | 3.000  |
| 004            | 1            | 3 de janeiro de 2013  | Aprovada | 4.000  |




