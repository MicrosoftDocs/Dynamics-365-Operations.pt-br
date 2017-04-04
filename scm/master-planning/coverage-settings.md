---
title: "Configurações de cobertura"
description: "O planejamento mestre usa configurações de cobertura para calcular requisitos de itens."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c1c5654afa6b592e178af052e3e4a7e246a94c9f
ms.lasthandoff: 03/31/2017


---

# <a name="coverage-settings"></a>Configurações de cobertura

O planejamento mestre usa configurações de cobertura para calcular requisitos de itens. 

Você pode especificar as configurações de cobertura de várias formas:

-   Especifique as configurações de cobertura para um grupo de cobertura. Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura. Clique ** mestres &gt; grupos de cobertura &gt; de &gt; cobertura de configuração de planejamento ** para criar um grupo de cobertura. Você pode vincular um grupo de cobertura a um produto. Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**. Se o link for genérico, independentemente das dimensões do produto, use o **Grupo de cobertura** na Guia Rápida **Plano** na página **Detalhes do produto** Se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará como padrão o **Grupo de cobertura geral** especificado nos **Parâmetros de planejamento mestre** como o padrão.

-   Especificar configurações de cobertura para um produto. Você pode criar configurações de cobertura para um produto específico. Clique ** produtos gerenciamento &gt; de informações &gt; sobre produtos liberou ** produto. Selecione o produto, no painel ** ações **, o plano ** ** ** guia, o grupo de cobertura, clique ** ** cobertura de item para abrir ** ** cobertura de item ** a página. Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**. As configurações de cobertura na página** Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.

<!-- -->

-   Especificar as configurações de cobertura para um produto usando um assistente. O assistente é um guia passo a passo que o ajuda a configurar os parâmetros principais de cobertura de item. Na página **Cobertura de item**, clique em **Assistente** para abrir o **Assistente de Cobertura de Item**.

<!-- -->

-   Especifique as configurações de cobertura para um grupo de dimensões. Clique ** comum gerenciamento &gt; de informações &gt; sobre produtos liberou ** produto. ** Em detalhe ** liberado página de produto, em ** ** guia geral, administração ** ** no grupo, clique ** grupo de dimensão de armazenamento ** o link. Na página **Grupo de dimensões de armazenamento**, selecione o campo **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento. As dimensões de produtos, como preparação, colorem, dimensões, denominam, devem ter ** plano de cobertura por dimensão ** o campo selecionado.



<a name="see-also"></a>Consulte também
--------

[Master plans](master-plans.md)


