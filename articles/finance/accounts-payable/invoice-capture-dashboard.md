---
title: Painel de solução do Invoice capture
description: Este artigo descreve o painel de soluções do Invoice capture.
author: sunfzam
ms.date: 10/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690108"
---
# <a name="invoice-capture-solution-dashboard"></a>Painel de solução do Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

No Invoice Capture, o painel inclui gráficos que fornecem uma visão geral das faturas que foram importadas. Esses gráficos podem ajudar o gerenciador de Contas a Pagar (AP) a analisar o desempenho do processo de geração de fatura. O Gerenciador de AP pode exibir o status do processo de geração de fatura e, ao aplicar filtros diferentes, também pode exibir detalhes.

## <a name="available-charts"></a>Gráficos disponíveis

Os seguintes gráficos estão disponíveis no painel:

- **Todas as faturas capturadas por status** – este gráfico mostra os status a seguir de uma fatura capturada. Ao selecionar um status, os usuários podem filtrar as faturas capturadas na lista detalhada.

    - Capturado
    - Concluído
    - Em análise
    - Substituído

- **Volume total de fatura captura** – Este gráfico mostra o número de faturas capturadas por período. Os usuários podem alterar o período usando a lista suspensa.
- **Fatura capturada dos principais fornecedores** – Este gráfico mostra o número total de faturas por fornecedor. Os fornecedores que têm mais faturas aparecem na parte superior.
- **Dias para a conclusão por fatura com exceções** – este gráfico mostra o número médio de dias necessários para capturar uma fatura. Essas informações podem ajudar o Gerenciador de AP a analisar o tempo para processar uma fatura quando for necessária intervenção manual. Se houver uma tendência ascendente, os usuários poderão revisar os detalhes do processo e ajustar as configurações para ajudar a reduzir o número de dias necessários.
- **Faturas incompletas por tempo pendente** – este gráfico mostra o número de dias que uma fatura capturada não foi gerada no sistema de planejamento de recursos empresariais (ERP). Quanto maior o número de dias pendentes, mais longo será o processo de geração de fatura. O Gerenciador de AP pode fazer uma busca detalhada nas faturas capturadas detalhadas e gerar faturas no sistema ERP.
