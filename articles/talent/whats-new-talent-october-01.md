---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (1 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303237"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Novidades ou alterações no Dynamics 365 for Talent Core HR (1 de outubro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.1035.0**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Desativar validação de pagamentos eletrônicos

A validação das informações de pagamentos eletrônicos ocorre se você configurar os pagamentos para depósito direto no espaço de trabalho **Autoatendimento para funcionários** (ESS) ou diretamente no formulário do funcionário. Essa opção oferece a flexibilidade para remover essa validação se você não requer as verificações de validação para valores e valores restantes. Esse recurso é útil se você está se integrando a um sistema de folha de pagamento externo que tem com requisitos diferentes.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Autoatendimento para gerentes – Adicionar metas para membros de equipe no bloco Metas de desempenho da equipe

Antes desta versão, os gerentes podiam adicionar metas aos funcionários individualmente por meio das metas de desempenho associadas a cada funcionário. Com essa atualização, os gerentes podem acessar o bloco **Metas de desempenho da equipe** e criar novas metas marcando alguns de seus relatórios diretos.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Autoatendimento para gerentes – Adicionar avaliações para membros de equipe no bloco Avaliações de desempenho da equipe

Antes desta versão, os gerentes podiam adicionar avaliações aos funcionários individualmente com as avaliações associadas a cada funcionário. Com essa atualização, os gerentes podem acessar o bloco **Avaliações de desempenho da equipe** e criar novas avaliações marcando alguns de seus relatórios diretos.

## <a name="configure-proration-options-by-leave-plan"></a>Configurar opções de rateio por plano de licença

As organizações concedem folgas de maneira diferente com base em quando os funcionários entraram e saíram da empresa. Para algumas organizações, os funcionários são recebem a alocação total na sua data de início, enquanto outros fazem rateio da concessão. São oferecidas novas opções nesta versão para escolher como fazer o rateio de concessões e competências para pessoas que estão entrando ou saindo de uma organização. As opções incluem: rateado, competência total e nenhuma competência.

## <a name="other-changes"></a>Outras alterações

-   Entidade de funcionário atualizada – O título **Pessoal** agora pode ser atualizado usando o suplemento/gerenciamento de dados do Excel.

-   Alteração de segurança para permitir a remoção dos botões **Excluir** e **Desativar** no autoatendimento para funcionários de informações de pagamento.

## <a name="known-issue"></a>Problema conhecido

-   **Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os Quadros de Fatos na página **Trabalhador** estão fechados. Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões **Anexos** serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
