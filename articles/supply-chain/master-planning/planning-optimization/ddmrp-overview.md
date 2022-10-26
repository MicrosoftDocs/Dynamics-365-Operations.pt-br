---
title: Visão geral do DDMRP (Planejamento de Requisitos de Material Orientado por Demanda)
description: Este artigo fornece informações sobre o DDMRP (Planejamento de Requisitos de Material Orientado por Demanda), uma metodologia de planejamento baseada na separação de fornecimento e demanda.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689479"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Visão geral do DDMRP (Planejamento de Requisitos de Material Orientado por Demanda)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Durante anos, as empresas usaram o MRP (Planejamento de Requisitos de Material) como um sistema para calcular os materiais e os componentes necessários para fabricar um produto. No entanto, as cadeias de fornecedores mudaram. As peças têm prazos de entrega mais longos, pois cada vez mais são originadas no exterior. Portanto, muitas empresas informaram enfrentar falta de estoque ou estoque em excesso, pois não sabem quanto estocar. Além disso, há mais flutuação de mercado (às vezes imprecisamente prevista) e os clientes estão exigindo produtos com um prazo de entrega curto. Portanto, há escassez de cadeia de fornecedores em todo o mundo. Além disso, as ferramentas de MRP geralmente fornecem aos planejadores milhares de ações a serem executadas. Portanto, é difícil saber no que focar. Em geral, a solução para muitas desses problemas é alternar para o DDMRP (Planejamento de Requisitos de Material Orientado por Demanda).

O DDMRP é uma metodologia de planejamento baseada na separação de fornecimento e demanda. Essa separação é obtida pela configuração de itens do ponto de separação. Para esses itens, os buffers são mantidos de modo a garantir que a quantidade correta de estoque seja mantida. A separação de fornecimento e demanda ajuda a evitar o "efeito chicote", pois a variabilidade não é passada pela cadeia. (O *efeito chicote* refere-se à forma como as flutuações pequenas na demanda no nível de varejo podem causar flutuações cada vez maiores na demanda nos níveis de atacado, distribuidor, fabricante e fornecedor de material bruto.) A finalidade de cada buffer é cobrir o uso médio de uma peça e também poder ser ajustado para cobrir picos de demanda.

O DDMRP foi comprovado como uma metodologia de planejamento valiosa para ambientes variáveis em que os tempos de tolerância do cliente são menores que os prazos de entrega cumulativos.

## <a name="the-five-components-of-ddmrp"></a>Os cinco componentes do DDMRP

O DDMRP tem cinco componentes sequenciais (etapas). Os três primeiros componentes basicamente definem a configuração inicial e progressiva de um modelo de planejamento de requisitos de material orientado por demanda. Os dois últimos componentes definem a operação diária da metodologia.

1. **[Posicionamento estratégico de estoque](ddmrp-inventory-positioning.md)** – identifique pontos de separação na rede da cadeia de fornecedores. Os pontos de separação são pontos específicos da sua cadeia de fornecedores nos quais você coloca um buffer de estoque que será monitorado e reabastecido.
2. **[Perfis e níveis de buffer](ddmrp-buffer-profile-and-levels.md)** – para cada ponto de separação, identifique os tamanhos de buffer (quantidade mínima, quantidade máxima e ponto de reabastecimento) e a quantidade do reabastecimento.
3. **[Ajustes de buffer dinâmico](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)** – ajuste os níveis de buffer com base em parâmetros operacionais variáveis ou eventos futuros planejados.
4. **[Planejamento orientado por demanda](ddmrp-planning.md)** – gere ordens de fornecimento conforme elas são necessárias. Essas ordens de fornecimento incluem ordens de fabricação, ordens de compra e ordens de transferência de estoque
5. **[Execução altamente colaborativa e visível](ddmrp-visual-and-collaborative-execution.md)** – execute as ordens de fornecimento com a ajuda da visualização.

Normalmente, o DDMRP é usado pelos fabricantes que têm uma BOM (lista de materiais) de vários níveis. No entanto, ele também pode ser aplicado a redes de distribuição e de varejo.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP no Dynamics 365 Supply Chain Management

O DDMRP está incluído no Microsoft Dynamics 365 Supply Chain Management e não requer taxas de licença adicionais. No Supply Chain Management, a funcionalidade do DDMRP foi adicionada ao módulo **Planejamento mestre** existente. No entanto, é necessário usar o suplemento Otimização de Planejamento. 

O DDMRP é integrado às configurações de planejamento existentes no Supply Chain Management e é usado em conjunto com essas configurações para chegar à configuração de planejamento correta para a sua empresa. Ele é controlado por um novo código de cobertura que é completamente diferente do período, mín/máx, requisito e assim por diante. Não se trata de um módulo novo e ele não substitui a funcionalidade de planejamento existente. No entanto, ele oferece mais funcionalidade a ser usada.
