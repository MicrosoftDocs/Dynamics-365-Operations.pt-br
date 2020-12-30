---
title: Melhorar o modelo de previsão (versão preliminar)
description: Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646070"
---
# <a name="improve-the-prediction-model-preview"></a>Melhorar o modelo de previsão (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão. Comece a melhorar seu modelo no espaço de trabalho **Previsões de pagamento de cliente** no Microsoft Dynamics 365 Finance. As etapas de melhoria são concluídas no AI Builder.

## <a name="select-historical-outcomes"></a>Selecionar resultados históricos

Primeiro, selecione um ou mais dos três resultados possíveis para faturas: **No prazo**, **Atrasado** e **Muito atrasado**. Todos os três resultados devem ser selecionados. Se você desmarcar a seleção de qualquer um dos resultados, as faturas serão filtradas do processo de treinamento e a precisão da previsão será reduzida.

[![Confirmação de resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Se a sua organização exigir apenas dois resultados, altere os limites **Atrasado** e **Muito atrasado** para 0 (zero) dias. Dessa forma, você efetivamente recolhe a predição a um estado binário de **No prazo** ou **Atrasado**.

## <a name="select-fields"></a>Selecionar campos

Quando estiver selecionando os campos a serem incluídos no modelo, lembre-se de que a lista inclui todos os campos disponíveis na entidade do Common Data Service mapeada para os dados no Azure Data Lake. Alguns desses campos **não** devem ser selecionados. Os campos que não devem ser selecionados caem em uma das três categorias:

- O campo é necessário para a entidade do Common Data Service, mas não há dados de backup para ele no data lake.
- O campo é uma ID e, portanto, não faz sentido para um recurso de aprendizado de máquina.
- O campo representa informações que não estarão disponíveis durante a previsão.

As seções a seguir mostram os campos disponíveis para as entidades de fatura e de cliente e listam os campos que **não** devem ser selecionados para treinamento. A categoria especificada para cada um desses campos se refere às categorias na lista anterior.
 
### <a name="invoice-common-data-model-entity"></a>Entidade de fatura do Common Data Model

A ilustração a seguir mostra os campos disponíveis para a entidade de fatura.

[![Campos disponíveis para a entidade de fatura](./media/available-fields.png)](./media/available-fields.png)

Os campos a seguir não devem ser selecionados para treinamento:

- **Conta de Fatura** (categoria 2)
- **Está fechada** (categoria 3) – este campo é usado para filtrar faturas para treinamento (fechada) e de previsão (não fechada).
- **Nome** (categoria 1)
- **Id de Origem** (categoria 2)
- **Registro de origem** (categoria 2)
- **Tabela de origem** (categoria 2)

### <a name="customer-common-data-model-entity"></a>Entidade de cliente do Common Data Model

A ilustração a seguir mostra os campos disponíveis para a entidade de cliente.

[![Campos disponíveis para a entidade de cliente](./media/related-entities.png)](./media/related-entities.png)

O campo a seguir não deve ser selecionados para treinamento:

- **Chave Exclusiva de Linha** (categoria 2)

## <a name="filters"></a>Filtros

No momento, os filtros não dão suporte ao cenário Previsão de pagamento do cliente. Portanto, selecione **Ignorar esta etapa** e prossiga para a página de resumo.

[![Modelo de foco com filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
