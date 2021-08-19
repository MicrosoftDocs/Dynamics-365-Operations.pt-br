---
title: 'Criar relação de atividade: Sucessor'
description: O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea5e7c145b2daf1e9c0afdb64c865e9fbfee3e5578edc24538e077ef4e83fe34
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717044"
---
# <a name="create-activity-relation---successor"></a>Criar relação de atividade: Sucessor

[!include [banner](../../includes/banner.md)]

O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade. O registro mostra como criar uma relação de atividade.

Pré-requisitos:

- Uma versão e um fluxo de produção no modo de rascunho. 

- Duas atividades sucessivas no fluxo de produção são criadas mas não relacionadas.


## <a name="find-the-production-flow-version"></a>Localizar a versão do fluxo de produção 
1. Acesse Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Na lista, marque a linha selecionada.
5. Na lista, selecione uma versão de rascunho.
    * Relacionamentos de atividade podem ser adicionados a versões de rascunho ou ativas de um fluxo de produção.  

## <a name="open-the-activity-overview"></a>Abrir a visão geral da atividade
1. Clique em Atividades.
    * Observe que o formulário mostra todas as atividades do fluxo de produção que estão alocadas para a versão dos fluxos de produção nos quais você está trabalhando.  

## <a name="add-a-successor"></a>Adicionar um sucessor
1. Clique em Adicionar sucessor.
2. No campo Atividade, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. Marque a caixa de seleção Restrição.
6. No campo Valor de restrição, insira um número.
    * O horário de restrição é o horário que será agendado entre o final agendado do predecessor (data e horário de vencimento) e o início agendado do predecessor.  
7. No campo Unidades, digite um valor.
8. No campo Razão do tempo de ciclo, insira um número.
    * Se ambas as atividades forem executadas no mesmo takt, a razão do tempo de ciclo deverá ser 1. Se o antecessor for executado com o dobro da velocidade do sucessor, a razão deverá ser 2.   As razões do tempo de ciclo são usadas para calcular os tempos de ciclo individuais das atividades do fluxo de produção.  
9. Clique em OK.
10. Feche a página.
11. Clique na guia GridPanel.
12. Feche a página.
13. Atualize a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]