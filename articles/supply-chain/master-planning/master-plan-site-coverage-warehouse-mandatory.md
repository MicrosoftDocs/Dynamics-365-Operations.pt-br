---
title: Planejamento mestre para cobertura de site, depósito obrigatório
description: Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado. O depósito é a dimensão obrigatória.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 008061d286505a2e678e15fbff7706da9c410dfe
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187545"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planejamento mestre para cobertura de site, depósito obrigatório

[!include [banner](../includes/banner.md)]

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

![Demanda para cobertura de site, depósito obrigatório    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)

[Planejamento mestre para de site e cobertura de depósito, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre para cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Determinar a versão da BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]