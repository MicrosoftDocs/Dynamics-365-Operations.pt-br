---
title: Grupos de ordens de serviço
description: Este tópico descreve como trabalhar com grupos de ordens de serviço no Gerenciamento de ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7b0e3e5b25a291517d5ccefa1ed25b20255be187
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356040"
---
# <a name="work-order-pools"></a>Grupos de ordens de serviço

[!include [banner](../../includes/banner.md)]


Você pode usar grupos de ordens de serviço para ordens de serviço de grupo com algo em comum. Veja alguns exemplos de situações para as quais você pode criar grupos de ordem de serviço:

- Equipes de trabalho, por exemplo, Equipe de manutenção A ou Equipe de manutenção B  

- Habilidades profissionais, como eletricistas ou encanadores  

- Locais físicos  

- Cronogramas, como semanas ou outros períodos  

De acordo com a sua necessidade, você pode inserir uma ordem de serviço em vários grupos de ordens de serviço.


## <a name="create-a-work-order-pool"></a>Criar um grupo de ordens de serviço

Na página de listagem **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**, você obterá uma visão geral dos grupos de ordens de serviço e criará novos grupos.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**.

2. Selecione **Novo**.

3. No campo **Grupo**, insira um identificador para o grupo de ordens de serviço.

4. No campo **Nome**, insira um nome.

5. Defina a opção **Ativo** como **Sim** para indicar que o grupo de ordens de serviço está ativo.

6. Defina a opção **Excluir relações de ordem de serviço** como **Sim** se desejar que as ordens de serviço sejam automaticamente removidas do grupo de ordens de serviço.

7. No campo **Excluir estado de ciclo de vida**, selecione o estado de ciclo de vida da ordem de serviço. Por exemplo, o estado de ciclo de vida da ordem de serviço para concluir uma ordem de serviço pode ser definido para excluir automaticamente as relações com grupos de ordens de serviço.

    Você pode começar a adicionar ordens de serviço ao seu grupo de ordens de serviço imediatamente.

8. Na Guia Rápida **Ordens de serviço**, selecione **Adicionar linha**.

9. No campo **Ordem de serviço**, selecione uma ordem de serviço. Os campos relacionados são automaticamente atualizados.

10. Repita as etapas 8 a 9 para adicionar mais ordens de serviço.

11. Se as ordens de serviço adicionadas forem efetuadas em uma ordem específica, no campo **Ordem de classificação**, você pode inserir os números **1**, **2**, **3**, e assim por diante, para especificar a ordem.

12. Para visualizar uma lista de todas as ordens de serviço incluídas no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Ordens de serviço** para abrir a página de listagem **Todas as ordens de serviço**.

13. Para calcular e visualizar a capacidade máxima do agendamento de manutenção, ordens de serviço não agendadas e ordens de serviço agendadas, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Capacidade máxima** para abrir a caixa de diálogo **Calcular capacidade máxima**.

14. Para calcular e visualizar previsões de itens (peças sobressalentes e outros itens necessários) relacionadas ao agendamento de manutenção, ordens de serviço não agendadas e ordens de serviço agendadas, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Previsão de itens** para abrir a caixa de diálogo **Calcular previsão de itens**.

15. Para visualizar uma lista de requisições de compra relacionadas às ordens de serviço no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Compras**, selecione **Requisição de compra da ordem de serviço** para abrir a página de listagem **Requisição de compra da ordem de serviço**.

16. Para visualizar uma lista de ordens de compra relacionadas às ordens de serviço no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Compras**, selecione **Compra da ordem de serviço** para abrir a página de listagem **Compra da ordem de serviço**.

>[!NOTE]
>Quando um grupo de ordens de serviço não for mais relevante para seu planejamento de trabalho, defina a opção **Ativo** do grupo como **Não** na exibição de lista da página **Grupo de ordens de serviço**.

Para excluir todas as linhas da ordem de serviço, defina a opção **Excluir relações da ordem de serviço** como **Sim**. Esta opção é útil se, por exemplo, você quiser criar um grupo vazio que poderá usar posteriormente para outras ordens de serviço. Quando estiver pronto para usar o grupo de ordens de serviço para criar novas relações de ordens de serviço posteriormente, lembre-se de definir a opção **Excluir relações da ordem de serviço** como **Não**.

A ilustração a seguir mostra um exemplo da página de listagem **Grupo de ordens de serviço**.

![Figura 1.](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Adicionar uma ordem de serviço a um grupo de ordens de serviço

Conforme descrito na seção anterior, você poderá adicionar ordens de serviço a um grupo de ordens de serviço ao criá-lo. Você também pode adicionar ordens de serviço a um grupo de ordens de serviço na página de listagem **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

1. Selecione a ordem de serviço e, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Manter**, selecione **Grupo de ordens de serviço**.

2. Selecione a ordem de serviço na lista e clique em **Grupo de ordens de serviço**.

3. Na caixa de diálogo **Manter grupo de ordens de serviço**, no campo **Adicionar/remover**, selecione **Adicionar**.

4. No campo **Grupo**, selecione o grupo de ordens de serviço.

5. Selecione **OK**.

6. Para colocar a ordem de serviço que você adicionou em uma ordem específica no grupo de ordens de serviço, na página de listagem **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativas**, selecione o grupo e depois **Editar**. Em seguida, na página **Grupo de ordens de serviço** na Guia Rápida **Ordens de serviço**, use o campo **Ordem de classificação** para ajustar a ordem das ordens de serviço incluídas no grupo.

Para remover uma ordem de serviço de um grupo de ordens de serviço, repita essas etapas, mas selecione **Remover** na etapa 3.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]