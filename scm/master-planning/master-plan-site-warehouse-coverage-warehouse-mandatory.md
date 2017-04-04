---
title: "Planejamento mestre o planejamento da cobertura de site e depósito, depósito obrigatório"
description: "Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito é obrigatória."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a0931d88f84544160803e42466575c02f47588a4
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Planejamento mestre o planejamento da cobertura de site e depósito, depósito obrigatório

Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito é obrigatória.

Este cenário de planejamento mestre envolve estas condições:

-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.
-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.
-   As dimensões do site e do depósito estão definidas como planejamento de cobertura. Outras dimensões também podem ser definidas como planejamento de cobertura. No entanto, elas não são afetadas pela funcionalidade multissite.

O gráfico a seguir ilustra como o planejamento mestre ocorre. Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:
-   The warehouse is set to **Manual**. Clique ** depósitos &gt; de divisão &gt; de estoque a configuração &gt; de gerenciamento de estoque. ** Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.
-   A cobertura de item é definida para o item. Clique ** produtos gerenciamento &gt; de informações&gt; sobre produtos liberou ** produto. Selecione o item e, depois, no painel de ações, ** plano ** na guia, clique ** ** cobertura de item.
-   As relações de reabastecimento são definidas para o depósito. Clique ** depósitos &gt; de divisão &gt; de estoque a configuração &gt; de gerenciamento de estoque. ** Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.
-   O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban. Clique ** produtos gerenciamento &gt; de informações&gt; sobre produtos liberou ** produto. Selecione o item e, depois, no painel de ações, ** plano ** na guia, clique ** padrão ** configurações de ordem. No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.

![Cobertura de demanda do depósito e do site, depósito obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Consulte também
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planejamento mestre - cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site, depósito não obrigatório](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planejamento mestre - cobertura de site e depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planejamento mestre – como a versão da BOM é determinada](master-plan-bom-version-determined.md)


