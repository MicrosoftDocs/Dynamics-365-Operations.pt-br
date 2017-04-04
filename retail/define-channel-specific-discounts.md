---
title: "Definir descontos específicos do canal"
description: "Os fornecedores geralmente definem descontos diferentes em canais diferentes. Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Definir descontos específicos do canal

Os fornecedores geralmente definem descontos diferentes em canais diferentes. Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico. 

<a name="channel-specific-discounts"></a>Descontos específicos do canal
--------------------------

Os fornecedores geralmente oferecem descontos diferentes nos canais diferentes. Isso é possível ser feito para atender a condições locais marketing ou para manusear fornecedores concorrentes.

Varejo e comércio no Microsoft Dynamics 365 para os grupos de preços a usa operações canal- definam descontos específicos. Grupos de preços podem ser atribuídos a uma ou mais das seguintes entidades: canais, catálogos, afiliações e programas de fidelidade. Este artigo aborda canais, mas os mesmos conceitos se aplicam a descontos de catálogo, descontos de afiliações e descontos de fidelidade.

## <a name="price-groups"></a>Grupos de preços
alignnone” width= " 640 "align= " label " id= de legenda\[anexo\_256084 "\][grupos de preços do![(]. /media/price-groups-1024x608.png)](. O grupo de preços em /media/price-groups.png) de varejo vincula\[/caption\]

O diagrama acima ilustra a relação entre entidades que podem estar em uma transação (canal, catálogo, associação, cliente, cartão-fidelidade) e em vários tipos de descontos que podem ser configurados. Todas as transações físicas ocorrerem em um canal, o canal é garantido estiver presente em uma transação. As demais entidades são opcionais. Em cada página de dados mestres, há um link para uma página de grupos de preços relacionada na qual é possível ver e adicionar grupos de preços quando necessário. Um grupo de preços é usado para relacionar quatro tipos de entidades diferentes para os descontos, a ajustes, de preço e contratos comerciais. Recomendamos que você planeja uma estratégia de como você nomeará os grupos de preços a manter organizados. Para usar um padrão ou uma letra numerar o prefixo ou sufixo para diferenciar entre diferentes tipos. Por exemplo, 1 xxxxx para grupos de preços de canal e 2 xxxxx para grupos de preço de catálogo. Há quatro páginas de consulta com foco em cada uma das entidades de varejo que podem ter descontos associados a elas.

-   **Grupos de preços do canal de varejo **- Essa página mostra uma lista de canais e descontos vinculados entre si para cada grupo de preço.
-   **Grupos de preços de catálogo **- Essa página mostra uma lista de catálogos e descontos vinculados entre si para cada grupo de preço.
-   **Grupos de preços de fidelidade **- Essa página mostra uma lista de programas de fidelidade e descontos vinculados entre si para cada grupo de preço.
-   **Grupos de preços de afiliação **- Essa página mostra uma lista de afiliações e descontos vinculados entre si para cada grupo de preço.

## <a name="example-channel-discount-set-up"></a>Exemplo de configuração de desconto de canal
O exemplo a seguir ilustra as tarefas envolvidas na configuração de um desconto de canal.

1.  No exemplo, você tem um canal denominado **Houston** e criará um desconto denominado **Volta à escola**.
2.  Como a estratégia de preços e descontos inclui a possibilidade de descontos de canal, você sempre criará um grupo de preços específico do canal quando criar um canal.
3.  Você tem o grupo de preços **Houston-PG** que é atribuído ao canal **Houston**.
4.  Após a criação do desconto **Volta à escola**, você precisa clicar em **Grupos de preços** na parte superior da página **Desconto**. A página **Grupos de preços de desconto** será aberta. Em seguida, clique em **Novo** e selecione o grupo de preços **Houston-GP**.
5.  Agora você pode habilitar o desconto e enviá-lo por push ao canal.

 

<a name="see-also"></a>Consulte também
--------

[Price adjustments and discounts](price-adjustments-discounts.md)


