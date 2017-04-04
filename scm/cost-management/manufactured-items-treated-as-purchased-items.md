---
title: "Produtos de instalação que podem ser produzidos ou obtido"
description: "O produto podem ser originários em várias formas - podem ser gerados () ou fabricado (comprado ser obtido.) Este artigo descreve alguns pontos típicos a serem considerados quando você configura produtos para oferecer suporte de várias fontes."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5360c7b1475763b8e33205bff560393e9ee51882
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-products-that-can-be-produced-or-procured"></a>Produtos de instalação que podem ser produzidos ou obtido

O produto podem ser originários em várias formas - podem ser gerados () ou fabricado (comprado ser obtido.) Este artigo descreve alguns pontos típicos a serem considerados quando você configura produtos para oferecer suporte de várias fontes. 

Várias fontes geralmente são usadas para um item comprado que é fabricado ocasionalmente, ou quando um item que era um item fabricado é alterado, de forma que agora seja um item comprado. O item primeiro é designado como item fabricado para definir se as informações sobre a lista de materiais (BOM) e sobre o roteiro podem ser definidas, e para dar suporte a ordens de produção do item. O tipo de produção deve ser definido como **BOM** (ou, para processo de fabricação, **Fórmula** ou **Coproduto**).

Quando você usa custo padrão, o registro de custo do item pode ser calculado para o item fabricado. No entanto, o registro de custo do item pode não corresponder ao custo padrão que você deseja para fins de compra. Neste caso, o custo padrão deve ser inserido manualmente e ativado para o registro de custo do item. Para o cálculo do custo, use uma BOM e roteiro especiais que representem a combinação da fonte de produtos ao longo de um período fiscal, para minimizar as variações ao longo do tempo. Além disso, um item fabricado em um site pode ser transferido para outro site. Portanto, o custo do item deve ser inserido e ativado manualmente no site para o qual o item será transferido. Quando você usa um item fabricado como um componente em produtos de alto nível, os custos do componente devem ser tratados como um item comprado. Esta diretriz é aplicada, independentemente de os custos do componente serem calculados ou inseridos manualmente. Em outras palavras, um cálculo de BOM deve tratar os custos do item como um componente comprado, em vez de usar informações de roteiro e de BOM do item para calcular custos. Para impedir o cálculo, selecione o sinalizador **Parar detalhamento** que é incorporado no grupo de cálculo de BOM atribuído ao item. Para impedir que os cálculos de planejamento mestre detalhem os requisitos no item, defina o limite de detalhamento para 0 (zero) dias na cobertura do item ou no grupo de cobertura. O cálculo do agendamento mestre tratará o item como comprado e não executará mais cálculos para as informações de roteiro e de BOM do item.




