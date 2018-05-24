---
title: "Configurações de cobertura"
description: "O planejamento mestre usa configurações de cobertura para calcular requisitos de itens."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 858328ec60e0ffa5ca46a98b365fb0fc599ae1f0
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="coverage-settings"></a>Configurações de cobertura

[!include [banner](../includes/banner.md)]

O planejamento mestre usa configurações de cobertura para calcular requisitos de itens. 

Você pode especificar as configurações de cobertura de várias formas:

-   Especifique as configurações de cobertura para um grupo de cobertura. Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura. Clique em **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura** para criar um grupo de cobertura. Você pode vincular um grupo de cobertura a um produto. Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**. Se o link for genérico, independentemente das dimensões do produto, use o **Grupo de cobertura** na Guia Rápida **Plano** na página **Detalhes do produto** Se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará como padrão o **Grupo de cobertura geral** especificado nos **Parâmetros de planejamento mestre** como o padrão.

-   Especificar configurações de cobertura para um produto. Você pode criar configurações de cobertura para um produto específico. Clique em **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**. Selecione o produto, no **Painel de Ação**, na guia **Plano**, no **Grupo de cobertura**, clique em **Cobertura de item** para abrir a página **Cobertura de item**. Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**. As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.

<!-- -->

-   Especificar as configurações de cobertura para um produto usando um assistente. O assistente é um guia passo a passo que o ajuda a configurar os parâmetros principais de cobertura de item. Na página **Cobertura de item**, clique em **Assistente** para abrir o **Assistente de Cobertura de Item**.

<!-- -->

- Especifique as configurações de cobertura para um grupo de dimensões. Clique em **Gerenciamento de informações do produto &gt; Comum &gt; Produtos liberados**. Na página **Detalhes do produto liberado**, na guia **Geral**, no grupo **Administração**, clique no link **Grupo de dimensões de armazenamento**. Na página **Grupo de dimensões de armazenamento**, selecione o campo **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento. Todas as dimensões do produto, como a configuração, a cor, o tamanho, o estilo devem ter o campo **Plano de cobertura por dimensão** selecionado.



<a name="additional-resources"></a>Recursos adicionais
--------

[Planos mestres](master-plans.md)




