---
title: Compras
description: Este tópico explica compras no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f3e01dd85cbe8e2b2c9095431f3e0aead817a5a5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352753"
---
# <a name="procurement"></a>Compras

[!include [banner](../../includes/banner.md)]

Em Gerenciamento de ativos, você pode obter uma visão geral das requisições de compra e ordens de compra que estão relacionadas a ordens de serviço. Você também pode criar uma ordem de compra ou uma requisição de compra de uma ordem de serviço.

A página de listagem **Requisição de compra de ordem de serviço** (**Gerenciamento de ativos** > **Comum** > **Compras** > **Requisição de compra de ordem de serviço**) mostra uma lista de requisições de compra que estão relacionadas a ordens de serviço. Ao selecionar um trabalho de ordem de serviço nessa página, você pode usar os botões no grupo **Exibir** na guia Painel de ações da **Requisição de compra da ordem de serviço** para realizar várias ações:

- Para abrir a requisição de compra relacionada, selecione **Requisição de compra**. 
- Para abrir a ordem de serviço relacionada, selecione **Ordem de serviço**.
- Para obter uma visão geral que mostre onde o item na linha selecionada é usado em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço no Gerenciamento de Ativos, selecione **Item onde usado**. Para obter mais informações sobre essa visão geral, consulte [Item onde usado](../controlling-and-reporting/item-where-used.md).

A ilustração abaixo mostra um exemplo da página de listagem **Requisição de compra da ordem de serviço**.

![Figura 1.](media/08-work-orders.png)


A página de listagem **Compra de ordem de serviço** (**Gerenciamento de ativos** > **Comum** > **Compras** > **Requisição de compra de ordem de serviço**) mostra uma lista de ordens de compra que estão relacionadas a ordens de serviço. Ao selecionar um trabalho de ordem de serviço nessa página, você pode usar os botões no grupo **Exibir** na guia Painel de ações da **Compra da ordem de serviço** para realizar várias ações:

- Para abrir a ordem de compra relacionada, selecione **Ordem de compra**. 
- Para abrir a ordem de serviço relacionada, selecione **Ordem de serviço**.
- Para obter uma visão geral que mostre onde o item na linha selecionada é usado em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço no Gerenciamento de Ativos, selecione **Item onde usado**. Para obter mais informações sobre essa visão geral, consulte [Item onde usado](../controlling-and-reporting/item-where-used.md).

A ilustração a seguir mostra um exemplo da página de listagem **Compra da ordem de serviço**.

![Figura 2.](media/09-work-orders.png)


Na página de listagem **Compra da ordem de serviço** e **Requisição de compra da ordem de serviço**, um símbolo relacionado ao controle da data de entrega aparece do lado direito de cada linha. Se o símbolo for um ponto de exclamação em um círculo vermelho, a entrega da ordem de compra ou requisição de compra relacionada pode sofrer atrasos.

Para uma ordem de compra, a data relacionada à linha da ordem de compra é usada para calcular um possível atraso. Para visualizar essa data, na página **Ordem de compra**, selecione a linha da ordem de compra. A data é exibida no campo **Data de entrega confirmada** na guia **Configuração** da Guia Rápida **Detalhes da linha**. Se o campo **Data de entrega confirmada** não estiver configurado, a data no campo **Data de entrega** na Guia Rápida **Cabeçalho da ordem de compra** é usada para o cálculo. Uma dessas datas será comparada à data disponível na ordem de serviço ou no trabalho da ordem de serviço, na seguinte ordem:

1. Data de início real na ordem de serviço, ou  

2. Data de início agendada no trabalho de ordem de serviço relacionado, ou 

3. Data de início agendada na ordem de serviço, ou 

4. Data de início esperada na ordem de serviço 

Para uma requisição de compra, a data no campo **Data solicitada** na Guia Rápida **Cabeçalho da requisição de compra** da página **Requisições de compra** é usada para calcular um possível atraso. A data nesse campo é comparada à data disponível na ordem de serviço ou no trabalho de ordem de serviço, na mesma ordem usada para uma ordem de compra.


## <a name="create-a-purchase-order-from-a-work-order"></a>Criar uma ordem de compra de uma ordem de serviço

Na página de listagem **Todas as ordens de serviço**, você pode selecionar um trabalho de ordem de serviço e criar uma ordem de compra relacionada ou uma requisição de compra relacionada. Dessa forma, você ajuda a garantir que existam relações de projeto entre a ordem de compra ou a requisição de compra e a ordem de serviço.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço para criar uma ordem de compra e, em seguida, selecione **Editar**.

3. Na Guia Rápida **Trabalhos de manutenção da ordem de serviço**, selecione o trabalho de ordem de serviço para o qual deseja criar a ordem de compra.

4. Selecione **Tarefas do item** > **Ordem de compra do trabalho da ordem de serviço**.

5. Na página de listagem **Ordens de compra de projeto**, clique em **Novo**.

6. Crie a ordem de compra.

>[!NOTE]
>Para criar uma requisição de compra relacionado, rastrear as mesmas etapas. No entanto, selecione **Tarefas do item** > **Requisição de compra do trabalho da ordem de serviço** na etapa 4.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relação de projeto entre ordem de serviço e ordem de compra ou requisição de compra

Uma linha de ordem de compra ou linha de requisição de compra está relacionada a um trabalho de ordem de serviço por meio do projeto de ordem de serviço e o número da atividade de projeto relacionada. Quando você cria uma ordem de compra ou uma requisição de compra de um trabalho de ordem de serviço, o número da atividade de projeto relacionado é obrigatório. Se todos os trabalhos da ordem de serviço na ordem de serviço relacionada tiverem o mesmo tipo de trabalho de manutenção, o número de atividade do projeto será inserido automaticamente na ordem de compra ou na requisição de compra. Se todos os trabalhos da ordem de serviço tiverem tipos de trabalho de manutenção diferentes, insira o número de atividade do projeto na ordem de compra ou na requisição de compra.

Para visualizar ou inserir o número da atividade relacionada à linha da ordem de compra, na página de listagem **Compra da ordem de serviço**, selecione o registro da ordem de compra e, na coluna **Ordem de compra**, selecione o link para a ordem de compra. Você pode localizar o campo **Número da atividade** na guia **Projeto** na Guia Rápida **Detalhes da linha**.

A ilustração abaixo mostra um exemplo da página **Ordem de compra**, com enfoque no **Número da atividade**.

![Figura 3.](media/10-work-orders.png)

Da mesma forma, para visualizar ou inserir o número da atividade relacionada à linha da requisição de compra da ordem de serviço, na página de listagem **Requisição de compra da ordem de serviço**, selecione o registro de requisição de compra e, na coluna **Requisição de compra**, selecione o link para a requisição de compra. Você pode localizar o campo **Número da atividade** na guia **Projeto** na Guia Rápida **Detalhes da linha**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]