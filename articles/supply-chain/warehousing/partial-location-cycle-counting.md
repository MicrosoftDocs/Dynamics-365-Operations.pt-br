---
title: Contagem cíclica parcial do local
description: Os planos de contagem cíclica guiam as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable, WHSRFMenuItemCycleCount, WHSCycleCountPlanListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a541818a72f5c24db8784071f447c83a2aa4edfd
ms.sourcegitcommit: 95f90ac3f248716abdab16d5de6ccbf059616e4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666737"
---
# <a name="partial-location-cycle-counting"></a>Contagem cíclica parcial do local

[!include [banner](../includes/banner.md)]

Os planos de contagem cíclica guiam as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local.

Ao usar os planos de contagem cíclica para criar o trabalho de contagem, você pode guiar as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local. Ao filtrar produtos específicos, o gerente do depósito pode reduzir custos indiretos de revisão, evitar erros de consolidação e economizar tempo.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Como configurar a contagem cíclica parcial do local

Quando você usa o processo de trabalho do depósito para operações de contagem, um cabeçalho de trabalho é criado para cada local. Quando você define o plano de contagem cíclica, você pode usar a consulta **Selecionar localizações** para limitar o trabalho de contagem cíclica criado. Ao selecionar produtos para o plano de contagem cíclica, você pode selecionar consultas de produto e de grade de produto para refinar o que é contado.

Você pode associar um **modelo de trabalho** a um plano de contagem cíclica para definir como o trabalho de contagem cíclica deve ser criado. O modelo de trabalho para as operações de contagem refere-se diretamente ao plano de contagem cíclica.

Ao definir os detalhes do modelo de trabalho, você pode usar a opção **Divisões de linha de trabalho** para especificar se as linhas de trabalho de contagem devem ser agrupadas por número de item ou por número de grade de produto. Esta configuração é necessária se você deseja contar o estoque disponível apenas para produtos específicos em um local. As linhas de trabalho de contagem cíclica criadas terão o nível de informação que você define aqui, e a operação de contagem guiada será tratada com base nesse nível.

Se você associar planos de contagem cíclica a modelos de trabalho usando a opção **Divisões de linha de trabalho**, o campo **Contagem cíclica parcial** é selecionado para o trabalho de contagem cíclica criado, e várias linhas de trabalho de contagem cíclica serão criadas com base na definição do modelo de trabalho.

Antes do trabalho de contagem cíclica parcial poder ser processado, você deve, no mínimo, selecionar **Exibir número do item** para o item de menu do dispositivo móvel como parte da configuração de contagem cíclica. Será solicitado ao operador de depósito que registre somente informações de contagem relacionadas às linhas de contagem (números de item e dimensões do produto). Qualquer outro estoque disponível será ignorado para esse processo de contagem.

Para o processo de contagem do ciclo parcial, a data ou a hora da **Contagem do último ciclo** não será atualizada para a localização, mesmo que todos os itens disponíveis em um determinado local sejam contados. A contagem do ciclo parcial não considera o parâmetro **Dias entre a contagem cíclica** na página **Planos de contagem cíclica**. A contagem de ciclos parciais não oferece suporte à contagem simultânea de vários itens no mesmo local. A funcionalidade de contagem de ciclos parciais pode resultar no mesmo local contado várias vezes para um item quando o **Plano de contagem cíclica do processo** é executado. Para evitar esse cenário, especifique filtros no campo **Selecionar locais**.

> [!NOTE]
> O aplicativo de depósito não fornece o botão **Adicionar LP ou item** quando você usa o processo de contagem de ciclo parcial.

## <a name="example"></a>Exemplo

Por exemplo, somente o item número A0001 deve ser contado no depósito 61.

1. Um novo modelo de trabalho para contagem cíclica é criado. A opção **Divisões de linha de trabalho** é usada para agrupar linhas de trabalho de contagem por número de item. Portanto, o trabalho de contagem cíclica criado terá linhas por número de item. Você também pode agrupar as linhas por número de grade de produto.
1. É criado um novo plano de contagem cíclica que faz referência ao modelo de trabalho recém-criado. O plano da contagem cíclica inclui todas as localizações no depósito 61 (consulta **Selecionar localizações**) que mantém o inventário para o item número A0001. A seleção de produtos específicos é definida na seção **Seleções de produtos de contagem cíclica**.
1. Você pode selecionar produtos para planos de contagem cíclica definindo o campo **Locais vazios** como **Excluir vazios**. Quando o plano da contagem cíclica é processado, o trabalho de contagem cíclica parcial para o número de item A0001 é criado. O processo de contagem real pode ser realizado usando um item de menu de dispositivo móvel para a contagem cíclica guiada.

## <a name="additional-resources"></a>Recursos adicionais

[Contagem cíclica](cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]