---
title: Configurar realocação de item de pouca seleção
description: Este tópico mostra como permitir que os trabalhadores do depósito encontrem rapidamente locais alternativos se não houver estoque suficiente no local para o qual eles foram direcionados.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecd05add44bacae517109f8bab2cb43376fe07c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216802"
---
# <a name="set-up-short-picking-item-reallocation"></a>Configurar realocação de item de pouca seleção

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente locais alternativos se não houver estoque suficiente no local para o qual eles foram direcionados. 

O processo de realocação é controlado por uma **Exceção de trabalho** e usado pelo **trabalhador** do depósito.

É possível usar processos de realocação Automáticos, Manuais ou ambos:

- Realocação automática - As diretivas de localização são usadas para determinar se as mercadorias estão disponíveis em outro local. Se possível, o trabalho será atualizado e o usuário do depósito será direcionado para o local alternativo.
- Realocação manual - Permite que o usuário do depósito selecione um ou mais locais com quantidades de mercadorias não reservadas. 
- Automática e manual - Se o sistema não puder executar uma realocação automática e os locais estiverem disponíveis com quantidades não reservadas, o usuário será solicitado a selecionar um local.

## <a name="set-up-work-exceptions"></a>Configurar exceções de trabalho
É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.

A empresa de dados de demonstração USMF foi usada para criar este procedimento.

1. No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho**.
2. Clique em **Novo** 
3. No campo **Código de exceção do trabalho**, digite um valor. Isso será o título dessa exceção. Por exemplo, manual de separação insuficiente.
4. No campo **Descrição**, digite um valor. Isso será uma breve descrição do uso dessa exceção. Por exemplo, Separação insuficiente - item não disponível.
5. No campo do tipo de **Exceção**, selecione **Separação insuficiente**.
6. Marque a caixa de seleção **Ajustar estoque**. Se marcada, o estoque será automaticamente ajustado para 0 no local de separação insuficiente.
7. No campo **Código de tipo de ajuste padrão**, insira ou selecione um valor. Por exemplo, na USMF, você pode selecionar **Remover Res Adj Out**. Cada Código de tipo de ajuste contém quatro características: nome, descrição, nome do diário de estoque e **Remover reservas**. Se **Remover reservas** estiver habilitado, as reservas da linha de ordem de separação insuficiente serão removidas.  
8. No campo **Realocação de item**, selecione um valor, como Manual. Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Configurar um trabalhador para usar a realocação de item manual

A empresa de dados de demonstração USMF foi usada para criar este procedimento.

1. Feche a página.
2. No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalhador**.
3. Clique em **Editar**.
4. Na lista, selecione o trabalhador. Por exemplo, Julia Funderburk.
5. Expanda a FastTab **Usuários**.
6. Na lista, selecione uma **ID de Usuário**. Por exemplo, 24.
7. Expanda a FastTab **Trabalho**.
8. Selecione **Sim** no campo **Permitir realocação manual de itens**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]