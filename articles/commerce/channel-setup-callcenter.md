---
title: Configurar um canal de call center
description: Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 878774c8e5485211525e7e7b63973173f6874b26
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218360"
---
# <a name="set-up-a-call-center-channel"></a>Configurar um canal de call center


[!include [banner](includes/banner.md)]

Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral


No Dynamics 365 Commerce, o call center é um tipo de canal do Commerce que pode ser definido no aplicativo. Definir um canal para as entidades de call center permite que o sistema vincule dados e padrões de processamento de ordens específicos a ordens de venda. Embora uma empresa possa definir vários canais de call center no Commerce, é importante observar que um usuário individual pode estar vinculado apenas a um canal de call center. 

Antes de criar um novo canal de call center, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Criar e configurar um novo canal de call center

Para criar e configurar um novo canal de call center, siga estas etapas.

1. No painel de navegação, acesse **Varejo e Comércio \> Canais \> Call centers \> Todos os call centers**.
1. No painel de ação, selecione **Novo**.
1. No campo **Nome**, forneça um nome para o novo canal.
1. Selecione a **Entidade legal** apropriada na lista suspensa.
1. Selecione a localização de **Depósito** apropriada na lista suspensa. Esse local será usado como padrão nas ordens de venda criadas para esse canal de call center, a menos que outros padrões tenham sido definidos no nível do cliente ou do item.
1. No campo **Cliente padrão**, forneça um cliente padrão válido. Esses dados são usados para auxiliar no preenchimento automático de padrões quando novos registros de clientes são criados. Ao criar ordens de call center, não é aconselhável criar ordens para o cliente padrão.
1. No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido. À medida que as ordens de call center são criadas e processadas, o perfil de notificação por email é usado para acionar alertas automáticos por email aos clientes com informações sobre o status da ordem.
1. Forneça um código informativo de **Substituição de preço**. Talvez você precise criar um código informativo para isso primeiro. Esse código de informações fornece o conjunto de códigos de motivo que o usuário será solicitado a escolher ao usar a funcionalidade de substituição de preço em uma ordem de call center.
1. Forneça um código informativo de **Código de bloqueio**. Talvez você precise criar um código informativo para isso primeiro. Esse código de informações fornece o conjunto de códigos de motivo opcionais que o usuário será solicitado a escolher ao fazer uma ordem em espera.
1. Forneça um código informativo de **Crédito**. Talvez você precise criar um código informativo para isso primeiro. Esse código de informações fornece o conjunto de códigos de motivo que o usuário pode escolher ao usar a funcionalidade de crédito de ordem do call center para fornecer reembolsos diversos ao cliente por motivos de atendimento ao cliente.
1. Opcional: configure dimensões financeiras na FastTab **Dimensões financeiras**. As dimensões inseridas aqui serão padronizadas em qualquer ordem de venda criada neste canal de call center.
1. Clique em **Salvar**.

A imagem a seguir mostra a criação de um novo canal de call center.

![Novo canal de call center](media/channel-setup-callcenter-1.png)

A imagem a seguir mostra um exemplo de canal de call center.

