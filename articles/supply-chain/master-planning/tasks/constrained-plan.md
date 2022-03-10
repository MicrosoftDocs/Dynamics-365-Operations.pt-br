---
title: Gerar um plano restrito
description: Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ChristianRytt
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fea315d41d01cb578d7d60c9eb7006e4b6c3362
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578335"
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