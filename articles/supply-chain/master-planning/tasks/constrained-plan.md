--- 
title: Gerar um plano restrito
description: "Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a>Gerar um plano restrito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade. O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados. 

A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o planejador de produção.


## <a name="set-up-a-constrained-plan"></a>Configurar um plano restrito
1. Clique em Planejamento mestre.
2. Clique em Planos mestre.
3. Na lista, localize e selecione o PDV desejado.
    * Exemplo: StaticPlan  
4. Selecione Sim no campo da capacidade finita.
5. No tempo limite da Capacidade finita, insira '30'.
6. Expanda os limites de tempo na seção de dias.
7. Selecione Sim no campo da Capacidade.
8. No tempo limite de programação de capacidade (dias), insira um número.
    * Exemplo 60  
9. Selecione Sim no campo Atrasos calculados.
10. No tempo limite de Atrasos calculados (dias), insira um número.
    * Exemplo 60  
11. Expanda a seção de atrasos calculada.
12. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
13. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
14. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
15. Feche a página.

## <a name="create-a-constrained-plan"></a>Criar um plano restrito
1. Clique em Executar.
2. No campo Plano mestre, insira ou selecione um valor.
    * Selecione o plano para o qual você configurou restrições.  
3. Clique em OK.
    * Isso pode levar algum tempo.  
4. Clique em Ordens planejadas.


