---
title: Configurar um canal online
description: Este artigo descreve como criar um novo canal online no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: be9fafe8ece771ad6577db1cdb70af6f48e054cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272871"
---
# <a name="set-up-an-online-channel"></a>Configurar um canal online

[!include [banner](includes/banner.md)]

Este artigo descreve como criar um novo canal online no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece suporte a vários canais de varejo. Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais). As lojas online oferecem aos clientes a opção de comprar produtos na loja online do varejista, além das lojas físicas.

Para criar uma loja online no Commerce, primeiro você deve criar um canal online. Antes de criar um novo canal online, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).

Antes de criar um novo site, crie pelo menos uma loja online no Commerce. Para obter mais informações, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Criar e configurar um novo canal online

Para criar e configurar um novo canal online, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Canais \> Lojas Online**.
1. No painel de ação, selecione **Novo**.
1. No campo **Nome**, forneça um nome para o novo canal.
1. Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.
1. Na lista suspensa **Depósito**, insira o depósito apropriado.
1. No campo **Fuso horário da loja**, selecione o fuso horário apropriado.
1. No campo **Moeda**, selecione a moeda apropriada.
1. No campo **Cliente padrão**, forneça um cliente padrão válido.
1. No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.
1. No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.
1. No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra a criação de um novo canal online.

![Novo canal online.](media/channel-setup-online-1.png)

A imagem a seguir mostra um exemplo de canal online.

![Exemplo de canal online.](media/channel-setup-online-2.png)

## <a name="assign-the-channel-to-a-commerce-scale-unit"></a>Atribuir o canal a uma Commerce Scale Unit

Seu novo canal deve ser atribuído a uma Commerce Scale Unit. Para obter instruções, consulte [Configurar canais para usar a Commerce Scale Unit](../fin-ops-core/dev-itpro/deployment/initialize-retail-channels.md#configure-channels-to-use-commerce-scale-unit).

## <a name="set-up-languages"></a>Configurar idiomas

Se o seu site de comércio eletrônico der suporte a vários idiomas, expanda a seção **Idiomas** e adicione outros idiomas, conforme necessário.

## <a name="set-up-payment-account"></a>Configurar conta de pagamento

Na seção **Conta de pagamento**, você pode adicionar um provedor de serviço de pagamento terceirizado. Para obter informações sobre como configurar um conector de pagamento Adyen, consulte [Conector de pagamento do Dynamics 365 para Adyen](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Configuração adicional do canal

Outras tarefas que são necessárias para a configuração do canal online incluem configurar métodos de pagamento, modos de entrega e a atribuição de grupo de orçamento.

A imagem a seguir mostra opções de configuração de **Modos de entrega**, **Métodos de pagamento** e **Atribuição de grupo de orçamento** na guia **Configurar**.

![Outras ações de configuração do canal online.](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.
1. No painel de ação, selecione **Novo**.
1. No painel de navegação, selecione o método de pagamento desejado.
1. Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.
1. Defina as configurações adicionais necessárias para o tipo de pagamento.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de método de pagamento à vista.

![Exemplo de métodos de pagamento.](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Configurar os modos de entrega

Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.  

Para alterar ou adicionar um modo de entrega, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Gerenciamento de estoque \> Modos de entrega**.
1. No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.
1. Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal. Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.

A imagem a seguir mostra um exemplo de modo de entrega.

![Configurar os modos de entrega.](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Configurar uma atribuição de grupo de orçamento

Para configurar uma atribuição de grupo de orçamento, siga estas etapas.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de orçamento**.
1. No painel de ação, selecione **Novo**.
1. Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.
1. Na lista suspensa **Descrição**, insira uma descrição.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.

![Configurar atribuição de grupo de orçamento.](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Configurar um canal de varejo](channel-setup-retail.md)

[Configurar um canal de call center](channel-setup-callcenter.md)

[Conector de Pagamento do Dynamics 365 para Adyen](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
