---
title: Tipo de severidade do ativo
description: O tópico explica os tipos de severidade de ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7d6e3dea1b3c1ef47490df678f639c036cdd5c
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889808"
---
# <a name="asset-criticality-types"></a>Tipo de severidade do ativo

[!include [banner](../../includes/banner.md)]

 

O tópico explica os tipos de severidade de ativos no Asset Management. A severidade de ativos está relacionada aos ativos e é transferida para as ordens de serviço. Não pode ser alterada em uma ordem de serviço. A severidade de ativos é usada para calcular a severidade da ordem de serviço durante seu agendamento. Em outras palavras, é usada para calcular até onde um trabalho de manutenção em um ativo afeta a agenda de produção e a produtividade da empresa. Para obter mais informações sobre a instalação relacionadas ao cálculo de pontuações de classificação para o agendamento da ordem de serviço, consulte [Parâmetros do Asset Management](../setup-for-objects/enterprise-asset-management-parameters.md).

Para configurar a severidade, primeiro você cria os tipos de severidade que devem ser usados na configuração do ativo. Então, você configura as severidades de ativo.

## <a name="set-up-criticality-types"></a>Configurar tipos de severidade

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Tipos de severidade**.
2. Selecione **Novo** para criar um registro.
3. No campo **Severidade** , insira um número que indique a severidade.
4. No campo **Nome**, insira um nome para o tipo de severidade.
5. No campo **Fator**, insira um fator. Esse fator é usado no cálculo de agendamento da ordem de serviço para determinar o registro de severidade que deve ser usado. (O registro com o fator mais alto será sempre usado). Essa configuração será relevante se, conforme mostrado na ilustração, as linhas de severidade forem criadas com o mesmo valor de severidade.

    ![Página Tipos de severidade](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Configurar severidades de ativo

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Severidades de ativo**.
2. Selecione **Novo** para criar um registro.
3. Dependendo do grau de detalhamento desejado para a severidade do ativo, faça seleções relevantes nos campos **Local funcional**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Categoria do tipo de trabalho**, **Tipo de trabalho**, **Variação do tipo de trabalho** e **Necessidade de trabalho**.

    > [!NOTE]
    > Quando uma severidade de ativo é selecionada, o Asset Management examina todos os registros de severidade de ativo para verificar a existência uma possível correspondência. Ele sempre verifica a combinação mais específica primeiro. Ou seja, o Asset Management primeiro verifica **Necessidade de trabalho**. Se nenhuma correspondência for encontrada, verifica **Variação de tipo de trabalho**. Se nenhuma correspondência for encontrada, verifica **Tipo de trabalho** e assim em diante. Como você pode perceber no layout da página, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência. Se nenhuma correspondência for encontrada, o registro "padrão" que não possui nenhuma seleção é usado.

4. No campo **Severidade**, selecione um dos valores de severidade que você criou no no procedimento anterior.

### <a name="notes-about-criticality-setup"></a>Observações sobre a configuração de severidade

- Se você alterar a severidade de um ativo nessa configuração depois de já tê-la usado em uma ordem de serviço, a severidade da ordem de serviço não será atualizada de forma correspondente.
- A severidade em uma ordem de serviço é recalculada sempre que uma linha da ordem de serviço é adicionada ou excluída.
- Se uma ordem de serviço contiver vários trabalhos de ordem de serviço, a severidade mais alta, de acordo com o campo **Fator** na página **Tipos de severidade**, sempre será usada na ordem de serviço.
- Geralmente, a severidade do ativo pode mudar em um período. A severidade pode ser afetada pela compra de novo equipamento, restaurações e assim em diante. Considere a reavaliação das severidades do seu ativo em intervalos regulares (por exemplo, uma vez por ano em anos alternados) para garantir que as definições de severidade correspondam à sua configuração de produção atual.
