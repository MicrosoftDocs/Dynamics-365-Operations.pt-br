---
title: Gerar um plano restrito
description: Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c35d5a7465cc6cfe0bc12cb00796eff2aeed1ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808007"
---
# <a name="generate-a-constrained-plan"></a>Gerar um plano restrito

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade. O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados. 

A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o planejador de produção.


## <a name="set-up-a-constrained-plan"></a>Configurar um plano restrito
1. Na página inicial, selecione o espaço de trabalho **Planejamento mestre**.
2. Selecione **Planos mestres** na lista de links no lado direito da área de trabalho.
3. Na lista, localize e selecione o registro desejado. Exemplo: **StaticPlan**  
4. Selecione **Sim** no campo **Capacidade finita**.
5. No campo **Limite de tempo de capacidade finita**, insira `30`.
6. Expanda a seção **Limites de tempo em dias**.
7. Selecione **Sim** no campo **Capacidade**.
8. No campo **Limite de tempo de agendamento de capacidade (dias)**, insira um número. Exemplo: `60`  
9. Selecione **Sim** no campo **Atrasos calculados**.
10. No campo **Calcular limite de tempo para atrasos (dias)**, insira um número. Exemplo: `60` 
11. Expanda a seção **Atrasos calculados**.
12. Selecione **Sim** em todos os campos **Adicionar o atraso calculado à data da requisição**.
13. Feche a página.

## <a name="create-a-constrained-plan"></a>Criar um plano restrito
1. Selecione **Executar**.
2. No campo **Plano mestre**, insira ou selecione o plano para o qual você configurou restrições.  
3. Selecione **OK**.
4. Selecione **Ordens planejadas**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]