---
title: Usar dados externos em previsões de fluxo de caixa (versão prévia)
description: Este tópico descreve as etapas de configuração que devem ser concluídas para que os dados externos possam ser inseridos ou importados para previsões de fluxo de caixa.
author: rcarlson
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 66bdb8bd638859bb4fc5565e3f12a8f671addcff
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186681"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Usar dados externos em previsões de fluxo de caixa (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa. Este tópico descreve as etapas de configuração específicas ao uso de dados externos e que permitem que os dados externos sejam incluídos em uma previsão de fluxo de caixa.

## <a name="external-data-setup"></a>Dados mestres externos

Use a guia **Fonte externa** na página **Configuração de previsão de fluxo de caixa** (**Gerenciamento de caixa e de banco \> Previsão de fluxo de caixa**) para inserir configurações que suportam o uso de dados externos em previsões de fluxo de caixa.

Para obter mais informações sobre a configuração, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).

Para inserir dados externos para previsões de fluxo de caixa, você pode usar a experiência Abrir no Excel para inserir e modificar dados externos. Selecione o botão **Dados externos** e selecione **Adicionar dados externos** ou **Editar dados externos existentes**. Quando o arquivo do Microsoft Excel é aberto, você pode inserir informações nos seguintes campos:

- **ID da Entrada**
- **Descrição** (opcional)
- **Nome de origem externo** – Selecione um dos valores na lista que você definiu ao configurar o Finance Insights.
- **Entidade legal**
- **Data**
- **Valor na moeda de transação**
- **Código de Moeda**
- **Dimensão padrão** (opcional)
- **Número do documento** (opcional)
- **Número da conta** (opcional)
- **Nome da conta** (opcional)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importar dados externos usando a estrutura de gerenciamento de dados

Você pode importar dados externos para previsões de fluxo de caixa usando o espaço de trabalho **Gerenciamento de dados** e a entidade chamada **Entrada de origem externa de previsão de fluxo de caixa**.

Além disso, se você precisar mover os dados de configuração de um ambiente para outro, as seguintes entidades estão disponíveis para as tabelas de configuração necessárias:

- Configuração da fonte externa de previsão de fluxo de caixa
- Configuração da entidade legal de fonte externa de previsão de fluxo de caixa

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
