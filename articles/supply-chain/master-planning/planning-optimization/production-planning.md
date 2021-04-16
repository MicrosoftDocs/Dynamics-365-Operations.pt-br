---
title: Planejamento de produção
description: Este tópico descreve o planejamento de produção e explica como modificar as ordens de produção planejadas usando a Otimização de Planejamento.
author: ChristianRytt
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 22b78f44940f71097ca8b1cdb74edb06274bba75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839214"
---
# <a name="production-planning"></a>Planejamento de produção

A Otimização de Planejamento oferece suporte a vários cenários de produção. Se você estiver migrando do mecanismo de planejamento mestre interno existente, é importante estar ciente de alguns comportamentos alterados.

O vídeo a seguir apresenta uma breve introdução a alguns dos conceitos abordados neste tópico: [Dynamics 365 Supply Chain Management: aprimoramentos na Otimização de Planejamento](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Se o sistema ainda não incluir os recursos descritos neste tópico, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Ordens de produção planejadas usando a Otimização de Planejamento*.

## <a name="planned-production-orders"></a>Ordens de Produção Planejadas

Quando o planejamento mestre cria ordens planejadas para atender a requisições, o tipo de ordem é determinado pelo valor do campo **Tipo de ordem planejada**. Se o campo **Tipo de ordem planejada** estiver definido como *Produção*, ordens de produção planejadas serão criadas. Essas ordens de produção planejadas incluem informações sobre a lista de materiais (BOM) ativa e a ID de roteiro da configuração de produção relacionada.

## <a name="requirements-from-boms"></a>Requisições de BOMs

As informações da BOM são respeitadas durante o planejamento mestre. A saída do plano inclui o fornecimento de materiais para cobrir a demanda de materiais relacionada para produção.

Durante o planejamento mestre, a BOM ativa atual é usada para determinar os materiais necessários para a produção. Essa etapa é realizada em todos os níveis da estrutura da BOM que está relacionada à ordem de produção necessária. A requisição de materiais é atendida usando estoque disponível, fornecimento sob encomenda existente e ordens planejadas aprovadas. Se materiais adicionais forem necessários em qualquer lugar, uma ordem planejada será criada para cobrir a demanda.

## <a name="scheduling-during-firming"></a>Agendamento durante a confirmação

As ordens de produção planejadas incluem a ID de roteiro necessária para o agendamento de produção. No entanto, o suporte ao agendamento durante a execução de planejamento de ordens planejadas está pendente. A ID de roteiro é usada para agendar ordens de produção planejadas durante a confirmação. Portanto, o prazo de entrega das ordens de produção planejadas pode ser diferente do prazo de entrega das ordens de produção agendadas e confirmadas relacionadas, que são geradas a partir delas, conforme descrito aqui:

- **Ordem de produção planejada** – o prazo de entrega baseia-se no prazo de entrega estático do produto liberado.
- **Ordem de produção confirmada** – o prazo de entrega baseia-se no agendamento que usa informações de roteiro e restrições de recursos relacionadas.

Para obter mais informações sobre a disponibilidade esperada de recursos, consulte [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).

Se você depender de uma funcionalidade de produção que ainda não está disponível para a Otimização de Planejamento, poderá continuar usando o mecanismo de planejamento mestre interno. Nenhuma exceção é necessária.

## <a name="delays"></a>Atrasos

Se o prazo de entrega dos materiais requisitados for maior do que o período entre a data de hoje e a data de requisição dos materiais, a ordem planejada dos materiais requisitados e a ordem de produção relacionada serão atrasadas. Para ordens planejadas, o atraso (em dias) é calculado com base no prazo de entrega do produto liberado. Em seguida, as informações sobre o atraso são propagadas por todos os níveis da estrutura da BOM. Portanto, você pode seguir o impacto de uma matéria-prima atrasada até a ordem de venda do cliente.

## <a name="modifying-planned-orders"></a>Modificar ordens planejadas

Ao alterar as informações em uma ordem planejada, você receberá a seguinte mensagem: "Observe que o impacto das alterações manuais feitas nas ordens planejadas não será refletido no restante do plano até a próxima execução do planejamento mestre."

Se você quiser alterar as informações em uma ordem planejada e ver o impacto sobre as requisições de materiais relacionadas, siga estas etapas.

1. Atualize a ordem planejada.
2. Aprove a ordem planejada.
3. Execute o planejamento mestre.

Ao executar o planejamento mestre, você não deverá usar filtros se ordens de produção planejadas forem incluídas. Para obter mais informações, consulte a seção [Filtros](#filters) posteriormente neste tópico.

> [!NOTE]
> Se a data de entrega da ordem planejada for alterada para uma data posterior, a demanda poderá ser vinculada a uma nova ordem planejada. Esse comportamento ocorre quando a nova data de fornecimento causa um atraso para a demanda vinculada, mas, de acordo com as configurações de prazo de entrega, o atraso pode ser evitado.

## <a name="explosion-page"></a>Página Detalhamento

Você pode usar a página **Detalhamento** para analisar a demanda necessária para uma ordem de produção específica ou ordem de produção planejada, a cobertura relacionada e as informações de vinculação. As informações na página **Detalhamento** são atualizadas durante o planejamento mestre. Não é possível atualizar as informações diretamente na página **Detalhamento**.

## <a name="filters"></a><a name="filters"></a>Filtros

Para cenários de planejamento que incluem produção, recomendamos evitar execuções de planejamento mestre filtrado. Para garantir que a Otimização de Planejamento tenha as informações necessárias para calcular o resultado correto, você deve incluir todos os produtos que tenham qualquer relação com produtos em toda a estrutura da BOM da ordem planejada.

Embora itens filho dependentes sejam automaticamente detectados e incluídos nas execuções do planejamento mestre, quando o mecanismo de planejamento mestre interno é usado, a Otimização de Planejamento não executa essa ação.

Por exemplo, se um único parafuso da estrutura da BOM do produto A também for usado para produzir o produto B, todos os produtos na estrutura da BOM dos produtos A e B deverão ser incluídos no filtro. Como pode ser muito complexo garantir que todos os produtos façam parte do filtro, recomendamos evitar execuções de planejamento mestre filtrado quando ordens de produção estiverem envolvidas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]