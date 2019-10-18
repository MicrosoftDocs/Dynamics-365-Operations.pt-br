---
title: Estratégia do agente de resolução para configuração de produto
description: Este tópico descreve como você pode usar a estratégia do agente de resolução para melhorar o desempenho da configuração de produto.
author: cvocph
manager: AnnBe
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a548d3536bbc0056ee22c07c464af062029da81
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250567"
---
# <a name="solver-strategy-for-product-configuration"></a>Estratégia do agente de resolução para configuração de produto

[!include [banner](../includes/banner.md)]

Este tópico descreve como você pode usar a estratégia do agente de resolução para melhorar o desempenho da configuração de produto.

O conceito de estratégias do agente de resolução foi apresentado pela primeira vez na atualização cumulativa 7 (CU7) do Microsoft Dynamics AX 2012 R2. Foi estendido na atualização cumulativa 8 (CU8) do Microsoft Dynamics AX 2012 R3 e do Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.

O conceito de estratégia do agente de resolução agora consiste nas seguintes estratégias:

- Padrão
- Domínios mínimos primeiro
- De cima para baixo
- Z3

## <a name="solver-strategy"></a>Estratégia do agente de resolução 

Um modelo de configuração de produto pode ser formulado como um [problema de satisfação de restrição (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf). O Microsoft Solver Foundation (MSF) fornece dois tipos de estratégias do agente de resolução para resolver os CSPs que podem ser usados de modelos de configuração de produto. Essas estratégias do agente de resolução dependem da [heurística](https://techterms.com/definition/heuristic), usada para determinar a ordem na qual as variáveis dos CSPs são consideradas quando o problema está sendo resolvido. A heurística pode afetar significativamente o desempenho quando um problema ou uma classe de problemas estiverem sendo resolvidos.

A estratégia do agente de resolução para modelos de configuração de produto determina qual agente de resolução é usado com a heurística. As estratégias **Padrão**, **Domínios mínimos primeiro** e **De cima para baixo** usam os dois agentes de resolução do MSF, enquanto a estratégia **Z3** usa o agente de resolução Z3. 

Estudos reais de implementação do cliente mostraram que uma alteração na estratégia do agente de resolução para um modelo de configuração de produto pode reduzir o tempo de resposta de minutos para milissegundos. Portanto, vale a pena testar diferentes estratégias do agente de resolução para encontrar a mais eficiente para o seu modelo de configuração de produto.

## <a name="change-the-settings-for-the-solver-strategy"></a>Alterar as configurações da estratégia do agente de resolução

Para alterar a estratégia do agente de resolução, na página **Modelos de configuração de produto**, no Painel de Ação, selecione **Propriedades do modelo**. Em seguida, na caixa de diálogo **Editar os detalhes do modelo**, selecione uma estratégia do agente de resolução.

[![Alterando a estratégia do agente de resolução](./media/solver-strategy.png)](./media/solver-strategy.png)

Atualmente, não há uma lógica que detecte automaticamente qual estratégia do agente de resolução será a mais eficiente para a configuração de produto com base em restrições. Portanto, você deve testar as estratégias do agente de resolução uma a uma.

A tabela a seguir fornece recomendações sobre qual estratégia do agente de resolução usar em vários cenários.

| Estratégia do agente de resolução      | Use a estratégia neste cenário |
|----------------------|-----------------------------------|
| Padrão              | A estratégia **Padrão** foi otimizada para resolver modelos que dependem de restrições de tabela. Estudos de implementação do cliente mostraram que essa estratégia é a mais eficiente em cenários em que as restrições de tabela são usadas extensivamente. |
| Domínios mínimos primeiro | As estratégias **Domínios mínimos primeiro** e **De cima para baixo** estão estreitamente relacionadas. Estudos de implementação do cliente mostraram que a estratégia **De cima para baixo**, tem um desempenho melhor do que a estratégia **Domínios mínimos primeiro**. No entanto, a estratégia **Domínios mínimos primeiro** é mantida no produto para compatibilidade com versões anteriores. Essas duas estratégias do agente de resolução mostraram-se mais eficientes na resolução de modelos que contêm várias expressões aritméticas onde nenhuma restrição de tabela é usada. No entanto, em alguns casos, a estratégia **Padrão** tem um desempenho melhor do que essas duas estratégias. Portanto, lembre-se de testar cada estratégia. |
| De cima para baixo             | As estratégias **Domínios mínimos primeiro** e **De cima para baixo** estão estreitamente relacionadas. Estudos de implementação do cliente mostraram que a estratégia **De cima para baixo**, tem um desempenho melhor do que a estratégia **Domínios mínimos primeiro**. No entanto, a estratégia **Domínios mínimos primeiro** é mantida no produto para compatibilidade com versões anteriores. Essas duas estratégias do agente de resolução mostraram-se mais eficientes na resolução de modelos que contêm várias expressões aritméticas onde nenhuma restrição de tabela é usada. No entanto, em alguns casos, a estratégia **Padrão** tem um desempenho melhor do que essas duas estratégias. Portanto, lembre-se de testar cada estratégia. |
| Z3                   | Recomendamos o uso da estratégia **Z3** como a estratégia do agente de resolução padrão. Se estiver preocupado com o desempenho e a escalabilidade, você pode avaliar as outras estratégias. |

## <a name="additional-resources"></a>Recursos adicionais

[Criar modelo de configuração de produto](build-product-configuration-model.md)

[Heurística](https://techterms.com/definition/heuristic)

[Problema de satisfação de restrição](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)
