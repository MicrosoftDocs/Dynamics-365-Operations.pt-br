---
title: ​Configurações de cobertura​
description: Este tópico fornece informações sobre as configurações de cobertura que o agendamento do planejamento mestre usa para calcular os requisitos do item.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538885"
---
# <a name="coverage-settings"></a>​Configurações de cobertura​

[!include [banner](../includes/banner.md)]

O planejamento mestre usa configurações de cobertura para calcular requisitos de itens.

Você pode especificar as configurações de cobertura de várias formas:

- Especifique as configurações de cobertura para um grupo de cobertura.

    Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura. Para criar um grupo de cobertura, vá para **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura**. Você pode vincular um grupo de cobertura a um produto. Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**. Se o link for genérico, independentemente das dimensões do produto, use o campo **Grupo de cobertura** na Guia Rápida **Plano** da página **Detalhes do produto** Por padrão, se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará o grupo de cobertura geral especificado na página **Parâmetros de planejamento mestre**.

- Especificar configurações de cobertura para um produto.

    Você pode criar configurações de cobertura para um produto específico. Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**. Selecione o produto e, no Painel de Ação, na guia **Plano**, no grupo **Cobertura**, selecione **Cobertura de item** para abrir a página **Cobertura de item**. Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**. As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.

- Especificar as configurações de cobertura para um produto usando um assistente.

    O assistente guia você passo a passo ao longo do processo de configuração dos principais parâmetros de cobertura do item. Na página **Cobertura de item**, no Painel de Ação, selecione **Assistente** para abrir o **Assistente de Cobertura de Item**.

- Especifique as configurações de cobertura para um grupo de dimensões.

    Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**. Na página **Detalhes do produto liberado**, na Guia Rápida **Geral**, na seção **Administração**, selecione o link no campo **Grupo de dimensões de armazenamento**. Na página **Grupos de dimensões de armazenamento**, marque a caixa de seleção **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento. O campo **Plano de cobertura por dimensão** deve ser selecionado para todas as dimensões do produto, como configuração, cor, tamanho e estilo.

## <a name="additional-resources"></a>Recursos adicionais

[Planos mestres](master-plans.md)
