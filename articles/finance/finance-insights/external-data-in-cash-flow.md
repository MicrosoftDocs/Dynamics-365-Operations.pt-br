---
title: Usar dados externos em previsões de fluxo de caixa (versão prévia)
description: Este tópico descreve as etapas de configuração que devem ser concluídas para que os dados externos possam ser inseridos ou importados para previsões de fluxo de caixa.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 03318eaae0b3329dc758c48202f8f47ca2c4ab08
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245559"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Usar dados externos em previsões de fluxo de caixa (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa. Este tópico descreve as etapas de configuração específicas ao uso de dados externos e que permitem que os dados externos sejam incluídos em uma previsão de fluxo de caixa.

## <a name="external-data-setup"></a>Dados mestres externos

Use a guia **Fonte externa** na página **Configuração de previsão de fluxo de caixa** (**Gerenciamento de caixa e de banco \> Previsão de fluxo de caixa**) para inserir configurações que suportam o uso de dados externos em previsões de fluxo de caixa.

Para obter mais informações sobre a configuração, consulte [Previsão de fluxo de caixa](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

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

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]