--- 
title: "Criar e atribuir estruturas de regras avançadas"
description: "Este guia de tarefas aborda a criação e atribuição de uma estrutura de regra avançada a uma estrutura de conta."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7c38debf005cf14176a5184c489242e914c1ff4c
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-advanced-rule-structures"></a>Criar e atribuir estruturas de regras avançadas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefas aborda a criação e atribuição de uma estrutura de regra avançada a uma estrutura de conta. Este guia usa a empresa de demonstração USMF.


## <a name="create-an-advanced-rule-structure"></a>Criar estrutura de regras avançada
1. Vá para Contabilidade > Plano de contas > Estruturas > Estruturas de regra avançada.
2. Clique em Novo para abrir a caixa de diálogo suspensa.
3. No campo Estrutura de regra avançada, digite um nome para descrever a estrutura da regra.
4. No campo Descrição, digite um valor para descrever a estrutura.
5. Clique em OK.
6. Clique em Adicionar segmento.
7. Na lista de segmentos, selecione uma dimensão financeira.
    * Por exemplo, Loja.  
8. Clique em Adicionar segmento.
9. Na lista, clique no link da estrutura de regra avançada para exibi-la.
10. Clique em Ativar.
11. Clique em Ativar.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Aplicar estrutura de regra avançada a uma estrutura de conta
1. Feche o formulário.
2. Feche a página.
3. Vá para Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta.
4. Na lista, localize e selecione a estrutura de conta à qual deseja aplicar a regra avançada.
5. Clique no nome da estrutura de conta para abri-la.
6. Clique em Editar.
    * Você também pode clicar em Regras avançadas, e será solicitado que você coloque a estrutura de conta no modo de rascunho.  
7. Clique em Regras avançadas.
8. Clique em Novo para abrir a caixa de diálogo suspensa.
9. No campo Regra avançada, digite um valor.
10. No campo Nome, digite um valor.
11. Clique em Criar.
12. Clique em Adicionar novos critérios.
13. No campo Onde, selecione uma conta principal ou uma dimensão financeira.
14. No campo Operador, selecione uma opção, como está entre e inclui.
15. No campo Valor, digite um valor.
16. No campo por meio de, digite um valor.
17. Clique em Adicionar para abrir a caixa de diálogo suspensa.
18. Na lista, localize a estrutura de regra avançada que deseja usar quando os critérios inseridos forem atendidos.
19. Clique em Adicionar.
20. Feche a página.
21. Clique em Ativar.
22. Clique em Ativar.

