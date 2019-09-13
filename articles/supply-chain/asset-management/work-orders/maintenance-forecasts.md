---
title: Previsões de manutenção
description: Este tópico explica as previsões de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a416bbb79be3f25998d3c0da8d231d0df808685
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875507"
---
# <a name="maintenance-forecasts"></a>Previsões de manutenção

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Quando você cria uma ordem de serviço, você cria trabalhos da ordem de serviço com ativos e tipos de trabalho de manutenção relacionados. Quando você seleciona um tipo de trabalho de manutenção que contém previsões de manutenção, as previsões são copiadas automaticamente para a ordem de serviço.

Você pode adicionar ou excluir linhas de previsão em uma ordem de serviço. A configuração de um estado de ciclo de vida de ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você é capaz de adicionar ou editar linhas de previsão. 

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço na lista e clique em **Previsão**. Na **Previsão de manutenção da ordem de serviço**, são exibidas as linhas de previsão do tipo de trabalho de manutenção selecionadas no trabalho da ordem de serviço.


## <a name="add-hours-forecast-to-a-work-order"></a>Adicione a previsão de horas para uma ordem de serviço

1. Selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma previsão.

2. Na Guia Rápida **Horas**, clique em **Adicionar** para criar uma nova linha.

3. Selecione uma categoria no campo **Categoria**.

4. Insira o número de horas previstas no campo **Horas**.

5. No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.


## <a name="add-items-forecast-to-a-work-order"></a>Adicione a previsão de itens a uma ordem de serviço

Existem três maneiras de adicionar itens a uma previsão de manutenção de ordem de serviço: você pode criar linhas para itens (peças sobressalentes) que não estão incluídas na lista de peças de reposição ou BOM de ativos, é possível selecionar peças sobressalentes da lista de peças de reposição aprovadas e você pode selecionar itens da BOM de ativos.

1. Selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma previsão.

2. Selecione a Guia Rápida **Itens**.

3. Clique em **Adicionar** para criar uma nova linha de uma peça sobressalente que não está na lista de peças sobressalentes ou na lista de BOM de ativos.

4. Selecione o item no campo **Número do item**.

5. Insira a quantidade no campo **Quantidade de venda** e selecione uma unidade de quantidade no campo **Unidade**.

6. Insira o preço de custo estimado e a moeda nos campos relevantes e selecione uma **Propriedade da linha**.

7. Se quiser modificar a lista de dimensões exibidas nas linhas do item, clique em **Estoque** > **Dimensões de exibição**, selecione as dimensões e depois "Sim” no botão de alternância **Salvar configuração**.

8. Se quiser adicionar uma peça sobressalente aprovada à previsão de manutenção, clique em **Adicionar peças sobressalentes**, selecione a peça, edite as informações relacionadas, se necessário, e clique em **OK**.

9. Se quiser adicionar itens da BOM de ativos à previsão, clique em **Adicionar itens da BOM**, selecione o item, edite as informações relacionadas, se necessário, e clique em **OK**.

10. Clique em **Item onde usado** se quiser obter uma visão geral de onde o item é usado na linha selecionada no Gerenciamento de Ativos em relação aos ativos, padrões do tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço. 



## <a name="add-expense-forecast-to-a-work-order"></a>Adicione a previsão de despesa a uma ordem de serviço

1. Este tópico explica como adicionar uma previsão de despesa a uma ordem de serviço. No lado esquerdo do formulário, selecione o trabalho da ordem de serviço no qual você deseja adicionar uma previsão.

2. Selecione a Guia Rápida **Despesas**.

3. Clique em **Adicionar** para criar uma nova linha.

4. Selecione uma categoria no campo **Categoria**.

5. Insira quantidade no campo **Quantidade**.

6. Insira preço de custo, moeda de vendas e preço de venda nos campos relevantes.

7. No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.

>[!NOTE]
>Na Guia Rápida **Totais da previsão de manutenção**, você poderá ver uma visão geral do número de linhas criadas em cada guia, para o trabalho da ordem de serviço e para a ordem de serviço. Além disso, você poderá ver uma soma de horas de trabalho esperadas para o trabalho da ordem de serviço e para a ordem de serviço.

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Atualização automática de previsões de ordem de serviço

No Gerenciamento de Ativos, você pode atualizar todas as alterações nas previsões da ordem de serviço referentes aos custos da hora, custos do item e despesas, que foram atualizadas em outros módulos no Dynamics 365 for Finance and Operations. Isso é feito para garantir que os preços de custo mais recentes sejam sempre usados nas previsões de ordem de serviço. Também é possível fazer atualizações semelhantes para [previsões do tipo de trabalho de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Clique em **Gerenciamento de ativos** > **Periódico** > **Previsão** > **Atualizar previsão da ordem de serviço**.

2. Na caixa de diálogo suspensa **Atualizar previsão da ordem de serviço** é possível adicionar seleções sobre ordens de serviço ou trabalhos da ordem de serviço específicos, se necessário. Clique em **Filtro** para fazer essas seleções.

3. Se necessário, você pode configurar a atualização automática como trabalho em lotes na Guia Rápida **Executar em segundo plano**.

4. Clique em **OK** para iniciar a atualização da previsão.


![Figura 2](media/07-work-orders.png)

