---
title: Personalizar emails transacionais por modo de entrega
description: Este tópico descreve como configurar modelos de email personalizados para tipos específicos de notificação e modos de entrega no Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: faf5fba70bf9297727464e6046806696ab725001
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594942"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Personalizar emails transacionais por modo de entrega

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico descreve como configurar modelos de email personalizados para tipos específicos de notificação e modos de entrega no Microsoft Dynamics 365 Commerce.

Agora, os emails transacionais podem ser personalizados para uma combinação de um tipo de notificação (por exemplo, **Ordem criada**, **Ordem embalada** ou **Ordem faturada**) e um modo de entrega (por exemplo, à noite, retirada na loja ou retirada em frente à loja). Os emails transacionais personalizados permitem que os varejistas forneçam aos clientes experiências de atendimento personalizadas para o modo de entrega da ordem. Por exemplo, o evento "ordem embalada" pode ser personalizado de forma que forneça instruções de retirada em frente à loja para clientes que optam por retirada em frente à loja. Como alternativa, ele pode fornecer informações da operadora de remessa e de entrega para clientes que optam por ordem enviada.

> [!NOTE]
> Para usar a funcionalidade para emails transacionais personalizados, primeiro você deve ativar o recurso **Personalizar modelos de email transacional por modo de entrega**, acessando **Espaços de trabalho \> Gerenciamento de recursos** na sede do Commerce.

Os emails podem ser personalizados por modo de entrega para os seguintes tipos de notificação:

- **Cancelamento da ordem** – este tipo de notificação por email é novo.
- **Ordem criada**
- **Ordem confirmada**
- **Ordem faturada** – este tipo de notificação por email é novo. Ele pode ser usado em vez do tipo de notificação **Ordem enviada** que enviará uma notificação para qualquer evento de fatura que tenha um modo de entrega enviado (não um modo de entrega por retirada, execução ou eletrônica).
- **Ordem separada**
- **Ordem embalada**
- **Ordem pronta para retirada** – este tipo de notificação só poderá ser personalizado por modo de entrega somente se o recurso **Suporte a vários modos de entrega de retirada** estiver ativado. Nesse caso, esse tipo de notificação é funcionalmente equivalente ao tipo de notificação **Ordem embalada**.
- **Falha no pagamento**
- **Ordem de substituição criada**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Configurar modelos de email para modos de entrega específicos

Para esse procedimento, a suposição é que você já tenha criado novos modelos de email personalizados e os adicionou à página **Modelos de email da organização**. Para obter informações sobre como criar e carregar modelos de email, consulte [Criar modelos de email para eventos transacionais](email-templates-transactions.md).

Para configurar modelos de email para modos de entrega específicos na sede do Commerce, siga estas etapas.

1. Vá para **Perfil de notificação por email do Commerce**.
1. Em **Configurações de notificação de eventos de varejo**, selecione um tipo de notificação existente.
1. Enquanto o tipo de notificação ainda estiver selecionado, selecione **Configurar modos de entrega**.
1. Na caixa de diálogo **Modos de entrega**, selecione **Novo**.
1. Na nova linha, no campo **Modo de entrega**, selecione um modo de entrega.
1. No campo **ID de email**, selecione o modelo de email a ser mapeado para o modo de entrega.
1. Marque a caixa de seleção **Ativo**.
1. Repita as etapas 4 a 7 para adicionar mais modos de entrega.
1. Quando terminar, selecione **OK**.

> [!NOTE]
> - Quando mais de um modo de entrega estiver presente em linhas de uma ordem de venda, o modelo padrão será usado. O modelo padrão é o modelo mapeado para o tipo de notificação na página **Perfil de notificação de email no Commerce**.
> - Se uma ordem de venda tiver um modo de entrega ainda não configurado para um modelo de email personalizado, o modelo de email padrão será usado.

## <a name="additional-resources"></a>Recursos adicionais

[Criar ordens de call center](tasks/create-call-center-orders.md)

[Alterar modo de entrega no PDV](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]