--- 
title: "Criar relação de atividade: Sucessor"
description: "O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 5ac47a00a8eb40658af54274ce1d80349ec23d1e
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="create-activity-relation-successor"></a>Criar relação de atividade: Sucessor

[!include[task guide banner](../../includes/task-guide-banner.md)]

O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade. O registro mostra como criar uma relação de atividade.

Pré-requisitos:

- Uma versão e um fluxo de produção no modo de rascunho. 

- Duas atividades sucessivas no fluxo de produção são criadas mas não relacionadas.


## <a name="find-the-production-flow-version"></a>Localizar a versão do fluxo de produção 
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
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


