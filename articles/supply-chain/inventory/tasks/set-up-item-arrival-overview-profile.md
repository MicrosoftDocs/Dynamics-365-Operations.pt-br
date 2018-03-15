---
title: "Configurar um perfil de visão geral de entradas de item"
description: "Essa tarefa se concentra na configuração de um perfil de visão geral de entradas."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5ddc491d73bbb6ac02e37a9c9b9d93545f6f9556
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a>Configurar um perfil de visão geral de entradas de item

[!include[task guide banner](../../includes/task-guide-banner.md)]

Essa tarefa se concentra na configuração de um perfil de visão geral de entradas. O perfil de visão geral de entradas é um conjunto de regras que serão aplicadas quando a página de Visão geral de entradas for aberta por um usuário. Você pode usar este procedimento na empresa USMF de dados de demonstração. Este procedimento será geralmente executado por um auxiliar de recebimento.





1. Vá para Gerenciamento de estoque > Configuração > Distribuição > Perfis de visão geral de entradas.
2. Clique em Novo.
    * Considerando que você quase sempre irá trabalhar no mesmo depósito descarregando cargas de caminhões, você deve criar uma visão geral das chegadas para simplificar o processo de registro de itens recebidos.  
3. No campo Nome do perfil de visão geral de entradas, digite um valor.
4. No campo Mostrar linhas, selecione uma opção.
    * Selecione quais linhas dos recebimentos serão mostradas: Todas – mostra todas as linhas, independente do status.   Em andamento – Mostra as linhas dos recebimentos em que o progresso está Concluído ou Parcial. Isso significa que, para cada linha, toda a quantidade ou parte dela foi registrada em um diário de entrada.   Não concluído – Mostra as linhas de recebimentos em que o processo está Nenhum ou Parcial. Isso significa que, para cada linha, nada ou somente parte da quantidade foi registrada em um diário de entrada.  
5. Expanda ou recolha a seção Opções de entrada.
6. No campo Dias à frente, digite um valor.
    * Isso definirá um filtro para mostrar as linhas de recebimento esperadas para o recebimento nos próximos dias (dependendo do número que você definiu).  
7. No campo Dias atrás, digite um valor.
    * Isso definirá um filtro para mostrar as linhas de recebimento esperadas para o recebimento a alguns dias atrás.  
8. No campo Depósito, digite um valor.
    * Filtrar um ou mais depósitos.  
9. No campo Modo de entrega, selecione um valor.
    * Isso definirá um filtro para mostrar apenas as linhas de recebimento com esse Modo de entrega.  
10. No campo Nome, selecione WHS.
11. No campo Depósito, selecione o depósito 24.
    * Este é o depósito padrão que será usado para as linhas de recebimento registradas que usam este perfil.  
12. No campo Local, selecione Baydoor.
    * Esta é a localização padrão que será usada para as linhas de recebimento registradas que usam este perfil.  
13. Expanda ou recolha a seção Detalhes da consulta de entrada.
14. No campo Restringir ao local, selecione o local 2.
    * Isso definirá um filtro para mostrar apenas as linhas de recebimento com esse local.  
15. Defina a opção Ordens de compra como Sim.
    * Selecione as linhas de recebimento das ordens de compra.  
16. Defina a opção Ordens de transferência como Sim.
    * Selecione as linhas de recebimento das ordens de transferência.  
17. Clique em Salvar.
18. Feche a página.

