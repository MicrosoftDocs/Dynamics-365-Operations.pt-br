---
title: Visão geral de processos automatizados de faturas de fornecedor
description: Este artigo descreve o recurso para automatizar o processamento de faturas de fornecedores e os benefícios do uso de um processo automatizado.
author: abruer
ms.date: 02/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d2c629ed2d064a3350ec8ffe53940098d12ab0b5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883435"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Visão geral de processos automatizados de faturas de fornecedor

[!include [banner](../includes/banner.md)]

Este artigo descreve o recurso para automatizar o processamento de faturas de fornecedores e os benefícios do uso de um processo automatizado. Esse recurso consiste em recursos ativados no Gerenciamento de recursos. Esses recursos se aplicam somente a faturas de fornecedor, não a faturas que são processadas usando a página **Diário de fatura** ou **Diário de registro de fatura**.

Com frequência, as organizações trabalham com terceiros para processar faturas em papel usando um provedor de serviços de reconhecimento óptico de caracteres (OCR). O provedor de serviços retorna metadados da fatura legíveis para computadores. Para ajudar na automação, os recursos de automação de Contas a pagar permitem que você consuma esses artefatos de Contas a pagar.

É possível automatizar alguns processos de faturamento de fornecedor de Contas a pagar. Esses processos incluem enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliar linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes. O processo automatizado mostra informações sobre o andamento de uma fatura de fornecedor quando ele passa por cada um dos processos. Esse recurso pode ajudar os funcionários e gerentes de Contas a pagar a processar as faturas de fornecedor com mais eficiência. Isso também ajuda a reduzir os erros e as ineficiências que podem ocorrer quando as informações são inseridas e processadas manualmente.

Os processos de automação podem ser usados para executar estas tarefas:

- Aplicar automaticamente os pagamentos antecipados para faturas de fornecedores
- Enviar automaticamente faturas importadas para o sistema de fluxo de trabalho.
- Conciliar recebimentos de produtos a linhas da fatura de fornecedor pendentes.
- Simular o lançamento antes que uma fatura de fornecedor seja lançada.
- Exiba de forma rápida e eficiente o histórico de automação do fluxo de trabalho.
- Exiba e analise os resultados da automação do processamento de faturas de fornecedores.
- Retomar o processamento automatizado para várias faturas.

## <a name="submit-imported-vendor-invoices-to-the-workflow-system"></a>Enviar faturas do fornecedor importadas para o sistema de fluxo de trabalho

Como parte de um processo de faturamento de Contas a pagar, uma fatura importada pode ser enviada automaticamente para o sistema de fluxo de trabalho. O processo será executado em segundo plano, na frequência especificada por você (por hora ou por dia). A capacidade de enviar automaticamente faturas importadas para o sistema de fluxo de trabalho requer que seu processo comece com uma fatura importada. Para garantir que a fatura possa ser processada do início ao fim sem intervenção manual, uma tarefa de lançamento automatizada deve ser incluída na configuração do fluxo de trabalho.


As faturas relacionadas a ordens de compra (POs) e faturas que contêm uma categoria de compras não-OC e linhas não estocadas podem ser automaticamente enviadas para o sistema de fluxo de trabalho. As faturas inseridas manualmente e as faturas criadas usando o espaço de trabalho **Faturamento de colaboração do fornecedor** devem ser enviadas manualmente para o sistema de fluxo de trabalho. O processamento do aplicativo de pagamento antecipado deve ser executado manualmente para faturas importadas. Você pode aplicar manualmente pagamentos antecipados antes ou depois do lançamento da fatura importada. Você pode aplicar manualmente pagamentos antecipados a faturas padrão não lançadas usando a página **Faturas do fornecedor**. Após o lançamento, o pagamento antecipado liquidado estará disponível para ser aplicado manualmente a outras notas fiscais deste fornecedor na página **Fornecedores** (**Contas a pagar \> Comum \> Fornecedores \> Todos os fornecedores \> guia Fatura \> Aplicar**).

O recurso de automação fornece uma estrutura flexível que permite definir regras específicas da empresa para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliar linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes.

## <a name="match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Conciliar recebimentos de produtos lançados para linhas da fatura que têm uma política de conciliação tripla

Os recebimentos de produtos lançados podem ser correspondidos automaticamente às linhas de fatura para as quais uma política de conciliação tripla é definida. O processo será executado até que a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura. Como parte desse processo, você pode especificar o número máximo de vezes que o sistema deve tentar conciliar os recebimentos de produtos em uma linha da fatura antes de concluir que o processo falhou. O processo será executado em segundo plano, tanto por hora quanto por dia. Você pode executar o processo de correspondência automatizado como parte do processo de envio de faturas para o sistema de fluxo de trabalho. Como alternativa, você pode executá-lo como um processo autônomo.

