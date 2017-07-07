---
title: "Contagem cíclica parcial do local"
description: "Os planos de contagem cíclica guiam as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 856ac2a61bc06a772b586a0cf77496fc360db623
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="partial-location-cycle-counting"></a>Contagem cíclica parcial do local

[!include[banner](../includes/banner.md)]


Os planos de contagem cíclica guiam as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local.

Ao usar os planos de contagem cíclica para criar o trabalho de contagem, você pode guiar as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local. Ao filtrar produtos específicos, o gerente do depósito pode reduzir custos indiretos de revisão, evitar erros de consolidação e economizar tempo.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Como configurar a contagem cíclica parcial do local
Quando você usa o processo de trabalho do depósito para operações de contagem, um cabeçalho de trabalho é criado para cada local. Quando você define o plano de contagem cíclica, você pode usar a consulta **Selecionar localizações** para limitar o trabalho de contagem cíclica criado. Ao selecionar produtos para o plano de contagem cíclica, você pode selecionar consultas de produto e de grade de produto para refinar o que é contado. 

Você pode associar um **modelo de trabalho** a um plano de contagem cíclica para definir como o trabalho de contagem cíclica deve ser criado. O modelo de trabalho para as operações de contagem refere-se diretamente ao plano de contagem cíclica. 

Ao definir os detalhes do modelo de trabalho, você pode usar a opção **Divisões de linha de trabalho** para especificar se as linhas de trabalho de contagem devem ser agrupadas por número de item ou por número de grade de produto. Esta configuração é necessária se você deseja contar o estoque disponível apenas para produtos específicos em um local. As linhas de trabalho de contagem cíclica criadas terão o nível de informação que você define aqui, e a operação de contagem guiada será tratada com base nesse nível. 

Se você associar planos de contagem cíclica a modelos de trabalho usando a opção **Divisões de linha de trabalho**, o campo **Contagem cíclica parcial** é selecionado para o trabalho de contagem cíclica criado, e várias linhas de trabalho de contagem cíclica serão criadas com base na definição do modelo de trabalho. 

Antes do trabalho de contagem cíclica parcial poder ser processado, você deve, no mínimo, selecionar **Exibir número do item** para o item de menu do dispositivo móvel como parte da configuração de contagem cíclica. Será solicitado ao operador de depósito que registre somente informações de contagem relacionadas às linhas de contagem (números de item e dimensões do produto). Qualquer outro estoque disponível será ignorado para esse processo de contagem. 

Referente ao processo de contagem cíclica parcial, a data/hora **Última contagem cíclica** não será atualizada para a localização.

## <a name="example"></a>Exemplo
Por exemplo, somente o item número A0001 deve ser contado no depósito 61.

1.  Um novo modelo de trabalho para contagem cíclica é criado. A opção **Divisões de linha de trabalho** é usada para agrupar linhas de trabalho de contagem por número de item. Portanto, o trabalho de contagem cíclica criado terá linhas por número de item. Você também pode agrupar as linhas por número de grade de produto.
2.  É criado um novo plano de contagem cíclica que faz referência ao modelo de trabalho recém-criado. O plano da contagem cíclica inclui todas as localizações no depósito 61 (consulta **Selecionar localizações**) que mantém o inventário para o item número A0001. A seleção de produtos específicos é definida na seção **Seleções de produtos de contagem cíclica**.
3.  Você pode selecionar produtos para planos de contagem cíclica definindo o campo **Locais vazios** como **Excluir vazios**. Quando o plano de contagem cíclica é processado, o trabalho de contagem cíclica parcial para o item número A0001 é criado. O processo de contagem real pode ser realizado usando um item de menu de dispositivo móvel para a contagem cíclica guiada.



<a name="see-also"></a>Consulte também
--------

[Contagem cíclica](cycle-counting.md)

