---
title: "Planejamento mestre para cobertura de site, depósito não obrigatório"
description: "Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado."
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 79582e92daeaf0afb032448d36be12edd0926089
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Planejamento mestre para cobertura de site, depósito não obrigatório

[!include[banner](../includes/banner.md)]


Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado.

Este cenário de planejamento mestre envolve estas condições:

-   A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.
-   A dimensão do depósito não está definida como obrigatória. O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.
-   A dimensão do site está definida como planejamento de cobertura.
-   A dimensão do depósito não está definida como planejamento de cobertura. Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).

O gráfico a seguir ilustra como o planejamento mestre ocorre. Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:
-   A cobertura de item é definida para o item. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item e então clique em **Planejar &gt; Cobertura de item**.
-   As relações de reabastecimento são definidas para o depósito. Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**. Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .
-   O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban. Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**. Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**. No formulário **Configurações de ordem padrão**, veja o campo **Tipo de ordem padrão**.

![Demanda para cobertura de site, depósito não obrigatório    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a>Consulte também
--------

[Planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)

[Planejamento mestre - cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site e depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planejamento mestre - cobertura de site e depósito, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre – como a versão da BOM é determinada](master-plan-bom-version-determined.md)




