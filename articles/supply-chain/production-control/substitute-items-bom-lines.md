---
title: Substituição de material na fabricação
description: Este tópico descreve como substituir materiais durante o processo de produção.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa2f64026ec20a7b7562aac084866b69c5769029
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006957"
---
# <a name="material-substitution-in-manufacturing"></a>Substituição de material na fabricação

[!include [banner](../includes/banner.md)]

Este tópico descreve como substituir materiais durante o processo de produção. 

Há três métodos para substituir materiais durante o processo de produção:

-   Por data, quando o material é substituído por outro após uma data específica
-   Durante o planejamento mestre, quando um material em uma fórmula é substituído por um material diferente porque está esgotado
-   Durante a produção, quando um material está inesperadamente esgotado e é substituído por um material diferente

## <a name="substituting-material-by-date"></a>Substituição do material por data
Considere o seguinte cenário: Uma máquina que uma empresa fabrica contém um componente que expirará do catálogo do fornecedor em dois meses. A partir da data de vencimento, o fornecedor oferecerá um novo componente que pode ser substituído pelo componente antigo. As datas de validade de início e de término podem ser configuradas nas linhas de BOM (lista de materiais). Neste exemplo, você configura o componente antigo a expirar ao inserir a data de vencimento no campo **Data de término**. Em seguida, na BOM, configure o novo componente de substituição de forma que ele seja válido no dia posterior ao vencimento do antigo componente. Para isso, insira a data inicial no campo **Data de início**.

## <a name="substituting-material-by-planning"></a>Substituição do material por planejamento
Você só poderá substituir materiais durante o planejamento quando estiver usando fórmulas, e não quando estiver usando uma BOM. Considere o seguinte cenário: uma indústria alimentícia está fazendo de um molho usando uma fórmula com 20 ingredientes. Um ingrediente da fórmula pode ser substituído por um de dois outros ingredientes. No entanto, como esses dois ingredientes são mais caros do que o ingrediente preferencial, a substituição só será usada se o ingrediente preferencial estiver esgotado. O material que pode ser substituído é chamado de A, enquanto os dois materiais que podem substituí-lo são chamados de B e C. A substituição de material por planejamento é controlada pelos campos **Grupo de planos** e **Prioridade** nas linhas da fórmula. Neste exemplo, você cria linhas da fórmula para os três materiais e associa as linhas da fórmula ao mesmo grupo de planos. Na configuração, a linha da fórmula para o material A tem a maior prioridade (o número mais baixo), a linha da fórmula para o material C tem a menor prioridade e a linha da fórmula para o material B tem uma prioridade que está entre as prioridades das duas outras linhas. Se você tiver demanda do item concluído, o planejamento mestre primeiro determinará se a demanda do material A pode ser coberta. Se a demanda não puder ser coberta, o planejamento mestre examinará os materiais B e C, por ordem de prioridade. Se o material B estiver disponível, será usado após a confirmação de uma ordem de lote planejada para a fórmula. Se nenhum dos materiais estiver disponível, o planejamento mestre criará uma ordem planejada para o material A. **Observação:** quando você configurar linhas de fórmula em um grupo de planos, só deverá especificar uma quantidade on material com a prioridade mais altas. Essa quantidade será usada para calcular a demanda de todos os materiais no plano, até mesmo os materiais com prioridade inferior. Não é possível especificar quantidades diferentes em itens de prioridade inferior no grupo de planos.

## <a name="substituting-material-during-production"></a>Substituição de material durante a produção
Considere o cenário a seguir: uma placa de metal é necessária para uma operação de soldadura. Durante a operação, um trabalhador do depósito informa o operador da máquina que a placa de metal está esgotada. No entanto, foi decidido que a placa pode ser substituída por uma placa ligeiramente mais espessa. Dessa forma, a operação pode ser finalizada. O material pode ser adicionado à BOM para uma ordem de produção aberta. Se a ordem de produção tiver um status **Iniciado**, será solicitado que os usuários estimem novamente a ordem ao adicionarem um novo item à BOM de produção. Depois que o material for adicionado, uma nova lista de separação poderá ser criada para o novo item. Não é necessário adicionar o novo material à BOM de produção. Em vez disso, você pode adicionar diretamente à lista de separação de produção. Em seguida, quando a lista de separação for lançada, o sistema adicionará o material à BOM de produção.



