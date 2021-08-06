---
title: Melhorar o modelo de previsão (versão preliminar)
description: Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 376e48a442f5a1b459077fb7a0d52faf974a792f
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638407"
---
# <a name="improve-the-prediction-model-preview"></a>Melhorar o modelo de previsão (versão preliminar)

[!include [banner](../includes/banner.md)]

Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão. Comece a melhorar seu modelo no espaço de trabalho **Previsões de pagamento de cliente** no Microsoft Dynamics 365 Finance. As etapas de melhoria são concluídas no AI Builder.

## <a name="select-historical-outcomes"></a>Selecionar resultados históricos

Primeiro, selecione um ou mais dos três resultados possíveis para faturas: **No prazo**, **Atrasado** e **Muito atrasado**. Todos os três resultados devem ser selecionados. Se você desmarcar a seleção de qualquer um dos resultados, as faturas serão filtradas do processo de treinamento e a precisão da previsão será reduzida.

[![Confirmação de resultados.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Se a sua organização exigir apenas dois resultados, altere os limites **Atrasado** e **Muito atrasado** para 0 (zero) dias. Dessa forma, você efetivamente recolhe a predição a um estado binário de **No prazo** ou **Atrasado**.

## <a name="select-fields"></a>Selecionar campos

Quando estiver selecionando campos a serem incluídos no modelo, lembre-se de que a lista inclui todos os campos disponíveis na tabela do Microsoft Dataverse mapeada para os dados no Azure Data Lake. Alguns desses campos **não** devem ser selecionados. Os campos que não devem ser selecionados caem em uma das três categorias:

- O campo é necessário para a tabela do Dataverse, mas não há dados de backup para ele no data lake.
- O campo é uma ID e, portanto, não faz sentido para um recurso de aprendizado de máquina.
- O campo representa informações que não estarão disponíveis durante a previsão.

As seções a seguir mostram os campos disponíveis para as entidades de fatura e de cliente e listam os campos que **não** devem ser selecionados para treinamento. A categoria especificada para cada um desses campos se refere às categorias na lista anterior.
 
### <a name="invoice-dataverse-table"></a>Tabela de faturas do Dataverse

A ilustração a seguir mostra os campos disponíveis para a tabela de fatura.

[![Campos disponíveis para a tabela de fatura.](./media/available-fields.png)](./media/available-fields.png)

Os campos a seguir não devem ser selecionados para treinamento:

- **Conta de Fatura** (categoria 2)
- **Está fechada** (categoria 3) – este campo é usado para filtrar faturas para treinamento (fechada) e de previsão (não fechada).
- **Nome** (categoria 1)
- **Id de Origem** (categoria 2)
- **Registro de origem** (categoria 2)
- **Tabela de origem** (categoria 2)

### <a name="customer-dataverse-table"></a>Tabela de clientes do Dataverse

A ilustração a seguir mostra os campos disponíveis para a tabela de clientes.

[![Campos disponíveis para a tabela de clientes.](./media/related-entities.png)](./media/related-entities.png)

O campo a seguir não deve ser selecionados para treinamento:

- **Chave Exclusiva de Linha** (categoria 2)

## <a name="filters"></a>Filtros

Você pode filtrar as faturas que são usadas para treinamento, definindo critérios de filtragem para campos na fatura ou nas tabelas do cliente. Por exemplo, você pode definir um limite para incluir somente faturas em que o total seja igual a ou exceda um valor específico. Como alternativa, você pode excluir as faturas associadas a clientes de um grupo de clientes específico.

Para obter mais informações sobre como filtrar os dados, consulte [criar um modelo de previsão](https://docs.microsoft.com/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
