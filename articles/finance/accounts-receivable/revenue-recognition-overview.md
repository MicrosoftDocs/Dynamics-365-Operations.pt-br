---
title: Visão geral do reconhecimento de receita (contém vídeo)
description: Este artigo fornece informações sobre o recurso Reconhecimento de receita. Este recurso fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita para ordens de vários elementos.
author: bking
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5bf07356b5613f438034f8dabac7db197e69a6c8
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644021"
---
# <a name="revenue-recognition-overview"></a>Visão geral do reconhecimento de receita

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Essa funcionalidade será preterida em outubro de 2023, os novos usuários devem usar a cobrança de assinatura.

As empresas em setores que vendem vários elementos, como produtos, serviços, assinaturas etc., devem ter a capacidade de dividir ordens de vários elementos de modo que a receita possa ser reconhecida com base em um conjunto de diretrizes específicas da empresa e do setor.

O reconhecimento de receita, incluindo a funcionalidade de pacote, não é compatível com o uso em canais do Commerce (comércio eletrônico, PDV, call center). Os itens configurados com reconhecimento de receita não devem ser adicionados a ordens ou transações criadas em canais do Commerce.

Em geral, o processo de reconhecimento de receita pode ser usado para realizar estas tarefas:

* Alocar a receita, para ajudar a garantir que o preço adequado da receita seja reconhecido com base no valor dos componentes em ordens de vários elementos.
* Adiar receita, com base em uma agenda de receita que representa o período e as porcentagens contratuais para reconhecer receitas ao longo do tempo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

O vídeo [Como usar o reconhecimento de receita no Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (mostrado acima) está incluído na [playlist dos aplicativos de finanças e operações](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

O recurso Reconhecimento de receita fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita.

Os produtos lançados são usados para dar suporte ao reconhecimento de receita em documentos de ordem de venda. Os produtos lançados contêm a configuração necessária para determinar o preço de receita e a agenda de receita. A ordem de venda pode ser originária de um projeto de Tempo e materiais.

As empresas podem usar a funcionalidade de agenda de receita sem usar a funcionalidade de preço de receita. Portanto, o preço nas linhas de ordem de venda será usado como receita ou receita adiada. Se houver uma agenda de receita na linha de ordem de venda, preço na linha de ordem de venda será adiado. Se não houver uma agenda de receita na linha de ordem de venda, o preço na linha de ordem de venda será lançado em uma conta de receita quando for faturada.

O preço de receita será calculado alguém quando a ordem de venda for confirmada ou a fatura for lançada. Para visualizar o preço de receita antes que a fatura seja lançada, você deverá confirmar a ordem de venda.

Quando a ordem de venda for confirmada, uma agenda de receita prevista também será criada se qualquer linha de ordem de venda tiver uma agenda de receita. Quando a ordem de venda for faturada, a agenda de receita prevista será excluída e substituída pela agenda real de reconhecimento de receita.

Os detalhes da agenda de reconhecimento de receita são mantidos para cada linha de ordem de venda. Portanto, o gerente de reconhecimento de receita poderá exibir os detalhes e pode liberar linhas para a receita quando a obrigação contratual for concluída. No final de cada período, o gerente de reconhecimento de receita poderá criar um diário de receita para liberar linhas da agenda que estão vencidas ou antes de uma data que definirem. Esse diário de receita não é lançado imediatamente. Portanto, o gerente de reconhecimento de receita poderá verificar se os valores corretos estão sendo liberados da receita adiada para a receita real.

Se uma alteração contratual fizer com que uma nova linha de ordem de venda seja adicionada à ordem de venda existente ou a uma nova ordem de venda, um processo de realocação pode ser executado para corrigir o preço de receita em todas as linhas das ordens de venda.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

