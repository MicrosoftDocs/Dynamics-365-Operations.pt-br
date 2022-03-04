---
title: Dados externos em previsões de fluxo de caixa
description: Este tópico descreve as etapas de configuração que devem ser concluídas para que os dados externos sejam inseridos ou importados para previsões de fluxo de caixa.
author: rcarlson
ms.date: 02/16/2022
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
ms.openlocfilehash: 23342114c25cd1b59d47aa7ce63f09de029fa690
ms.sourcegitcommit: 465c84eb5cdc211692e2ae09b45d1400f9a315ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8314690"
---
# <a name="external-data-in-cash-flow-forecasts"></a>Dados externos em previsões de fluxo de caixa

[!include [banner](../includes/banner.md)]

Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa. Este tópico descreve as etapas de configuração específicas ao uso de dados externos e que permitem que os dados externos sejam incluídos em uma previsão de fluxo de caixa.

## <a name="external-data-setup"></a>Dados mestres externos

Use a guia **Fonte externa** na página **Configuração de previsão de fluxo de caixa** (**Gerenciamento de caixa e de banco \> Previsão de fluxo de caixa \> Configuração da previsão de fluxo de caixa**) para inserir configurações que dão suporte ao uso de dados externos em previsões de fluxo de caixa.

Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa. Antes que os dados externos sejam inseridos ou importados, as origens externas devem ser configuradas. Na guia **Fonte externa**, configure categorias externas de fluxo de caixa. Uma categoria pode ser de **Saída** ou de **Entrada**. A **liquidez** deve ser selecionada como o tipo de lançamento. Na grade **Configurações da entidade legal**, selecione as entidades legais e as contas principais correspondentes às quais as categorias externas de fluxo de caixa se aplicam.

Para obter mais informações sobre como configurar previsões de fluxo de caixa, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Inserir dados externos

Para inserir e modificar dados externos para previsões de fluxo de caixa, você pode usar a experiência **Abrir no Excel**. Selecione o botão **Dados externos** na página do espaço de trabalho **Previsão de fluxo de caixa** e, depois, selecione **Adicionar Dados Externos** ou **Editar dados externos existentes**. Quando o arquivo do Microsoft Excel é aberto, você pode inserir informações nos seguintes campos:

- **ID da Entrada** (exclusivo)
- **Descrição** (opcional)
- **Nome de Origem Externo** – selecione um dos valores na lista que você definiu ao configurar o Finance Insights.
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
