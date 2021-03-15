---
title: Gerar um plano restrito
description: Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4af946a8dd4e5311bcb90386c88d5e7f205c4eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999847"
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