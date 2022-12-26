---
title: Erros de lançamento de demonstrativo devido a conflitos de atualização ou estoque indisponível
description: Este artigo fornece possíveis soluções para problemas relacionados ao estoque durante o lançamento do demonstrativo no Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887621"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Erros de lançamento de demonstrativo devido a conflitos de atualização ou estoque indisponível

[!include [banner](../../includes/banner.md)]

Este artigo fornece possíveis soluções para problemas relacionados ao estoque durante o lançamento do demonstrativo no Microsoft Dynamics 365 Commerce.

## <a name="description"></a>descrição

Durante o lançamento das transações do Commerce, você pode receber mensagens de erro relacionadas a saídas de estoque ou conflitos de atualização.

### <a name="inventory-issues-error-message"></a>Mensagem de erro de saídas de estoque

Se você encontrar saídas de estoque, a mensagem de erro recebida será semelhante a este exemplo:

> xx não pode ser separado porque há somente yy disponível(is) no estoque

### <a name="update-conflict-error-messages"></a>Atualizar mensagens de erro de conflito

Um problema de conflito de atualização pode ocorrer quando o método de avaliação de estoque é *custo padrão* ou *média móvel*. Como esses dois métodos são métodos de custos permanentes, o custo final é determinado no momento do lançamento.

Se você estiver usando o método *média móvel*, a mensagem de erro de conflito de atualização recebida se assemelhará a este exemplo:

> O valor de estoque xx.xx não é esperado após o cálculo de despesas proporcionais

Se você estiver usando o método *custo padrão*, a mensagem de erro de conflito de atualização recebida se assemelhará a este exemplo:

> O custo padrão não corresponde ao valor do estoque financeiro após a atualização. Valor = xx.xx, Qtd. = yy.yy, Custo padrão = zz.zz

## <a name="resolutions"></a>Resoluções

### <a name="workaround-for-the-inventory-error"></a>Solução para o erro de estoque

É possível atenuar o erro de estoque atualizando manualmente o estoque do item ou habilitando o estoque físico negativo para o grupo de modelos de item associado ao item no Commerce Headquarters.

Para uma experiência de lançamento consistente, a Microsoft recomenda que você habilite o estoque físico negativo para o grupo de modelos de item. Em algumas situações, não será possível lançar demonstrativos negativos, a menos que o estoque físico negativo esteja habilitado.

Por exemplo, não há estoque disponível para um item, mas um caixa retorna o item e o adiciona novamente à mesma transação a um preço reduzido para imitar uma conciliação de preço. Nesse caso, a transação de devolução e a transação de venda serão retiradas na mesma instrução da ordem do cliente. No entanto, como não há garantia de que a linha de devolução (que aumenta o estoque) será lançada antes que a linha de venda (que reduz o estoque) seja lançada, os erros de estoque poderão ocorrer. Se o estoque físico negativo for habilitado neste cenário, a postagem da transação não é afetada negativamente e o sistema reflete corretamente o estoque.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Habilitar estoque físico negativo para um grupo de modelos de item

Para habilitar o estoque físico negativo para um grupo de modelos de item no Commerce Headquarters, siga estas etapas.

1. Acesse **Gerenciamento do estoque \> Configuração \> Estoque**.
1. No painel de navegação esquerdo, selecione o grupo de modelos de item.
1. Na seção **Políticas de estoque**, em **Estoque negativo**, marque a caixa de seleção **Estoque físico negativo**.

![Estoque físico negativo habilitado.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Solução alternativa para o erro de conflito de atualização

Para obter soluções possíveis para corrigir o erro de conflito de atualização, consulte [Um conflito de atualização ocorre quando o método de avaliação de estoque é custo padrão ou média móvel](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> Para o erro de conflito de atualização, não é necessário excluir as ordens de cliente geradas usando a etapa de agregação do lançamento. Depois de implementar as soluções sugeridas, o demonstrativo deverá ser lançado se você tentar lançá-lo novamente.
