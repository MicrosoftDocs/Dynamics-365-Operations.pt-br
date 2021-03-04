---
title: Previsões de manutenção
description: Este tópico explica as previsões de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2686dd6db032239e2a3aac03f3998cee055302f6
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422633"
---
# <a name="maintenance-forecasts"></a>Previsões de manutenção

[!include [banner](../../includes/banner.md)]



Quando cria uma ordem de serviço, você cria trabalhos da ordem de serviço que possuem ativos e tipos de trabalho de manutenção relacionados. Quando você seleciona um tipo de trabalho de manutenção que contém previsões de manutenção, as previsões são copiadas automaticamente para a ordem de serviço.

Você talvez possa adicionar ou excluir linhas de previsão de uma ordem de serviço. A configuração do estado de ciclo de vida da ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você pode adicionar ou editar as linhas de previsão. Para obter mais informações sobre os estados de ciclo de vida da ordem de serviço e os estágios do projeto relacionados, consulte [Previsões, ordens de serviço e projetos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço na lista e, em seguida, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Projeto**, selecione **Previsão**. A página **Previsão de manutenção da ordem de serviço** mostra as linhas de previsão do tipo de trabalho de manutenção selecionado no trabalho da ordem de serviço.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Adicionar previsão de horas para uma ordem de serviço

1. Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.

2. Na Guia Rápida **Horas**, selecione **Adicionar** para criar uma linha.

3. No campo **Categoria**, selecione uma categoria.

4. Insira o número de horas previstas no campo **Horas**.

5. No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.


## <a name="add-an-items-forecast-to-a-work-order"></a>Adicionar previsão de itens em uma ordem de serviço

Há três maneiras de adicionar itens a uma previsão de manutenção de ordem de serviço. Você pode criar linhas para os itens (peças sobressalentes) que não foram incluídos na lista de peças sobressalentes ou na BOM (lista de materiais) de ativos, pode selecionar peças sobressalentes na lista aprovada de peças sobressalentes ou selecionar itens da BOM de ativos.

- Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.

- Na Guia Rápida **Itens**, adicione itens à previsão de manutenção usando o método apropriado.

Para criar uma linha para uma peça sobressalente que não está na lista de peças sobressalentes ou na BOM de ativos, siga estas etapas:

1. Selecione **Adicionar**.
2. No campo **Nº do item**, selecione o item.
3. No campo **Quantidade de venda**, insira a quantidade.
4. No campo **Unidade**, selecione a unidade de medida da quantidade.
5. Nos campos **Preço de custo** e **Moeda**, informe os valores apropriados.
6. No campo **Propriedade da linha**, selecione uma propriedade de linha.
7. Para alterar a lista de dimensões exibida nas linhas do item, selecione **Estoque** > **Exibir dimensões**, selecione as dimensões e, depois, defina a opção **Salvar configuração** como **Sim**.

Para adicionar uma peça sobressalente de uma lista aprovada de peças sobressalentes, siga estas etapas:

1. Selecione **Adicionar peças sobressalentes**.
2. Selecione a peça sobressalente e edite as informações relacionadas, conforme o necessário.
3. Selecione **OK**.

Para adicionar um item da BOM de ativos, siga estas etapas:

1. Selecione **Adicionar itens da BOM**.
2. Selecione o item e edite as informações relacionadas, conforme o necessário.
3. Selecione **OK**.

Para obter uma visão geral que mostre onde o item na linha selecionada é usado em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço no Gerenciamento de Ativos, selecione **Item onde usado**. Para obter mais informações sobre essa visão geral, consulte [Item onde usado](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Adicionar previsão de despesa a uma ordem de serviço

1. Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.

2. Na Guia Rápida **Despesa**, selecione **Adicionar** para criar uma linha.

3. No campo **Categoria**, selecione uma categoria.

4. No campo **Quantidade**, insira a quantidade.

5. Nos campos **Preço de custo**, **Moeda de venda** e **Preço de venda**, insira os valores apropriados.

6. No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.

>[!NOTE]
>A Guia Rápida **Totais da previsão de manutenção** mostra uma visão geral do número de linhas que foram criadas em cada Guia Rápida para o trabalho da ordem de serviço selecionado e para a ordem de serviço. Também mostra o total de horas de trabalho previstas para o trabalho da ordem de serviço e para a ordem de serviço.

A ilustração a seguir mostra um exemplo da página **Previsão de manutenção da ordem de serviço**.

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Atualização automática de previsões de ordem de serviço

Se os valores de custos por hora, custos do item e despesas forem atualizados em outros módulos do Microsoft Dynamics 365 for Finance and Operations, as previsões da ordem de serviço no Gerenciamento de Ativos poderão ser automaticamente atualizadas para refletir essas alterações. Esse recurso ajuda a garantir que os preços de custo mais recentes sejam sempre usados nas previsões de ordem de serviço. Você também pode fazer atualizações semelhantes para [previsões de tipo de trabalho de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Selecione **Gerenciamento de ativos** > **Periódico** > **Previsão** > **Atualizar previsão da ordem de serviço**.

2. Na caixa de diálogo **Atualizar previsão da ordem de serviço**, na Guia Rápida **Registros a serem incluídos**, você pode adicionar seleções relacionadas a ordens de serviço ou trabalhos da ordem de serviço específicos, conforme o necessário. Clique em **Filtro** para fazer as seleções relevantes.

3. Na Guia Rápida **Executar em segundo plano**, você pode configurar a atualização automática como um trabalho em lote, conforme necessário.

4. Selecione **OK** para iniciar a atualização da previsão.


A ilustração a seguir mostra um exemplo da caixa de diálogo **Atualizar previsão da ordem de serviço**.

![Figura 2](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]