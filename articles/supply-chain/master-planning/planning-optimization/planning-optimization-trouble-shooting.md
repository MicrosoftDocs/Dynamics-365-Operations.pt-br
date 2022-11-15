---
title: Solucionar Problemas da Otimização de Planejamento
description: Este artigo descreve como corrigir problemas que podem ocorrer ao trabalhar com a otimização de planejamento.
author: t-benebo
ms.date: 05/07/2020
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
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739720"
---
# <a name="troubleshoot-planning-optimization"></a>Solucionar Problemas da Otimização de Planejamento 

[!include [banner](../../includes/banner.md)]

Este artigo descreve como corrigir problemas comuns que podem ocorrer ao trabalhar com a otimização de planejamento.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>A instalação do suplemento de otimização de planejamento não conclui

A Otimização do Planejamento requer um ambiente de alta disponibilidade habilitado para Lifecycle Services (LCS), camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior. Se você tentar instalar o suplemento em um ambiente de OneBox, a instalação não será concluída.

**Correção**: Cancele a instalação e use um ambiente de alta disponibilidade, nível 2 ou superior (não um ambiente Onebox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>O planejamento de trabalhos em lotes falha quando a otimização de planejamento é habilitada

Ao habilitar a otimização de planejamento, o mecanismo de planejamento mestre preterido é desabilitado automaticamente. Trabalhos em lotes de planejamento mestre criados para o mecanismo de planejamento mestre preterido falharão se forem disparados quando a Otimização de Planejamento estiver habilitada. Você pode receber uma mensagem de erro como *Esta operação disparou o planejamento mestre para o qual não há suporte quando a Otimização de Planejamento está habilitada*.

**Corrigir**: cancele todos os trabalhos de lote do planejamento mestre criados para o mecanismo de planejamento mestre preterido.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Os resultados da otimização de planejamento são diferentes dos resultados anteriores

A otimização do planejamento é diferente do design de mecanismo de planejamento mestre preterido em algumas áreas. Isso também pode ser causado por recursos pendentes.

**Correção**: execute a análise de ajuste da otimização do planejamento e analise os resultados enquanto consulta a documentação relacionada para compreender o impacto. Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>A Otimização de Planejamento pode ser habilitada

O **Status da conexão** deve ser **Conectado** antes que você possa definir **Usar otimização de planejamento** como **Sim**. Para obter mais informações, consulte [Introdução à Otimização de Planejamento](get-started.md).

**Correção**: verifique se o suplemento de Otimização de Planejamento foi instalado com êxito.

## <a name="error-message-is-shown-during-ctp"></a>A mensagem de erro é exibida durante o CTP

Se você tentar executar o CTP (capacidade de promessa) a partir de uma ordem de venda quando a Otimização do Planejamento estiver habilitada, você receberá a seguinte mensagem de erro: *Esta operação acionou o planejamento mestre que não tem suporte quando a Otimização de Planejamento está habilitada*.

Isso está relacionado a um recurso pendente que está planejado como parte do suporte para ordens de produção.

**Correção:** evite os cálculos do CTP quando a Otimização do Planejamento estiver habilitada até que o suporte do CTP esteja disponível.

## <a name="additional-resources"></a>Recursos adicionais

- [Introdução ao planejamento mestre](get-started.md)
- [Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]