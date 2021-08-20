---
title: Habilitar notificações de check-in do cliente no ponto de venda (PDV)
description: Este tópico descreve como habilitar notificações de check-in do cliente no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
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
ms.openlocfilehash: cf9331e1da54520787686a3f190e2ef6d150c0c10bd521919407f5e6c74551d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774574"
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

Adicione o link ou botão ao modelo mapeado para o tipo de notificação **Remessa concluída** e o modo de entrega que você está usando para o atendimento da ordem em frente à loja. No modelo, crie um link ou botão HTML que aponta para a URL da página de confirmação de check-in criada. Veja aqui um exemplo.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Para obter mais informações sobre como configurar modelos de email, consulte [Personalizar emails transacionais por modo de entrega](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Uma tarefa de confirmação de check-in é criada no PDV

Depois que um cliente notificar a loja em que estão presentes para retirada, eles receberão uma notificação de confirmação de check-in e uma tarefa será criada na lista de tarefas no PDV para a loja em que o cliente retira a ordem. A tarefa contém todas as informações de cliente e ordem necessárias para atender à ordem. Na tarefa, o campo de instruções mostra todas as informações coletadas do cliente por meio do formulário de informações adicionais. 

## <a name="additional-resources"></a>Recursos adicionais

[Fazer check-in para o módulo de retirada](check-in-pickup-module.md)
