---
title: Ocultar modos de entrega sem transportadora das opções de remessa no PDV
description: Este artigo descreve uma opção de configuração que pode impedir a exibição de modos de entrega sem transportadora para seleção quando ordens de remessa são criadas no aplicativo do ponto de venda (POS).
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 469e6ebb8afed26a6bf25f4c9c3ab8f7f4ac78ba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896996"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Ocultar modos de entrega sem transportadora das opções de remessa no PDV


[!include [banner](includes/banner.md)]

Este artigo descreve uma opção de configuração disponível para o aplicativo de ponto de venda (PDV). Esta opção de configuração alterará o comportamento da seleção de um modo de entrega quando ordens de remessa são criadas no PDV.

Quando os usuários criam ordens de remessa de clientes no PDV, eles podem selecionar um modo de entrega para a remessa. Essa funcionalidade está disponível independentemente da ordem inteira sendo enviada ou de apenas linhas selecionadas.

Por padrão, a caixa de diálogo em que um modo de entrega é selecionado mostra todos os modos de entrega válidos para a combinação de um canal, um item e um endereço de entrega. Esses modos de entrega são definidos na página **Modos de entrega** em headquarters (**Vendas e marketing \> Configurar \> Distribuição \> Modos de entrega**). Modos de entrega "sem transportadora", como **Execução** ou **Retirada**, também podem aparecer para seleção na caixa de diálogo.

Contudo, foi adicionado um recurso que permite ocultar modos de entrega sem transportadora na caixa de diálogo. Para ativar esse recurso, na página **Parâmetros do Commerce**, na guia **Ordens do cliente**, defina a opção **Mostrar apenas opções de modo de transportadora para ordens de remessa** como **Sim**. Depois de ativar esse recurso e executar os trabalhos de distribuição apropriados para sincronizar as informações com o banco de dados do canal, os modos de entrega sem transportadora não aparecerão para seleção durante o processo de criação de ordens de remessa no PDV.


[!INCLUDE[footer-include](../includes/footer-banner.md)]