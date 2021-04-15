---
title: Configurar um canal de varejo
description: Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 713cbe68c151b6893519843611089941cabf0e70
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800582"
---
# <a name="set-up-a-retail-channel"></a>Configurar um canal de varejo

[!include [banner](includes/banner.md)]

Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece suporte a vários canais de varejo. Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais). Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe. Você deve configurar todos esses elementos para poder criar um canal de loja de varejo. 

Antes de criar um canal de varejo, certifique-se de seguir os [pré-requisitos do canal](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Criar e configurar um novo canal de varejo

1. No painel de navegação, vá para **Módulos \> Canais \> Lojas \> Todas as lojas**.
1. No painel de ação, selecione **Novo**.
1. No campo **Nome**, forneça um nome para o novo canal.
1. No campo **Número da loja**, forneça um número de loja exclusivo. O número pode ser alfanumérico e ter no máximo 10 caracteres.
1. Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.
1. Na lista suspensa **Depósito**, insira o depósito apropriado.
1. No campo **Fuso horário da loja**, selecione o fuso horário apropriado.
1. Na lista suspensa **Grupo de impostos**, selecione um grupo de impostos apropriado para a loja.
1. No campo **Moeda**, selecione a moeda apropriada.
1. No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.
1. No campo **Cliente padrão**, forneça um cliente padrão válido.
1. No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.
1. No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra a criação de um novo canal de varejo.

![Novo canal de varejo](media/channel-setup-retail-1.png)

A imagem a seguir mostra um exemplo de canal de varejo.

![Exemplo de canal de varejo](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Outras configurações

Existem várias outras configurações opcionais que podem ser definidas nas seções **Demonstrativo/fechamento** e **Diversos** conforme as necessidades da loja de varejo.

Além disso, consulte [Layouts de tela para o ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar o layout de tela padrão na seção **Layout da tela** e [Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md) para obter informações de configuração sobre a seção **Estações de hardware**.

A imagem a seguir mostra um exemplo de configuração da instalação de canal de varejo.

![Exemplo de configuração de canal de varejo](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Outras configurações de canal

Existem outros itens que precisam ser configurados para um canal e que podem ser encontrados no **Painel de ação** da seção **Configurar**.

Outras tarefas necessárias para a configuração do canal online incluem configurar métodos de pagamento, declaração de valores em caixa, modos de entrega, conta de receita/despesa, seções, a atribuição de grupo de orçamento e cofres.

A imagem a seguir mostra várias opções adicionais de configuração de canal de varejo na guia **Configurar**.

![Configurar o canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.
1. No painel de ação, selecione **Novo**.
1. No painel de navegação, selecione o método de pagamento desejado.
1. Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.
1. Defina as configurações adicionais necessárias para o tipo de pagamento.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de método de pagamento à vista.

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a>Configurar a declaração de valores em caixa

1. No painel de ação, selecione a guia **Configurar** e, depois, **Declaração de valores em caixa**.
1. No painel de ação, selecione **Novo** e crie todas as denominações aplicáveis de **Moeda** e **Nota**.

A imagem a seguir mostra um exemplo de declaração de valores em caixa.

![Configurar declarações de valores em caixa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Configurar os modos de entrega

Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.  

Para alterar ou adicionar um modo de entrega, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.
1. No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.
1. Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal. Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.

A imagem a seguir mostra um exemplo de modo de entrega.

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Configurar conta de receita/despesa

Para configurar a conta de receita/despesa, siga estas etapas.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Conta de receita/despesa**.
1. No painel de ação, selecione **Novo**.
1. Em **Nome**, insira um nome.
1. Em **Nome de pesquisa**, insira um nome de pesquisa.
1. Em **Tipo de conta**, insira o tipo de conta.
1. Insira o texto de **Linha de mensagem 1**, **Linha de mensagem 2**, **Texto da guia 1** e **Texto da guia 2**, conforme necessário.
1. Em **Lançamento**, insira as informações de lançamento.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de conta de receita/despesa.

![Configurar contas de receita/despesa](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Configurar seções

Para configurar seções, siga estas etapas.

1. No painel de ação, selecione a guia **Configurar** e clique em **Seções**.
1. No painel de ação, selecione **Novo**.
1. Em **Número da seção**, insira um número de seção.
1. Em **Descrição**, insira uma descrição.
1. Em **Tamanho da seção**, insira um tamanho de seção.
1. Defina configurações adicionais para **Geral** e **Estatísticas de venda**, conforme necessário.
1. No painel de ação, selecione **Salvar**.

### <a name="set-up-a-fulfillment-group-assignment"></a>Configurar uma atribuição de grupo de orçamento

Para configurar uma atribuição de grupo de orçamento, siga estas etapas.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de orçamento**.
1. No painel de ação, selecione **Novo**.
1. Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.
1. Na lista suspensa **Descrição**, insira uma descrição.
1. No painel de ação, selecione **Salvar**

A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.

![Configurar atribuições de grupo de orçamento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Configurar cofres

Para configurar cofres, siga estas etapas.

1. No painel de ação, selecione a guia **Configurar** e clique em **Cofres**.
1. No painel de ação, selecione **Novo**.
1. Insira um nome para o cofre.
1. No painel de ação, selecione **Salvar**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Configurar um canal online](channel-setup-online.md)

[Configurar um canal de call center](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
