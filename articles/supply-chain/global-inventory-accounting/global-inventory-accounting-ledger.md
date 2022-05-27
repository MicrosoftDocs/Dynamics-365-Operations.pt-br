---
title: Razão do Contabilidade de estoque global
description: Este tópico descreve os razões da Contabilidade de estoque global, que são definidos por uma combinação de uma moeda, um calendário, uma convenção e uma associação com uma entidade legal.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f5f610fa51fce18ecefbf96892b56b05208c666c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676065"
---
# <a name="global-inventory-accounting-ledger"></a>Razão do Contabilidade de estoque global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

A Contabilidade de estoque global tem seu próprio conjunto de razões. Toda vez que uma transação relacionada ao inventário é processada para uma entidade legal relevante, o sistema pode considerar essa transação em qualquer número de razões da Contabilidade de estoque global, conforme necessário.

Um razão é um registro de medidas de débito e crédito. Essas medidas são classificadas usando elementos de custo e contas de sub-razão. Um razão da Contabilidade de estoque global é definido por sua combinação de uma moeda, um calendário, uma convenção e uma associação com uma entidade legal.

Para configurar os razões contábeis de estoque global, Acesse **Contabilidade de estoque global \> configuração \> Razões do Contabilidade de estoque global**. Em cada razão, defina os seguintes campos:

- **Nome** – Digite o nome do razão.
- **Descrição** – Digite uma descrição do razão.
- **Calendário fiscal** – Especifique o calendário fiscal do razão.
- **Moeda e tipo de taxa de câmbio** – Use os campos nesta Guia Rápida para selecionar a moeda contábil usada pelo razão e o tipo de taxa de câmbio. A moeda selecionada pode ser diferente da moeda usada pela entidade legal. Na Contabilidade de estoque global, os usuários podem definir quantos razões de custo forem necessários. A Contabilidade de estoque global oferece suporte a estatísticas de estoque em várias moedas e em várias avaliações. Defina os seguintes campos:

    - **Moeda** – Selecione a moeda de custo na qual os valores relacionados ao estoque são mantidos. Esses valores incluem o valor de estoque, o custo dos produtos vendidos, o estoque em trânsito e todos os tipos de variação.
    - **Tipo de taxa de câmbio** – Selecione a taxa de câmbio que o sistema deve usar para converter o valor da transação na moeda da transação e o custo padrão dos itens na moeda de custo.

- **Nome da convenção** – Especifique uma convenção. Uma convenção é um conjunto de diretivas que estabelecem como os custos serão contabilizados neste razão.
- **Entidade legal** – O razão considerará os documentos lançados na entidade legal selecionada.
- **Preparação** – Escolha se as transações de estoque criadas antes da criação do razão devem ser processadas de acordo com a moeda e a convenção do razão. Selecione um dos seguintes valores:

    - **Ativado** – O razão deve processar transações criadas antes da criação do razão.
    - **Ativado** – O razão deve processar somente transações que foram criadas depois do razão.

    > [!IMPORTANT]
    > Você **não** poderá voltar e definir este campo depois de inserir novos documentos.

- **Status** – O sistema define automaticamente o status de os razões recém-criados para *Preparar*.
