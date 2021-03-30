---
title: Criar um plano para um site
description: O planejador de produção calcula os requisitos de capacidade e de material para a produção de um item específico.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5ef805ba42500175d29208f1dcd5d383c63adb8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214337"
---
# <a name="create-a-plan-for-a-site"></a>Criar um plano para um site

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]