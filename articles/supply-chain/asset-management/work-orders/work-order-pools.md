---
title: Grupos de ordens de serviço
description: Este tópico descreve como trabalhar com grupos de ordens de serviço no Gerenciamento de ativos.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875505"
---
# <a name="work-order-pools"></a>Grupos de ordens de serviço


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Você pode usar grupos de ordens de serviço para ordens de serviço de grupo com algo em comum. Por exemplo, você pode criar grupos de ordens de serviço para

- equipes de trabalho, por exemplo, Equipe de Manutenção A, Equipe de Manutenção B  

- habilidades profissionais, por exemplo, eletricistas ou encanadores  

- locais físicos  

- cronogramas, por exemplo, semanas ou outros períodos  


Se necessário, uma ordem de serviço pode ser colocada em vários grupos de ordens de serviço.


## <a name="create-work-order-pool"></a>Criar grupo de ordens de serviço

Em **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**, você obterá uma visão geral dos grupos de serviço e criará novos grupos.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**.

2. Clique em **Novo**.

3. Insira uma ID de grupo de ordens de serviço no campo **Grupo** e um nome no campo **Nome**.

4. Selecione "Sim" no botão de alternância **Ativo** para indicar que o grupo de ordens de serviço está ativo.

5. Selecione "Sim" no botão de alternância **Excluir relações de ordem de serviço** se desejar que as ordens de serviço sejam automaticamente removidas do grupo de ordens de serviço.

6. No campo **Excluir estado de ciclo de vida**, selecione o estado de ciclo de vida da ordem de serviço. Por exemplo, o estado de ciclo de vida da ordem de serviço para concluir uma ordem de serviço pode ser definido para excluir automaticamente as relações com grupos de ordens de serviço.

7. Você pode começar a adicionar ordens de serviço ao seu grupo de ordens de serviço imediatamente. Na Guia Rápida **Ordens de serviço**, clique em **Adicionar linha**.

8. Selecione uma ordem de serviço no campo **Ordem de serviço**. Os campos relacionados são automaticamente atualizados.

9. Repita as etapas 7 e 8 se desejar adicionar mais ordens de serviço.

10. No campo **Ordem de classificação**, você pode indicar se as ordens de serviço devem ser realizadas em qualquer ordem. Insira os números 1, 2, 3 e assim por diante para indicar uma sequência específica para as ordens de serviço selecionadas.

11. Clique no botão **Ordens de serviço** para ver uma lista de todas as ordens de serviço incluídas no grupo de ordens de serviço.

12. Clique no botão **Capacidade máxima** para abrir **Capacidade máxima** para calcular e exibir a capacidade máxima para o agendamento de manutenção, as ordens de serviço não agendadas e as ordens de serviço agendadas.

13. Clique no botão **Previsão de itens** para abrir **Previsão de itens** para calcular e exibir previsões para itens (partes sobressalentes e outros itens obrigatórios) relacionados ao agendamento de manutenção, às ordens de serviço não agendadas e às ordens de serviço agendadas.

14. Clique no botão **Requisição de compra da ordem de serviço** para abrir a lista **Requisição de compra da ordem de serviço** para ver uma lista de requisições de compra relacionadas às ordens de serviço no grupo de ordens de serviço.

15. Clique no botão **Requisição de compra da ordem de serviço** para abrir a lista **Requisição de compra da ordem de serviço** para ver uma lista de ordens de compra relacionadas às ordens de serviço no grupo de ordens de serviço.

>[!NOTE]
>Quando um grupo de ordens de serviço não for mais relevante para seu planejamento de trabalho, defina a caixa de seleção **Ativo** do grupo como "Não" na exibição de lista **Grupo de ordens de serviço**.

Marque a caixa de seleção **Excluir relações de ordem de serviço** se quiser excluir todas as linhas da ordem de serviço, por exemplo, para criar um grupo vazio que poderá ser usado posteriormente para outras ordens de serviço. Lembre-se de desmarcar a caixa de seleção **Excluir relações de ordem de serviço** se quiser usar o grupo de ordens de serviço para criar novas relações de ordem de serviço posteriormente.


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Adicionar a ordem de serviço em um grupo de ordens de serviço

Conforme descrito na seção acima, você poderá adicionar ordens de serviço a um grupo de ordens de serviço ao criá-lo. Você também pode adicionar uma ordem de serviço a um grupo de ordens de serviço de uma da lista **Todas as ordens de serviço**.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço na lista e clique em **Grupo de ordens de serviço**.

3. Selecione "Adicionar" no campo **Adicionar/remover**.

4. Selecione o grupo de ordens de serviço no campo **Grupo**.

5. Clique em **OK**.

6. Depois de adicionar uma ordem de serviço a um grupo de ordens de serviço, se você quiser colocar a ordem de serviço em uma sequência específica no grupo: abra uma das páginas de listagem de grupos de ordens de serviço, selecione o grupo e clique em **Editar**, ajuste a ordem de classificação das ordens de serviço incluídas no grupo em formulário **Grupo de ordens de serviço** > Guia Rápida **Ordens de serviço** > campo **Ordem de classificação**.

Se quiser remover a ordem de serviço selecionada em um grupo de ordens de serviço, selecione "Remover" na etapa 3.

