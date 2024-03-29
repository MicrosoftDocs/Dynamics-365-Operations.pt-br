---
title: Criar uma versão de fluxo de produção
description: Esse procedimento tem como foco a criação de uma versão de fluxo de produção.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b72d6162edd0ae6ccbfdcfe3e63ecff30528454
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569251"
---
# <a name="create-a-production-flow-version"></a>Criar uma versão de fluxo de produção

[!include [banner](../../includes/banner.md)]

Esse procedimento tem como foco a criação de uma versão de fluxo de produção. Nesse procedimento, os parâmetros de produção para lean manufacturing e as unidades de medida para tempo de classe devem ser definidos. Também pode ser necessário definir um fluxo de valor e um perfil de produção. Para saber mais sobre fluxos e atividades de produção em lean manufacturing, consulte os white papers a respeito de Lean manufacturing para Microsoft Dynamics AX. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-production-flow"></a>Criar um fluxo de produção
1. Acesse Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Nome, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
    * Selecione uma unidade operacional de fluxo de valor de tipo. O fluxo de valor é uma unidade operacional que abrange todos os fluxos e atividades do fluxo de valor. Nessa fase, as unidades operacionais se limitam a uma entidade legal e não apresentam funcionalidade adicional.  
7. No campo Perfil de produção, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
    * Selecione um perfil de produção para o fluxo de produção. Perfis de produção permitem a definição de material, trabalho e contas WIP para um processo de produção. Para associar o contexto de contabilidade a um fluxo de produção, um perfil de produção deve ser selecionado.  
9. Clique em Salvar.

## <a name="create-a-production-flow-version"></a>Criar uma versão de fluxo de produção
1. Clique em Adicionar.
2. No campo Data de vencimento, insira uma data e hora.
    * Se necessário, defina uma data de vencimento para a versão. É possível atualizá-la a qualquer momento, mesmo para versões ativas. É possível usá-la para planejar a retirada gradual de uma versão.  
3. Clique em OK.
4. Na lista, marque a linha selecionada.
5. No campo Unidade, digite um valor.
6. Resolver altera a unidade Takt.
7. No campo Takt time médio, insira um número.
    * Defina o takt time médio da versão. Para o controle de takt da versão do fluxo de produção, defina um takt time médio de destino. O takt é definido como quantidade por período de tempo. No exemplo, o takt time é 0,2 horas por 10 unidades. Para um tempo de trabalho de 8 horas, isso corresponde a uma capacidade de produtividade diária de 400 unidades.  
8. No campo Quantidade por ciclo, insira um número.
    * Defina a quantidade por ciclo relacionada ao takt time médio.  
9. Alterne a expansão da seção Detalhes da versão.
10. No campo Takt time mínimo, insira um número.
    * Defina o takt time mínimo. O takt time mínimo deve ser menor que ou igual ao takt time médio.  
11. No campo Takt time máximo, insira um número.
    * O takt time máximo deve ser maior que ou igual ao takt time médio.  
12. No campo Período para tempo de ciclo real (dias), insira um número.
    * Insira o número de dias no Período para tempo de ciclo real. O período para tempo de ciclo real é o número de dias em que os trabalhos são agregados do minuto real regressivamente para calcular o tempo de ciclo real. O valor pode ser alterado a qualquer momento e só é usado para o cálculo dos tempos de ciclo reais.  
13. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]