## <a name="pre-validate-vendor-invoice-posting"></a>Pré-validar lançamento de fatura de fornecedor

A simulação de lançamento completa as etapas de validação feitas durante o processo de lançamento para faturas de fornecedor, mas nenhuma conta é atualizada. Para executar o processo, você pode selecionar uma única fatura ou várias faturas na página **Faturas de fornecedor pendentes**.

## <a name="enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>Experiência avançada para exibir informações históricas do fluxo de trabalho e de automação para faturas de fornecedor

É fornecida uma exibição de fácil leitura do histórico do fluxo de trabalho da fatura do fornecedor. O histórico do fluxo de trabalho da fatura do fornecedor pode ser acessado diretamente da fatura do fornecedor. Portanto, são necessários menos cliques para encontrar essas informações. Se a sua organização tiver ativado a capacidade de enviar automaticamente faturas de fornecedor importadas para o fluxo de trabalho, o histórico de automação será fornecido para as faturas importadas. O histórico de automação ajuda a identificar a etapa do processo atual, bem como as etapas que já foram concluídas. Quando uma etapa não for bem-sucedida, informações detalhadas serão fornecidas para ajudar você a entender o motivo da falha.

## <a name="analytics-and-metrics"></a>Análise e métrica

O espaço de trabalho **Entrada da fatura de fornecedor** permite que você se concentre nas faturas de fornecedor que não tiveram êxito no processo automatizado. Os blocos no espaço de trabalho listam informações sobre faturas de fornecedor que não foram enviadas com êxito para o sistema de fluxo, importadas ou conciliadas com recebimentos de produtos. As métricas do Microsoft Power BI também são fornecidas para oferecer aos gerentes de Contas a pagar informações sobre a eficiência da automação de faturas de fornecedores.


## <a name="resume-automation-processing-for-multiple-invoices"></a>Retomar o processamento para várias faturas

Quando uma fatura importada não for enviada com êxito para o fluxo de trabalho usando o processo automatizado, o sistema a removerá do processamento automatizado adicional. Um auxiliar de contas a pagar pode revisar e editar a fatura antes que o processo automatizado a reenvie para o fluxo de trabalho. Quando uma razão de falha pode ser resolvida pela mesma correção para várias faturas, você pode reiniciar o processo automatizado na página **Retomar o processamento automatizado para várias faturas**. 

## <a name="tracking-the-invoice-received-date-value"></a>Rastreamento do valor de Data de recebimento da fatura

O valor de **Data de recebimento da fatura** indica a data em que a empresa recebeu a fatura do fornecedor. Ele fornece um ponto de partida para rastrear o progresso da fatura por meio dos processos de automação. Esse valor pode ser incluído nos dados importados de uma fatura de fornecedor. Para faturas criadas manualmente, você pode especificar a data. Se nenhum valor for inserido, a data atual será usada por padrão.


## <a name="tracking-the-imported-invoice-amount-and-imported-sales-tax-amount-values"></a>Rastrear o valor da fatura importado e os valores de imposto importados

Os valores de **Valor da fatura importado** e **Valor de imposto importado** para faturas de fornecedor podem ser fornecidos no arquivo de importação de faturas do fornecedor. Normalmente, esses valores são de uma fatura digitalizada por um fornecedor externo e incluídos no arquivo de importação. Como a fatura é processada em Contas a pagar, os valores serão calculados com base nos dados da fatura. A fatura só poderá ser lançada se os valores importados corresponderem aos valores calculados. Valores de correspondência garantem que a fatura reflita precisamente o valor devido ao fornecedor. Se a sua organização permite que as faturas importadas sejam enviadas para o sistema de fluxo de trabalho automaticamente, você pode exigir que os totais importados correspondam aos totais calculados antes que a fatura possa ser enviada para o sistema de fluxo de trabalho.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Automação de faturas de fornecedores-retomar processamento de automação para várias faturas
Quando uma fatura importada não for enviada com sucesso para o fluxo de trabalho por meio do processo automatizado, ela será removida de outros processamentos automatizados. Um auxiliar de contas a pagar pode revisar e editar a fatura antes que o processo automatizado a reenvie para o fluxo de trabalho. Quando uma razão de falha pode ser resolvida pela mesma correção para várias faturas, você pode reiniciar o processo automatizado na página **Retomar o processamento automatizado para várias faturas**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
