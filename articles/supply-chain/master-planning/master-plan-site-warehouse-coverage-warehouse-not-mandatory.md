---
title: Planejamento mestre para cobertura de site e depósito, depósito não obrigatório
description: Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito não é obrigatória.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8350646e70c7ea7d705a69ecb52f389e829a0fc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833464"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planejamento mestre para cobertura de site e depósito, depósito não obrigatório

[!include [banner](../includes/banner.md)]

Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito não é obrigatória.

Este cenário de planejamento mestre envolve estas condições:

-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda. Essa configuração não pode ser modificada.
-   A dimensão do depósito não está definida como obrigatória. O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.
-   As dimensões do site e do depósito estão definidas como planejamento de cobertura. Outras dimensões também podem ser definidas como planejamento de cobertura. No entanto, elas não são afetadas pela funcionalidade multissite.

O gráfico a seguir ilustra como o planejamento mestre ocorre. Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:
-   O depósito está definido como Manual. Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**. Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.
-   A cobertura de item é definida para o item. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item, e depois, no Painel de Ações, na guia **Plano**, clique em **Cobertura de item**.
-   As relações de reabastecimento são definidas para o depósito. Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**. Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.
-   O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item e, no Painel de Ações, na guia **Plano**, clique em **Configurações de ordem padrão**. No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.

![Demanda para site e depósito, depósito não obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)

[Planejamento mestre para cobertura de site, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre para de site e cobertura de depósito, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório](master-plan-site-coverage-warehouse-not-mandatory.md)

[Determinar a versão da BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]