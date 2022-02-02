---
title: Habilitar notificações de check-in do cliente no ponto de venda (PDV)
description: Este tópico descreve como habilitar notificações de check-in do cliente no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 95b4e3a1750cf072db919492f7445e87654701da
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983152"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Habilitar notificações de check-in do cliente no ponto de venda (PDV)

[!include [banner](includes/banner.md)]

Este tópico descreve como habilitar notificações de check-in do cliente no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

Em emails "ordem pronta para retirada", as organizações podem fornecer um link ou botão que permita aos clientes notificar a loja em que estão no local e aguardar que o pacote seja trazido para eles. Em seguida, os clientes recebem uma confirmação de check-in e a loja recebe uma notificação como uma tarefa no aplicativo de PDV. Essa tarefa serve como um aviso para que um representante de vendas forneça a ordem ao veículo do cliente. Portanto, o cliente não precisa inserir a loja.

O fluxo de trabalho de check-in do cliente também pode ser configurado para coletar informações adicionais de clientes, como o número de vaga de estacionamento, a marca, o modelo, a cor do veículo e instruções de entrega. O atendente da loja de varejo pode usar essas informações para facilitar o atendimento da ordem.

## <a name="enable-customer-check-in"></a>Habilitar o check-in do cliente

Quando o recurso de check-in do cliente é ativado, o Commerce gera uma ID de confirmação de ordem (também conhecida como ID de referência do canal). Ele também gera IDs de confirmação de ordens para ordens criadas por meio de canais de ponto de venda (PDV) ou de call center. 

Para ativar o recurso de check-in de cliente na sede do Commerce, siga estas etapas.

1. Acesse **Espaços de trabalho \> Gerenciamento de recursos**.
2. Procure o recurso **Gerar um formato de ID de referência de canal consistente entre canais**. 
3. Selecione o recurso e, depois, **Habilitar agora** no painel de propriedades. 

## <a name="create-a-check-in-confirmation-page"></a>Criar uma página de confirmação de check-in

No site de comércio eletrônico, você deve criar uma nova página que servirá como a experiência de confirmação do check-in. Por meio de configuração adicional, a página também pode incluir um formulário que coleta informações adicionais de clientes para facilitar o atendimento da ordem. Para obter informações sobre como configurar a página e o módulo, consulte [Módulo de check-in do cliente](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Configurar o modelo de email transacional

Você deve adicionar um link **Estou aqui** ou um botão ao modelo para o email transacional que os clientes recebem quando a ordem está pronta para retirada. Os clientes usarão este link ou botão para notificar a loja de que chegaram para retirar a ordem. 

Adicione o link ou botão ao modelo mapeado para o tipo de notificação **Remessa concluída** e o modo de entrega que você está usando para o atendimento da ordem em frente à loja. No modelo, crie um link ou botão HTML que aponte para a URL da página de confirmação de check-in que você criou e que inclui os nomes e os valores dos parâmetros, conforme mostrado no exemplo a seguir.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Para obter mais informações sobre como configurar modelos de email, consulte [Personalizar emails transacionais por modo de entrega](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Uma tarefa de confirmação de check-in é criada no PDV

Depois que um cliente notifica a loja de que está presente para retirada, a página de check-in mostra uma mensagem de confirmação e um código QR opcional que contém a ID de confirmação da ordem do cliente. Ao mesmo tempo, uma tarefa é criada na lista de tarefas no PDV para a loja em que o cliente está retirando a ordem. Essa tarefa contém todas as informações de cliente e ordem necessárias para atender à ordem. O campo de instruções da tarefa mostra todas as informações coletadas do cliente por meio do formulário de informações adicionais.

## <a name="end-to-end-testing"></a>Teste de ponta a ponta

O check-in do cliente exige que parâmetros e valores específicos sejam passados para a página de check-in e, em seguida, para a API do check-in do cliente. Portanto, a abordagem mais fácil é testar o recurso em um ambiente no qual uma ordem de teste pode ser criada e embalada. Dessa forma, um email de "ordem pronta para retirada" pode ser gerada com uma URL que contém os nomes e valores de parâmetros necessários.

Para testar o recurso de check-in do cliente, siga estas etapas.

1. Crie a página de check-in do cliente e, em seguida, adicione e configure o módulo de check-in do cliente. Para obter mais informações, consulte [Fazer check-in para o módulo de retirada](check-in-pickup-module.md). 
1. Insira a página, mas não a publique.
1. Adicione o link a seguir a um modelo de email que é chamado pelo tipo de notificação de conclusão de embalagem para um modo de entrega de retirada. Para obter mais informações, consulte [Criar modelos de email para eventos transacionais](email-templates-transactions.md).

    - **Para ambientes de pré-produção (UAT):** Adicione o trecho de código na seção [Configurar o modelo de email transacional](#configure-the-transactional-email-template) anteriormente neste tópico.
    - **Para ambientes de produção:** Adicione o seguinte código comentado para que os clientes existentes não sejam afetados.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Crie uma ordem em que o modo de entrega de retirada é especificado.
1. Ao receber o email disparado pelo tipo de notificação de conclusão de embalagem, teste o fluxo do check-in abrindo a página de check-in que tem a URL que você adicionou anteriormente. Como a URL inclui o sinalizador `&preview=inprogress`, você será solicitado a autenticar para que possa exibir a página.
1. Insira as informações adicionais necessárias para configurar o módulo.
1. Verifique se a exibição de confirmação de check-in é exibida corretamente.
1. Abra o terminal de PDV da loja em que a ordem será retirada.
1. Selecione o bloco **Ordens a serem retiradas** e verifique se a ordem é exibida.
1. Verifique se qualquer informação adicional configurada no módulo de check-in é exibida no painel de detalhes.

Depois de verificar se o recurso de check-in do cliente funciona de ponta a ponta, siga estas etapas.

1. Publique a página de check-in.
1. Se você estiver testando em um ambiente de produção, retire os comentários da URL no modelo de email de "ordem pronta para retirada" para que o link **Estou aqui** seja exibido. Em seguida, recarregue o modelo.

## <a name="additional-resources"></a>Recursos adicionais

[Fazer check-in para o módulo de retirada](check-in-pickup-module.md)

[Personalizar emails transacionais por modo de entrega](customize-email-delivery-mode.md)

[Criar modelos de email para eventos transacionais](email-templates-transactions.md)
