---
title: Mensagens de ação
description: Uma mensagem de ação é uma sugestão gerada pelo sistema para alterar uma ordem planejada ou firmada existente.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570244"
---
# <a name="action-messages"></a>Mensagens de ação

[!include [banner](../includes/banner.md)]

Uma mensagem de ação é uma sugestão gerada pelo sistema para alterar uma ordem planejada, aprovada ou firmada existente.

As mensagens de ação são geradas pelo cálculo do planejamento mestre em resposta a requisitos modificados. Por exemplo, a data de remessa ou a quantidade é alterada em uma ordem de venda depois que você já criou uma ordem de compra para atender à demanda dessa ordem de venda. Nesse caso, o mestre que planeja o cálculo gera uma ou mais mensagens que sugerem atualizar a ordem de compra. Você decide se deseja fazer as alterações propostas.

É possível configurar a forma como as mensagens de ação são calculadas para um grupo de cobertura que é vinculado a um item.

## <a name="select-action-messages"></a>Selecionar mensagens de ação

Na página **Grupos de cobertura**, é possível selecionar as mensagens de ação a serem geradas pelo sistema, e os grupos de cobertura ou os itens aos quais as mensagens se aplicam. A tabela a seguir lista a mensagem de ação que você pode selecionar.

| Mensagem | Descrição |
|---|---|
| Adiantar | O sistema irá gerar mensagens de ação, conforme necessário, para mover as ordens para uma data anterior. No campo **Margem de adiantamento**, é possível especificar o número máximo de dias que podem se passar entre o recebimento e a saída sem ação antecipada. |
| Adiar | O sistema irá gerar mensagens de ação, conforme necessário, para mover as ordens para uma data posterior. No campo **Margem de adiamento**, é possível especificar o número máximo de dias que podem se passar entre o recebimento e a saída sem ação de adiamento. |
| Diminuir | O sistema irá gerar mensagens de ação quando as ordens de produção, ordens de compra e outras transações de recebimento devem ser reduzidas para evitar níveis de estoque excessivos. |
| Aumentar | O sistema irá gerar mensagens de ação quando as ordens de produção, ordens de compra e outras transações de recebimento devem ser aumentadas para evitar níveis de estoque baixos. |
| Ações derivadas | As mensagens de ação criadas para transações de recebimento serão propagadas para qualquer requisito derivado, e as mensagens de ação necessárias serão geradas para as transações de recebimento que atendem a esses requisitos. |

As seções a seguir fornecem alguns cenários detalhados.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Aumentar e diminuir ações com quantidades de ordem padrão do produto

Na página **Configurações Padrão da Ordem** de um item, você pode configurar quantidades mínima e máxima da ordem e diversos valores. O sistema leva essas configurações em conta quando sugere ações para garantir que as sugestões nunca causem falta de oferta.

Por exemplo, você tem um item com as seguintes configurações na página **Configurações Padrão da Ordem**:

- **Quantidade mínima de ordens:** *0*
- **Quantidade máxima de ordens:** *90*
- **Múltiplo:** *20*

Se houver demanda para uma quantidade de 60 deste item, o planejamento mestre criará uma ordem de compra planejada para uma quantidade de 60. Se a demanda for aumentada em 30, o planejamento mestre irá sugerir um aumento de 40, pois ele respeitará o múltiplo de 20 e nunca causará a falta de oferta.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Mensagens de ação para ordens relacionadas a estoque de segurança

As mensagens de ação de ordens que fornecem estoque de segurança nunca sugerirão a diminuição da quantidade, abaixo da quantidade necessária para o estoque de segurança. Em outras palavras, se houver uma ordem que esteja fornecendo estoque de segurança e demanda de cliente, e a demanda for reduzida ou cancelada, o planejamento mestre irá sugerir a diminuição da ordem planejada pela redução da demanda. No entanto, ele nunca sugerirá um valor menor do que o estoque de segurança necessário.

O sistema não sugerirá o adiamento de ações para fornecer estoque de segurança, pois supõe-se que o estoque de segurança deve ser fornecido no tempo e na data necessários.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Avançar e adiar ações relacionadas a BOMs

As ações relacionadas aos componentes das listas de materiais (BOMs) devem ser aplicadas antes das ações de seus itens pai, pois as ordens posteriores relacionadas às BOMs de nível superior podem ser afetadas. Em seguida, você deve executar o planejamento mestre novamente para recalcular e sugerir as ações apropriadas.

Por exemplo, você tem a situação de consulta a seguir:

- O bem final *FG* do tipo *produção* tem uma BOM que inclui *RM* de matéria-prima.
- A data atual é 21 de janeiro.
- Uma ordem de produção existente e liberada para *FG* está agendada para 25 de janeiro.
- Para dar suporte à ordem de produção existente, o planejamento mestre criou uma ordem de compra planejada para o *RM* obrigatório. Esta ordem tem uma data obrigatória de 25 de janeiro.
- Uma nova ordem de venda para *FG* é criada hoje. Sua data obrigatória é hoje (21 de janeiro).
- 21 de Janeiro está fechada para entrega no calendário de *RM*, mas 22 de janeiro está aberta.

Quando o planejamento mestre é executado, ele gera mensagens de ação de adiantamento que sugerem mudar a produção programada anteriormente para que você possa atender à ordem de hoje.

- Para atender à nova demanda, ele sugere mover a ordem de produção para *FG* para até 21 de janeiro. (Ele faz essa sugestão sem levar em consideração a data de fechamento de *RM*.)
- Como *RM* ainda é necessário para a ordem de produção, ele sugere a transferência da ordem de compra planejada também. No entanto, desta vez ele verifica o calendário de *RM*. Portanto, ele sugere mover a ordem de compra planejada para o *RM* em 22 de janeiro (porque 21 de janeiro está fechada).

Como você pode ver, o *RM* de matéria-prima obrigatório agora vai chegar muito atrasado para a produção programada de *FG*. Portanto, primeiro você deve aplicar a ação adiantada à ordem de compra planejada para *RM* e executar o planejamento mestre novamente. Nesse ponto, o planejamento mestre gerará uma nova mensagem de ação que sugere mudar a ordem de produção de *FG* para 22 de janeiro.
