---
title: Visão geral do reconhecimento de receita
description: Este tópico fornece informações sobre o recurso Reconhecimento de receita. Este recurso fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita para ordens de vários elementos.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863554"
---
# <a name="revenue-recognition-overview"></a>Visão geral do reconhecimento de receita

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> O recurso Reconhecimento de receita ainda não pode ser ativado por meio do Gerenciamento de recursos. No momento, você deve usar as chaves de configuração para ativá-lo.

As empresas em setores que vendem vários elementos, como produtos, serviços, assinaturas, etc, devem ter a capacidade de dividir ordens de vários elementos de modo que a receita possa ser reconhecida com base em um conjunto de diretrizes específicas da empresa e específicas do setor.

Em geral, o processo de reconhecimento de receita pode ser usado para realizar estas tarefas:

* Alocar a receita, para ajudar a garantir que o preço adequado da receita seja reconhecido com base no valor dos componentes em ordens de vários elementos.
* Adiar receita, com base em uma agenda de receita que representa o período e as porcentagens contratuais para reconhecer receitas ao longo do tempo.

O recurso Reconhecimento de receita fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita.

Os produtos lançados são usados para dar suporte ao reconhecimento de receita em documentos de ordem de venda. Os produtos lançados contêm a configuração necessária para determinar o preço de receita e a agenda de receita. A ordem de venda pode ser originária de um projeto de Tempo e material.

As empresas podem usar a funcionalidade de agenda de receita sem usar a funcionalidade de preço de receita. Portanto, o preço nas linhas de ordem de venda será usado como receita ou receita adiada. Se houver uma agenda de receita na linha de ordem de venda, preço na linha de ordem de venda será adiado. Se não houver uma agenda de receita na linha de ordem de venda, o preço na linha de ordem de venda será lançado em uma conta de receita quando for faturada.

O preço de receita será calculado alguém quando a ordem de venda for confirmada ou a fatura for lançada. Para visualizar o preço de receita antes que a fatura seja lançada, você deverá confirmar a ordem de venda.

Quando a ordem de venda for confirmada, uma agenda de receita prevista também será criada se qualquer linha de ordem de venda contiver uma agenda de receita. Quando a ordem de venda for faturada, a agenda de receita prevista será excluída e será substituída pela agenda real de reconhecimento de receita.

Os detalhes da agenda de reconhecimento de receita são mantidos para cada linha de ordem de venda. Portanto, o gerente de reconhecimento de receita poderá exibir os detalhes e pode liberar linhas para a receita quando a obrigação contratual for concluída. No final de cada período, o gerente de reconhecimento de receita poderá criar um diário de receita para liberar linhas da agenda que estão vencidas ou antes de uma data que ele definir. Esse diário de receita não é lançado imediatamente. Portanto, o gerente de reconhecimento de receita poderá verificar se os valores corretos estão sendo liberados da receita adiada para a receita real.

Se uma alteração contratual fizer com que uma nova linha de ordem de venda seja adicionada à ordem de venda existente a uma nova ordem de venda, um processo a realocação pode ser executado para corrigir o preço de receita em todas as linhas das ordens de venda.