![Exemplo de canal de call center](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuração adicional do canal

Outras tarefas necessárias para a configuração do canal de call center incluem configurar métodos de pagamento e modos de entrega.

A imagem a seguir mostra opções de configuração de **Modos de entrega** e **Métodos de pagamento** na guia **Configurar**.

![Outras ações de configuração do canal de call center](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, siga as etapas a seguir para cada tipo de pagamento com suporte neste canal. Os usuários deverão selecionar métodos de pagamento predefinidos para vinculá-los ao canal de call center. Antes de configurar os métodos de pagamento do seu call center, primeiro configure os métodos de pagamento principais em **Varejo e Comércio \> Configuração de canal \> Métodos de pagamento \> Métodos de pagamento**.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.
1. No painel de ação, selecione **Novo**.
1. No painel de navegação, selecione um método de pagamento entre os pagamentos predefinidos disponíveis.
1. Defina as configurações adicionais necessárias para o tipo de pagamento. Para cartões de crédito, cartões-presente ou cartões de fidelidade, é necessária uma configuração adicional selecionando a função **Configuração do cartão**. 
1. Configure as contas de lançamento adequadas para o tipo de pagamento na seção **Lançamento**.
1. No painel de ações, clique em **Salvar**.

A imagem a seguir mostra um exemplo de método de pagamento à vista.

![Exemplo de métodos de pagamento](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Configurar os modos de entrega

Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.  

Para alterar ou adicionar um modo de entrega a ser associado ao canal de call center, siga as etapas a seguir.

1. No formulário de modos de entrega de call center, selecione **Gerenciar modos de entrega**
1. No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.
1. Na seção **Canais de varejo**, clique em **Adicionar linha** para adicionar o canal de call center. Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.
1. Verifique se o modo de entrega foi configurado com os dados na FastTab **Produtos** e FastTab **Endereços**. Se nenhum produto ou endereço de entrega for válido para o modo de entrega, a escolha durante a entrada de ordem resultará em erros.
1. Após a alteração das configurações do modo de entrega de call center, o trabalho **Processar modos de entrega** deve ser executado para explodir a matriz de alterações. Esse trabalho pode ser encontrado em **Varejo e Comércio \> TI de Varejo e Comércio \> Processar modos de entrega**.

A imagem a seguir mostra um exemplo de modo de entrega.

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Configurar usuários do canal

Para criar uma ordem de venda que esteja vinculada ao canal de call center da sede do Commerce, o usuário que criar a ordem de venda deverá estar vinculada ao canal de call center. O usuário não poderá vincular manualmente uma ordem de venda criada na sede do Commerce ao canal de call center. O link é sistemático e baseado no usuário e no relacionamento do usuário com o canal de call center. Um usuário pode estar vinculado apenas a um canal de call center.

1. No painel de ação, selecione a guia **Canal** e, depois, **Usuários do canal**.
1. No painel de ação, selecione **Novo**.
1. Escolha uma **ID do Usuário** existente na lista de seleção suspensa para vincular esse usuário ao canal de call center

Depois que a configuração do usuário do canal for concluída e o usuário criar uma ordem de venda na sede do Commerce, a ordem do cliente será vinculada ao canal de call center associado. Quaisquer configurações desse canal serão aplicadas sistematicamente à ordem de venda. Um usuário pode confirmar a qual canal de call center a ordem de venda está vinculada, visualizando a referência do nome do canal no cabeçalho da ordem de venda.


### <a name="set-up-price-groups"></a>Configurar grupos de preços

Os grupos de preços são opcionais, mas, se usados, podem controlar quais preços de venda serão oferecidos aos clientes que fazem ordens no canal de call center. Se um grupo de preços não tiver sido configurado para o cliente ou se os grupos de preços do catálogo não estiverem sendo aplicados à ordem de venda (usando o campo **ID do código-fonte** no cabeçalho da ordem de call center), o grupo de preços do canal é usado para localizar preços de itens. Se um grupo de preços não for encontrado no canal de call center, os preços padrão do item mestre serão usados. 

Para configurar um grupo de preços, faça o seguinte:

1. No painel de ação, clique na guia **Canal** e selecione **Grupos de preços**.
1. No painel de ações, clique em **Novo**.
1. Selecione um **Grupo de preços de varejo** na lista de seleção suspensa.

## <a name="additional-resources"></a>Recursos adicionais

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Funcionalidade de vendas do call center](call-center-functionality.md)

[Configurar opções de processamento de ordens do call center](set-up-order-processing-options.md)

[Catálogos do call center](call-center-catalogs.md)

[Configurar e trabalhar com alertas de fraude](set-up-fraud-alerts.md)

[Configurar programas de continuidade para call centers](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]