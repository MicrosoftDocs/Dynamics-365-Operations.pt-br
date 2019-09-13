---
title: Compras
description: Este tópico explica compras no Gerenciamento de Ativos.
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
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875502"
---
# <a name="procurement"></a>Compras


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Em Gerenciamento de Ativos, você pode obter uma visão geral das requisições de compra e ordens de compra relacionadas a ordens de serviço. Também é possível criar uma ordem de compra ou uma requisição de compra de uma ordem de serviço.

Na lista **Requisição de compra de ordem de serviço** (**Gerenciamento de ativos** > **Comum** > **Compras** > **Requisição de compra de ordem de serviço**), você verá uma lista de requisições de compra relacionadas a ordens de serviço.

- Selecione um trabalho de ordem de serviço na lista **Requisição de compra de ordem de serviço** e clique no botão **Requisição de compra** para abrir a requisição de compra relacionada.  
- Selecione um trabalho de ordem de serviço na lista **Requisição de compra de ordem de serviço** e clique no botão **Ordem de serviço** para abrir a ordem de serviço relacionada.  
- Selecione um trabalho de ordem de serviço na lista **Requisição de compra de ordem de serviço** e clique no botão **Item onde usado** se quiser obter uma visão geral de onde o item na linha selecionada é usado no Gerenciamento de Ativos em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço. 

![Figura 1](media/08-work-orders.png)


Na lista **Requisição de compra de ordem de serviço** (**Gerenciamento de ativos empresariais** > **Comum** > **Compras** > **Compra de ordem de serviço**), você verá uma lista de requisições de compra relacionadas a ordens de serviço.

- Selecione um trabalho de ordem de serviço na lista **Compra de ordem de serviço** e clique no botão **Ordem de compra** para abrir a ordem de compra relacionada.  
- Selecione um trabalho de ordem de serviço na lista **Compra de ordem de serviço** e clique no botão **Ordem de serviço** para abrir a ordem de serviço relacionada.  
- Selecione um trabalho de ordem de serviço na lista **Compra de ordem de serviço** e clique no botão **Item onde usado** se quiser obter uma visão geral de onde o item na linha selecionada é usado no Gerenciamento de Ativos em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço. 

![Figura 2](media/09-work-orders.png)


Nas listas mostradas acima, um ícone relacionado ao controle da data de entrega é colocado à direita em cada linha. Se o ícone mostrar um ponto de exclamação em um círculo vermelho, isso significa que a entrega na requisição de compra ou na ordem de compra relacionada pode ser atrasada.

Em uma requisição de compra, a data usada para calcular o possível atraso encontra-se no formulário **Requisições de compra** > Guia Rápida **Cabeçalho de requisição de compra** > campo **Data solicitada**. Essa data é comparada à data disponível na ordem de serviço ou no trabalho de ordem de serviço da mesma forma como a data da ordem de compra.

Em uma ordem de compra, a data usada para calcular o possível atraso é a data relacionada à linha de ordem de compra, mostrada no formulário **Ordem de compra** > selecione a linha da ordem de compra > **Detalhes da linha** Guia Rápida > guia **Configuração** > campo **Data de entrega confirmada**. Se esse campo não for preenchido, a data no campo **Data de entrega** da Guia Rápida **Cabeçalho da ordem de compra** será usada. Uma dessas datas será comparada à data disponível na ordem de serviço ou no trabalho de ordem de serviço na seguinte ordem:

- Data de início real na ordem de serviço ou  

- Data de início agendada no trabalho de ordem de serviço relacionado ou  

- Data de início agendada na ordem de serviço ou  

- Data de início esperada na ordem de serviço  


## <a name="create-purchase-order-from-a-work-order"></a>Criar uma ordem de compra de uma ordem de serviço

Em **Todas as ordens de trabalho**, selecione um trabalho de ordem de serviço e crie uma ordem de compra ou uma requisição de compra relacionada. Isso é feito para garantir relações de projeto entre a ordem de compra ou a requisição de compra e a ordem de serviço.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Na lista **Todas as ordens de serviço** ou **Ordens de serviço ativas**, selecione a ordem de serviço para a qual você deseja criar uma ordem de compra e clique em **Editar**.

3. No formulário **Ordem de serviço** > Guia Rápida **Trabalhos de manutenção de ordem de serviço**, selecione o trabalho de ordem de serviço para o qual deseja criar a ordem de compra.

4. Clique em **Tarefas de item** > **Ordem de compra de trabalho de ordem de serviço**.

5. Na página de listagem **Ordens de compra de projeto**, clique em **Novo**.

6. Crie a ordem de compra.

>[!NOTE]
>A criação de uma requisição de compra é praticamente idêntica à criação de uma ordem de compra. A única diferença é aquela no procedimento acima, você clica em **Tarefas de item** > **Requisição de compra de trabalho de ordem de serviço** na etapa 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relação de projeto entre ordem de serviço e ordem de compra ou requisição de compra

Uma linha de ordem de compra ou linha de requisição de compra está relacionada a um trabalho de ordem de serviço por meio do projeto de ordem de serviço e o número da atividade de projeto relacionada. Quando você cria uma ordem de compra ou uma requisição de compra de um trabalho de ordem de serviço, o número da atividade de projeto relacionado é obrigatório. O número de atividade do projeto será inserido automaticamente em uma ordem de compra ou em uma requisição de compra se a ordem de serviço relacionada contiver trabalhos de ordem de serviço que usem o mesmo tipo de trabalho de manutenção. Se os trabalhos de ordem de serviço contiverem tipos de trabalho de manutenção diferentes, o número de atividade de projeto deverá ser inserido manualmente.

Para consultar ou inserir o número de atividade relacionado a uma linha de ordem de compra, abra **Compra da ordem de serviço** > selecione o registro da ordem de compra > clique na ordem de compra na coluna **Ordem de compra** > Guia Rápida **Detalhes da linha** > guia **Projeto** > campo **Número da atividade**.


![Figura 3](media/10-work-orders.png)


Da mesma forma, para consultar ou inserir o número de atividade relacionado a uma linha de requisição de compra de ordem de serviço, abra **Requisição de compra da ordem de serviço** > selecione o registro da requisição de compra > clique na requisição de compra na coluna **Requisição de compra** > Guia Rápida **Detalhes da linha** > guia **Projeto** > campo **Número da atividade**.

