--- 
title: Criar um plano para um site
description: "O planejador de produção calcula os requisitos de capacidade e de material para a produção de um item específico."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d89d34d4d429faf87c70943961f7141a6258d482
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-plan-for-a-site"></a>Criar um plano para um site

[!include[task guide banner](../../includes/task-guide-banner.md)]

O planejador de produção calcula os requisitos de capacidade e de material para a produção de um item específico. Depois que as indicações de fornecimento são criadas, ele encontra as ordens no site para o qual ele está planejando e confirma ordens a partir de ordens urgentes. As ordens mais urgentes são aquelas que precisam ser confirmadas na data atual. Use a empresa USMF de dados de demonstração para executar essas tarefas.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Criar materiais e planejamento de capacidade para um item
1. Clique em Planejamento mestre.
    * Você precisa navegar para o Painel padrão.  
2. Clique em Executar.
3. Expanda os Registros para incluir a seção.
4. Clique em Filtro.
5. Na lista, marque a linha selecionada.
6. No campo Critérios, digite um valor.
    * Exemplo: D0001  
7. Clique em OK.
8. Clique em OK.
    * Isso pode levar alguns minutos.  
9. Atualize a página.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identificar as ordens urgentes planejadas para o item
1. Abra o filtro na coluna do número do item.
2. Aplicar um filtro no campo "Número de item", com um valor de "D0001", usando o operador de filtro "começa com".
3. Filtro de coluna de data Abrir ordem.
4. Aplicar um filtro no campo "Data da ordem", com um valor de data atual, usando o operador de filtro "é exatamente".

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Confirmar as ordens urgentes para o item
1. Na lista, marque ou desmarque todas as linhas.
2. Clique em Confirmar.
3. Clique em OK.


