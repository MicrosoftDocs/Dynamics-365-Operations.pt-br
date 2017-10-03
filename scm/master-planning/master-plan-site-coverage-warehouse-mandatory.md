---
title: "Planejamento mestre para cobertura de site, depósito obrigatório"
description: "Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado. O depósito é a dimensão obrigatória."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a1bf8f2253c63e4b6ca8fee02ec6b1cfb8aad73c
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planejamento mestre para cobertura de site, depósito obrigatório

[!include[banner](../includes/banner.md)]


Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado. O depósito é a dimensão obrigatória.

Este cenário de planejamento mestre envolve estas condições:

-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda. Essa configuração não pode ser modificada.
-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.
-   A dimensão do site está definida como planejamento de cobertura. Outras dimensões também podem ser definidas como planejamento de cobertura. No entanto, elas não são afetadas pela funcionalidade multissite.
-   A dimensão do depósito não está definida como planejamento de cobertura. Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).

O gráfico a seguir ilustra como o planejamento mestre ocorre. Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:
-   A cobertura de item é definida para o item. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item e então clique em **Planejar &gt; Cobertura de item**.
-   As relações de reabastecimento são definidas para o depósito. Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**. Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .
-   O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**. No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.

![Demanda para cobertura de site, depósito obrigatório](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Consulte também
--------

[Planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)

[Planejamento mestre - cobertura de site e depósito, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site e depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planejamento mestre – como a versão da BOM é determinada](master-plan-bom-version-determined.md)




