---
title: BOMs de Ativos
description: Este tópico descreve listas de materiais (BOMs) de ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f42646ae865cd530203c997fd10c8ccd59e7fa2b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422320"
---
# <a name="asset-boms"></a>BOMs de Ativos

[!include [banner](../../includes/banner.md)]

 

Este tópico descreve listas de materiais (BOMs) de ativos no Asset Management. A **BOM de ativos** mostra uma lista de todos os itens (partes sobressalentes e outros itens) usados em um ativo durante toda sua vida útil. Quando você criar um novo ativo, considere a configuração de uma BOM de ativos como parte do procedimento de instalação. Assim, você pode controlar o histórico de itens do ativo desde a data de criação.

Depois de concluir um trabalho de manutenção, e depois que o consumo de item tiver sido registrado em uma ordem de serviço, você poderá acompanhar o consumo de peças sobressalentes e de outros itens usados no ativo. Essa funcionalidade permite manter um registro completo de consumo de itens para todos os ativos. Por exemplo, você pode usar o registro para monitorar se uma peça sobressalente específica é substituída com frequência, ou para controlar as partes sobressalentes ou outros itens usados no momento em um ativo.

> [!NOTE]
> Em uma ordem de serviço, o consumo de itens pode incluir peças sobressalentes e outros itens adicionais, como lubrificantes, parafusos e gaxetas.

Uma BOM de ativos pode ser automaticamente atualizada com base na configuração do Asset Management. Se um estado de ciclo de vida de ordem de serviço tiver sido criado para lidar com ordens de serviço encerradas ou concluídas, e se a opção **Atualizar BOM de ativos** para esse estado de ciclo de vida de ordem de serviço estiver definido como **Sim** na página **Estados de ciclo de vida de ordem de serviço**, todos os itens usados na ordem de serviço serão automaticamente atualizados na página **BOM de ativos** quando a ordem de serviço for atualizada para esse estado de ciclo de vida. 


Você também pode atualizar manualmente uma BOM de ativos criando novas linhas de item na página **BOM de ativos**.

Na página **BOM de ativos**, você pode rastrear o histórico de peças sobressalentes para ativos depois que o consumo de itens é registrado em uma ordem de serviço. Para usar essa funcionalidade, selecione os grupos de itens que devem ser usados para o registro de peças sobressalentes na página **Grupos de itens de peças sobressalentes**.

Para usar a funcionalidade BOM de ativos, primeiro você deverá configurar os grupos de itens de peças sobressalentes. Depois, se desejar que a BOM de ativos seja automaticamente atualizada quando uma ordem de serviço for concluída, você poderá configurar um estado de ciclo de vida de ordem de serviço para lidar essa atualização. 


## <a name="set-up-spare-parts-item-groups"></a>Configurar grupos de itens de peças sobressalentes

A configuração de histórico de peças sobressalentes se baseia em grupos de itens criados no módulo **Gerenciamento de estoque e depósito**. No Asset Management, você configura grupos de itens para poder acompanhar o histórico de peças sobressalentes dos itens nos grupos de itens selecionados.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativo** \> **Grupos de itens de peças sobressalentes**.
2. Selecione **Novo** para configurar um grupo de itens.
3. No campo **Grupo de itens**, selecione o grupo. O nome do grupo é inserido automaticamente no campo **Nome**.

## <a name="view-and-update-asset-boms"></a>Exibir e atualizar BOMs de ativos

Depois de lançar o consumo de itens em uma ordem de serviço, você poderá exibir o consumo de item registrado na página **BOM de ativos**.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Ativos ativos**. Selecione o ativo da lista e depois selecione **BOM de ativos**.

    > [!NOTE]
    > Para exibir todos os registros do consumo de item em todos os ativos, selecione **Gerenciamento de ativos** \> **Consultas** \> **Ativos** \> **BOM de ativos**.

2. Selecione **Atualizar BOM de ativos**. Você pode adicionar ativos, tipos de ativo e recursos à atualização como for necessário ao escolher **Selecionar**. Selecione **OK** para iniciar a atualização. Você também pode configurar a função Atualizar como um trabalho em lotes.
3. Se quiser ver mais informações relacionadas aos itens, adicione dimensões de estoque. Selecione **Estoque** \> **Exibição de dimensões** e marque as caixas de seleção para as dimensões que você deseja ver. Para manter essa configuração para todos os ativos na página **BOM de ativos**, defina a opção **Salvar configuração** como **Sim**.
4. Para obter uma visão geral de onde no Asset Management o item na linha selecionada é usado, em relação a ativos, padrões de tipo de trabalho, partes sobressalentes e ordens de serviço, selecione **Item onde usado**. 
5. Para ver apenas as linhas de item ativas, selecione **Exibir** \> **Atual**. Para ver todas as linhas de item, incluindo as linhas onde a data de vencimento é anterior à data atual, selecione **Exibir** \> **Tudo**.

> [!NOTE]
> Quando você tiver concluído uma ordem de serviço, se alguns itens ou peças sobressalentes relacionados ao ativo tiverem expirado ou tiverem sido substituídos por outros itens ou peças sobressalentes, recomendamos que você atualize a BOM de ativos de forma correspondente.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Criar uma nova linha de item em uma BOM de ativos

Você pode as linhas de item para ativos manualmente.

1. Na página **BOM de ativos**, selecione **Novo**.
2. No campo **Ativo**, selecione o ativo para o qual será adicionada uma linha de item.
3. No campo **Número da linha**, insira um número de linha sequencial.
4. No campo **Efetivação**, insira uma data inicial para o item.
5. Se item tiver um vencimento, no campo **Vencimento**, insira uma data de término.
6. No campo **Nº do item**, selecione o item. O nome é inserido automaticamente no campo **Nome do produto**.
7. No campo **Quantidade**, insira a quantidade usada. O campo **Unidade** será atualizado automaticamente.
