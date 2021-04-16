---
title: Alterar modo de entrega no PDV
description: Este tópico descreve como configurar e usar o modo de alteração da operação de entrega no PDV.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a88ca9cc8fc8cde6d738dbc4fcf474f1e27e05dd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796381"
---
# <a name="change-mode-of-delivery-in-pos"></a>Alterar modo de entrega no PDV

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar e usar a funcionalidade "Alterar modo de entrega" no ambiente de ponto de venda (PDV). 

Nas versões 10.0.10 e posteriores do Dynamics 365 Commerce, a operação **Alterar modo de entrega** (647) está disponível para ser adicionado aos layouts de tela de PDV.

O modo de alteração do recurso de entrega fornece a opção de alterar o modo de entrega de uma ou mais linhas de venda configuradas pela remessa na transação do PDV. Em versões anteriores do Commerce, você precisava passar por todos os fluxos de configuração **Remeter tudo** ou **Remeter selecionados**, se quiser alterar o modo de entrega em uma linha existente que foi configurada para remessa. Esse processo foi demorado e poderia resultar em alterações acidentais na origem da entrega ou nas datas de entrega da linha. A nova funcionalidade fornece um método alternativo para a atualização eficiente do modo de entrega nessas linhas de venda.

Para obter mais informações sobre como adicionar uma operação a um botão na grade de botões PDV, consulte [Layouts de tela para o ponto de venda](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).

Depois que esse recurso é configurado no PDV, quando você seleciona **Alterar modo de entrega**, será apresentado uma página de listagem que permite escolher as linhas da transação para as quais você deseja alterar o modo de entrega. Você pode escolher algumas ou todas as linhas ou sair sem fazer alterações. As linhas de venda que foram previamente configuradas para remessa são as únicas linhas da lista que podem ser alteradas. Se desejar alterar uma linha designada para retirada ou postergado para remessa, você deve usar as operações **Remeter tudo** ou **Remeter selecionados**. Por outro lado, se desejar alterar uma linha designada como remessa para uma retirada ou postergar, você deverá usar as operações **Separar todos**, **Separar selecionados**, **Executar todos** ou **Executar selecionado**.

Depois de selecionar as linhas que deseja alterar, clique em **Alterar modo de entrega** para ser solicitado a selecionar as opções do modo de entrega. Se você selecionou várias linhas para alterar, o PDV só exibirá os modos de entrega que foram configurados como permitidos para todos os produtos selecionados. Os modos de entrega podem ser configurados para dar suporte a produtos e endereços de entrega específicos. Se houver um modo de entrega aceitável para uma combinação de produtos e endereços, mas não for aceitável para outra combinação de produtos e endereços selecionados, o modo de entrega não estará disponível. Talvez seja necessário selecionar as linhas uma a uma e alterar o modo de entrega para cada linha separadamente se você desejar selecionar um modo de entrega para um produto que não tenha suporte por outro produto.  

Depois de selecionar o novo modo de entrega, a página de transação é exibida. Para revisar as seleções do novo modo de entrega, selecione a guia **Entrega** na lista de transações.

## <a name="additional-resources"></a>Recursos adicionais

[Criar ordens de call center](tasks/create-call-center-orders.md)

[Personalizar emails transacionais por modo de entrega](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]