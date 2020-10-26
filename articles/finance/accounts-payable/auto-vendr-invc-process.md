---
title: Visão geral de processos automatizados de faturas de fornecedor
description: Este tópico descreve o recurso para automatizar o processamento de faturas de fornecedores e os benefícios do uso de um processo automatizado.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 187b3c4f1a8b2c9ec6df95c19b261756ec4562dc
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "3904997"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Visão geral de processos automatizados de faturas de fornecedor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve o recurso para automatizar o processamento de faturas de fornecedores e os benefícios do uso de um processo automatizado. Esse recurso consiste em recursos ativados no Gerenciamento de recursos. Esses recursos se aplicam somente a faturas de fornecedor, não a faturas que são processadas por meio da página **Diário de fatura** ou **Diário de registro de fatura**.

Com frequência, as organizações trabalham com terceiros para processar faturas em papel usando um provedor de serviços de reconhecimento óptico de caracteres (OCR). O provedor de serviços retorna metadados da fatura legíveis para computadores. Para ajudar na automação, os recursos de automação de Contas a pagar permitem que você consuma esses artefatos de Contas a pagar.

É possível automatizar alguns processos de faturamento de fornecedor de Contas a pagar. Esses processos incluem enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliar linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes. O processo automatizado mostra informações sobre o andamento de uma fatura de fornecedor quando ele passa por cada um dos processos. Esse recurso pode ajudar os funcionários e gerentes de Contas a pagar a processar as faturas de fornecedor com mais eficiência. Isso também ajuda a reduzir os erros e as ineficiências que podem ocorrer quando as informações são inseridas e processadas manualmente.

Os processos de automação podem ser usados para executar estas tarefas:

- Enviar automaticamente faturas importadas para o sistema de fluxo de trabalho.
- Conciliar recebimentos de produtos a linhas da fatura de fornecedor pendentes.
- Simular o lançamento antes que uma fatura de fornecedor seja lançada.
- Exiba de forma rápida e eficiente o histórico do fluxo de trabalho.
- Exiba e analise os resultados da automação do processamento de faturas de fornecedores.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Automação de fatura de fornecedor – envie faturas de fornecedor importadas para o sistema de fluxo de trabalho

Como parte de um processo de faturamento de Contas a pagar, você pode fazer o sistema enviar automaticamente uma fatura importada para o sistema de fluxo de trabalho. O processo será executado em segundo plano, na frequência especificada por você (por hora ou por dia). A capacidade de enviar automaticamente faturas importadas para o sistema de fluxo de trabalho requer que seu processo comece com uma fatura importada. Para garantir que a fatura possa ser processada do início ao fim sem intervenção manual, uma tarefa de lançamento automatizada deve ser incluída na configuração do fluxo de trabalho.

As faturas relacionadas a ordens de compra (OCs) e faturas que contêm uma categoria de compras não OC e linhas que não estejam em estoque podem ser automaticamente enviadas para o sistema de fluxo de trabalho. As faturas inseridas manualmente e as faturas criadas por meio do espaço de trabalho **Faturamento de colaboração do fornecedor** devem ser enviadas manualmente para o sistema de fluxo de trabalho.

O recurso de automação fornece uma estrutura flexível que permite definir regras específicas da empresa para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliar linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Automação de fatura de fornecedor – concilie recebimentos de produtos a linhas de fatura com uma política de conciliação tripla

O sistema pode conciliar automaticamente os recebimentos de produtos lançados com as linhas da fatura para as quais uma política de conciliação tripla é definida. O processo será executado até que a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura. Como parte desse processo, você pode especificar o número máximo de vezes que o sistema deve tentar conciliar os recebimentos de produtos em uma linha da fatura antes de concluir que o processo falhou. O processo será executado em segundo plano, tanto por hora quanto por dia. Você pode executar o processo de correspondência automatizado como parte do processo de envio de faturas para o sistema de fluxo de trabalho. Como alternativa, você pode executá-lo como um processo autônomo.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Automação de fatura de fornecedor – pré-validar o lançamento da fatura de fornecedor

A simulação de lançamento completa as etapas de validação feitas durante o processo de lançamento para faturas de fornecedor, mas nenhuma conta é atualizada. Para executar o processo, você pode selecionar uma única fatura ou várias faturas na página **Faturas de fornecedor pendentes**.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-historical-information-for-vendor-invoices"></a>Automação de fatura de fornecedor – experiência avançada para exibir informações históricas do fluxo de trabalho para faturas de fornecedor

É fornecida uma exibição de fácil leitura do histórico do fluxo de trabalho da fatura do fornecedor. O histórico do fluxo de trabalho da fatura do fornecedor pode ser acessado diretamente da fatura do fornecedor. Portanto, são necessários menos cliques para encontrar essas informações.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Automação de fatura de fornecedor – análises e métricas

O espaço de trabalho **Entrada da fatura de fornecedor** permite que você se concentre nas faturas de fornecedor que não tiveram êxito no processo automatizado. Os blocos no espaço de trabalho listam informações sobre faturas de fornecedor que não foram enviadas com êxito para o sistema de fluxo, importadas ou conciliadas com recebimentos de produtos. As métricas do Microsoft Power BI também são fornecidas para oferecer aos gerentes de Contas a pagar informações sobre a eficiência da automação de faturas de fornecedores.
