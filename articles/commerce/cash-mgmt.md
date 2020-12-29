---
title: Aprimoramentos de gerenciamento de pagamento à vista
description: Este tópico descreve os aprimoramentos de gerenciamento de pagamento à vista no PDV para o Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0c561c39dfcbfa739c5a22394c05191e7f9bc107
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410154"
---
# <a name="cash-management-improvements"></a>Aprimoramentos de gerenciamento de pagamento à vista

[!include [banner](includes/banner.md)]


O gerenciamento de pagamento à vista é uma função fundamental para os varejistas em lojas físicas. Os varejistas desejam que suas lojas tenham sistemas que possam ajudá-los a fornecer rastreabilidade completa e responsabilidade de pagamento à vista e seu movimento pelos diferentes registros e caixas em uma loja. Eles devem ser capazes de reconciliar quaisquer diferenças e determinar a responsabilidade.


O Microsoft Dynamics 365 Commerce tem funcionalidades de gerenciamento de pagamento à vista em seu aplicativo de ponto de venda (PDV). Contudo, nas versões do Retail anteriores à versão 10.0.3, a funcionalidade de gerenciamento de pagamento à vista não é robusta o suficiente para fornecer rastreabilidade completa dos movimentos de pagamento à vista nas lojas. Embora os varejistas possam reconciliar o pagamento à vista de uma loja, eles não podem determinar com precisão a responsabilidade em caso de discrepância de pagamento à vista.


No Retail versão 10.0.3 e posterior, os varejistas ganharão rastreabilidade para lidar com pagamento à vista. Como parte dessa rastreabilidade, os varejistas poderão definir cofres, fazer transações de pagamento à vista nos dois lados e reconciliar transações de gerenciamento de pagamento à vista.

## <a name="set-up-traceability-and-define-safes"></a>Configurar rastreabilidade e definir cofres

Para configurar a nova funcionalidade de gerenciamento de pagamento à vista, siga estas etapas para configurar o perfil de funcionalidade para os armazenamentos.

1. Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade** e selecione um perfil de funcionalidade que esteja vinculado às lojas onde você quer fazer os aprimoramentos de gerenciamento de pagamento à vista.
2. Na Guia Rápida **Funções** do perfil de funcionalidade, em **Gerenciamento de pagamento à vista avançado**, defina a opção **Habilitar rastreabilidade de pagamento à vista** como **Sim**.
3. Para configurar cofres, vá para **Varejo e Comércio \> Canais \> Lojas \> Todas as lojas** e selecione uma loja.
4. Na página **Lojas**, no Painel de Ação, na guia **Configurar**, no grupo **Configurar**, selecione **Cofres**. Ao usar essa opção, você pode definir e manter vários cofres para uma loja.
4. Antes que a funcionalidade possa ser usada, você deve executar o trabalho de agenda de distribuição **1070 Configuração do canal** para sincronizar essas configurações com o banco de dados do canal.

## <a name="additional-cash-management-changes"></a>Alterações adicionais no gerenciamento de pagamento à vista

No Retail versão 10.0.3 e posterior, os seguintes recursos relacionados a transações de pagamento à vista também são fornecidos:

- Um usuário que é solicitado a "declarar o valor inicial" deve inserir a origem do pagamento à vista. O usuário pode procurar os cofres disponíveis que estão definidos na loja e selecionar o cofre do qual o dinheiro está sendo retirado para que possa ser colocado no registro.
- Um usuário que faz uma operação de "remoção de meio de pagamento" é solicitado a selecionar, em uma lista de transações de "entrada de flutuação" aberta, a transação em relação à qual a operação está sendo executada. Se a entrada de flutuação correspondente não existir no sistema, o usuário poderá criar uma transação de remoção de oferta não vinculada.
- Uma operação de "entrada de flutuação" solicita que um usuário selecione, em uma lista de transações de "remoção de meio de pagamento" abertas, a transação em relação à qual a operação de entrada de flutuação está sendo executada. Se a remoção de meio de pagamento correspondente não existir no sistema, o usuário poderá criar uma transação de entrada de flutuação não vinculada.
- Um usuário que faz um "depósito no cofre" é solicitado a selecionar o cofre onde o pagamento à vista está sendo depositado.
- Para os cofres definidos em uma loja, os usuários podem gerenciar operações, como declarar o valor inicial, fazer uma entrada de flutuação, fazer uma retirada de de meio de pagamento e fazer um depósito bancário.
- Para usuários que têm os privilégios de usuário apropriados, as operações "gerenciar turnos" mostram os saldos de pagamento à vista de turnos com fechamento ativo, suspenso e em branco.
- Para reconciliar as transações de pagamento à vista dentro de um turno ou em turnos, selecione o turno para reconciliar e depois selecione **Reconciliar**. A exibição que é aberta mostra a lista de transações reconciliadas e não reconciliadas em guias separadas. Nessa exibição, os usuários podem selecionar transações não reconciliadas e reconciliá-las ou selecionar transações reconciliadas anteriormente e desequilibrá-las.
- Durante a reconciliação, se a transação selecionada não for equilibrada, o usuário deve inserir uma descrição do motivo da reconciliação desbalanceada. Os usuários podem selecionar uma única transação e reconciliá-la com a descrição do motivo relevante, conforme necessário.
- Os usuários podem continuar a reconciliar e desestruturar as transações até que a mudança seja encerrada. Depois que um turno é fechado, as transações não podem ser reconciliadas.
- Quando um usuário escolhe fechar um turno, o Commerce valida que não há transações de gerenciamento de pagamento à vista não reconciliadas no turno. Os usuários não podem fechar um turno se houver transações não reconciliadas.
