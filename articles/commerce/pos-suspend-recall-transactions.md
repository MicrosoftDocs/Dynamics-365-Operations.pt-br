---
title: Suspender e continuar uma transação no ponto de venda (PDV)
description: Este tópico explica como os usuários podem suspender transações em andamento e retomá-las, posteriormente, ou iniciar um registro diferente, usando o Dynamics 365 Commerce.
author: jblucher
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fdb693cb3b7520a9850d3e37dd512fc5b2a847f3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798648"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a>Suspender e continuar uma transação no ponto de venda (PDV)

[!include [banner](includes/banner.md)]


Os usuários de ponto de venda (PDV) podem suspender transações em andamento e retomá-las posteriormente ou iniciar um registro diferente. As transações costumam ser suspensas para liberar rapidamente um registro para uma tarefa diferente sem perder o progresso da transação atual. Por exemplo, um associado da loja começa a processar transações de um cliente em um dispositivo móvel, mas precisa concluí-la em um registro com uma caixa registradora. Nesse caso, o associado da loja pode suspender a transação no dispositivo celular e, depois, recuperá-la e retomá-la em um registro.

## <a name="configure-suspend-and-resume-functionality"></a>Configure a funcionalidade de suspensão e retomada

### <a name="pos-operations"></a>Operações de PDV

Duas [operações de PDV](pos-operations.md) permitiram a suspensão e a retomada de cenários pelo PDV. Você pode atribuir essas operações a [grades de botões](pos-screen-layouts.md) na página da transação ou na página de boas-vindas.

- 503: Suspender Transação
- 504: Recuperar Transação

### <a name="receipt-template"></a>Modelo de recebimento

O PDV pode ser configurado para gerar uma guia impressa quando uma transação é suspensa. Essa guia pode ser usada para identificar rapidamente e recuperar a transação posteriormente.

Para habilitar o PDV para imprimir uma guia, você deve adicionar o formato de recebimento **Transação suspensa** ao perfil de recebimento da loja. Você pode criar o formato de recebimento de modo que ele inclua ou exclua detalhes específicos sobre a transação. Por exemplo, o formato pode incluir um código de barras para oferecer suporte à digitalização.

### <a name="receipt-numbering"></a>Numeração de recibo

Quanto a outros tipos de transação PDV que geram um recibo impresso, você pode definir uma sequência numérica para transações suspensas na seção **Numeração de recibo** do perfil de funcionalidade da loja.

### <a name="void-when-closing-shift"></a>Anular no fechamento do turno

Você pode usar a opção **Anular ao fechar turno** para exigir que os usuários concluam ou anulem transações suspensas antes de fechar seu turno. Durante a operação **Fechar turno**, o PDV solicitará que os usuários exibam ou anulem transações suspensas pendentes.

## <a name="suspend-and-resume-a-transaction"></a>Suspender e retomar uma transação

### <a name="suspend-a-transaction"></a>Suspenda uma transação

Os usuários com privilégios suficientes e aqueles com um layout de tela que inclua a operação **Suspender transação** poderão suspender uma transação para que ela possa ser recuperada posteriormente ou em outro registro.

Transações só poderão ser suspensas se **não** contiverem os seguintes tipos de linhas:

- Linhas de pagamento ativas
- Linhas de vale-presente (para emitir um vale-presente ou para adicionar ao saldo do vale-presente)

Uma transação suspensa não afeta informações de vendas nem informações de disponibilidade do estoque.

### <a name="resume-a-suspended-transaction"></a>Retomar uma transação suspensa

As transações suspensas podem ser recuperadas e retomadas na mesma loja por qualquer usuário com privilégios suficientes, e também que tenham um layout que inclua a operação **Recuperar transação**.

Para recuperar uma transação suspensa com rapidez e facilidade, digitalize o código de barras na guia impressa enquanto você estiver exibindo a lista de transações da operação **Recuperar transação**.

### <a name="considerations-for-offline-mode"></a>Considerações sobre o modo offline

- Qualquer transação suspensa enquanto o PDV estiver em modo online não poderá ser retomada em modo offline, pois os dados não estão sincronizados no banco de dados offline.
- Se você suspender uma transação enquanto o PDV estiver em modo offline, poderá recuperá-la em modo offline, desde que o PDV não volte ao modo online a qualquer momento, pois você suspendeu a transação. Quando o PDV é alternado para o modo online, os dados sobre transações suspensas são movidos para o banco de dados online e removidos do banco de dados offline. Portanto, as transações só podem ser retomadas em modo online. Se você alternar o PDV para o modo offline, não poderá retomar essas transações suspensas, pois elas já foram removidas do banco de dados offline.

### <a name="void-a-suspended-transaction"></a>Anular a transação suspensa

Você pode anular transações suspensas recuperando a transação e, depois, executando a operação, **Anular transação** ou pode selecionar a transação na lista **Recuperar transação** e selecionar **Anular** na barra de aplicativos. Como alternativa, a loja pode ser configurada para solicitar aos usuários que anulem transações suspensas ao fecharem o turno.


[!INCLUDE[footer-include](../includes/footer-banner.md)]