---
title: Solucionar problemas de planejamento mestre
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com planejamento mestre.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8e78634c0efb1c401297559ce40b2ca30519f3bf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809461"
---
# <a name="troubleshoot-master-planning"></a>Solucionar problemas de planejamento mestre

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com planejamento mestre.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>O detalhamento da lista de materiais se comporta de maneira diferente para ordens de produção firmadas e para ordens de produção estimadas para trabalho criado manualmente.

### <a name="issue-description"></a>Descrição do problema

Quando uma ordem de produção é firmada, os itens não são detalhados quando você detalha a lista de materiais (BOM). No entanto, quando você cria manualmente uma ordem de serviço e estima a ordem de produção, os itens são detalhados.

### <a name="issue-resolution"></a>Resolução do problema

O sistema está funcionando conforme o esperado. O detalhamento que ocorre quando a ordem de produção é firmada apontará para a ordem planejada, mas não parece que a ordem planejada está atualmente firmada neste caso. No entanto, se a ordem de produção foi estimada, o detalhamento é acionado a partir da ordem de produção liberada, onde não existe ordem planejada.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>O valor de atraso não é atualizado quando eu reprogramo uma ordem planejado.

Para atualizar o atraso de ordens planejadas, abra a caixa de diálogo **Reprogramação** para a ordem planejada. Na FastTab **Detalhamento**, verifique se a opção **Executar detalhamento após reprogramação** está definida como *Sim*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>A programação da produção não considera as margens de segurança definidas na cobertura do item para fornecimento vinculado.

### <a name="issue-description"></a>Descrição do problema

O planejamento mestre considera as margens de segurança. Contudo, as margens de segurança são ignoradas quando as ordens de produção planejadas são programadas.

### <a name="issue-resolution"></a>Resolução do problema

As margens são consideradas somente durante o planejamento mestre, não durante a programação manual. As margens são projetadas para atuar como um buffer durante a fase de planejamento, para dar alguma "margem" para o processo real.

Para obter o resultado desejado, você pode remover a margem. A rota deve ser atualizada para incluir o tempo desejado (por exemplo, como tempo de fila). O planejamento mestre e a programação manual devem produzir o mesmo resultado.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>As ordens planejadas são geradas mesmo que tenhamos itens em estoque e já existam ordens de produção para eles.

É possível consertar esse problema aumentando o valor de **Dias positivos** para os grupos relevantes na página **Grupo de cobertura**. Essa alteração fará com que o sistema determine se o estoque disponível pode ser usado para a demanda. Depois, uma nova ordem planejada não será gerada para os itens que estão em estoque.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>O planejamento mestre não parece respeitar as limitações de capacidade e está programando mais do que a capacidade disponível.

### <a name="issue-description"></a>Descrição do problema

Quando você usa a programação de operação em que há capacidade finita e a rota especifica uma combinação de requisitos para um grupo de recursos e recursos individuais, existe uma pequena chance de reserva excessiva devida à forma como o algoritmo valida os conflitos de capacidade. Essa reserva excessiva pode ocorrer quando você usa auxiliares para executar o planejamento mestre. É mais provável que ela ocorra se houver muitos trabalhos com um tempo de execução relativamente curto.

### <a name="issue-resolution"></a>Resolução do problema

Se for essencial que nenhuma reserva reserva excessiva ocorra na programação da operação, você pode tornar a parte da programação do planejamento mestre em thread único ativando a opção **Capacidade finita precisa para programação de operação** na página **Parâmetros de planejamento mestre**. Essa opção não está disponível por padrão. Você deve adicioná-la manualmente à página usando recursos de personalização. Quando você usa essa opção, a programação será executada mais lentamente pela falta de processamento paralelo.

## <a name="planned-orders-take-a-long-time-to-update"></a>As ordens planejadas demoram muito para serem atualizadas.

### <a name="issue-description"></a>Descrição do problema

Ao atualizar a quantidade necessária e/ou data de entrega em uma ordem planejada, normalmente leva pelo menos 30 segundos por ordem para salvar a atualização.

### <a name="issue-resolution"></a>Resolução do problema

Esse é um problema conhecido com o mecanismo de planejamento mestre integrado. Ele é causado pela explosão automática subjacente por meio da estrutura da BOM durante as edições. Esse problema é abordado na Otimização de Planejamento, onde um planejador pode atualizar e aprovar os pedidos relevantes e, quando desejado, acionar uma execução de planejamento para atualizar as ordens planejadas para a estrutura de BOM subjacente.

Uma maneira de melhorar o desempenho com o mecanismo de planejamento mestre integrado é fazer o seguinte:

1. Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano.
1. Expanda a FastTab **Limite de tempo em dias**.
1. Defina **Detalhamento** como *Sim* e defina o campo abaixo dessa configuração como 0 (zero).

> [!NOTE]
> Isso limitará o período de detalhamentos realizados desse plano mestre a um único dia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]