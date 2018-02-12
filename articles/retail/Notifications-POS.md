---
title: "Exibir notificações da ordem no ponto de venda"
description: "Este tópico descreve como habilitar notificações de ordem no ponto de venda e a estrutura de notificações, que podem ser estendidas a outras operações."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: aea36591a81f727059e37a958efa62a9ebde9d9d
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2017

---

# <a name="display-notifications-in-point-of-sale"></a>Exibir notificações no ponto de venda

No ambiente de varejo moderno de hoje, são atribuídas várias tarefas aos associados da loja, como auxiliar os clientes, inserir transações, executar contagens de estoque e receber ordens na loja. O cliente do ponto de venda (PDV) capacita os associados a executarem essas tarefas e muito mais, tudo isso com um único aplicativo. Com várias tarefas ser executadas durante um dia, os associados talvez precisem ser notificados quando algo exigir sua atenção. A estrutura de notificação no PDV resolve o problema, permitindo que os fornecedores configurem notificações com base na função. Com o Dynamics 365 for Retail com atualização 5 do Aplicativo, essas notificações somente podem ser configuradas para operações PDV.

Atualmente, o sistema fornece o recurso para exibir notificações para a operação de atendimento da ordem, porém, a estrutura é criada para ser extensível, de forma que no futuro, os desenvolvedores possam gravar um manipulador de notificação para qualquer operação e exibir as notificações no PDV.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Habilitar notificações para operações de atendimento da ordem

Para habilitar notificações para as operações de atendimento da ordem, consulte as seguintes etapas:

 - Vá até a página **Operações** (**Varejo** > **Configuração de canal** > **Configuração de PDV** > **PDV** > **Operações**).
 - Procure a operação de atendimento da ordem e marque a caixa de seleção **Habilitar notificações** para essa operação. Isso indica a estrutura de notificação para detectar o manipulador para a operação de atendimento da ordem. Se o manipulador for implementado, então as notificações serão exibidas no PDV, caso contrário, as notificações não serão exibidas para a operação.
- Vá para as permissões de PDV associadas aos trabalhadores e na Guia Rápida **Notificações**, adicione a operação Atendimento da ordem com a "Ordem de exibição" 1. Quando houver mais de uma notificação configurada, a ordem de exibição será usada para organizar a notificação de cima para baixo com 1 na parte superior. Podem ser adicionadas somente as operações nas quais a caixa de seleção **Habilitar notificações** foi selecionada. Além disso, as notificações serão exibidas apenas para as operações que foram adicionadas aqui e somente para aqueles trabalhadores cujas operações foram adicionadas às permissões de PDV correspondentes. 

> [!NOTE]
> As notificações podem ser substituídas em nível de usuário, navegando para o registro do trabalhador e selecionando **Permissões PDV** e editando a assinatura de notificação do usuário.

 - Vá até a página **Perfil de funcionalidade** (**Varejo** > **Configuração do canal** > **Configuração de PDV** > **Perfis de PDV** > **Perfis de funcionalidade**). Atualize a propriedade **Intervalo de notificação**, para definir o intervalo em minutos no qual as notificações devem ser recebidas. Recomendamos definir esse valor como 10 minutos para evitar comunicação desnecessária para as matrizes. Definir o intervalo de notificação como “0 "desativará as notificações.  

 - Vá para **Varejo** > **TI de Varejo** > **Agenda de distribuição**. Selecione a agenda “” 1060-Equipe para sincronizar configurações de assinatura em notificação e clique em **Executar agora**. Em seguida, sincronize o intervalo de permissão, selecionando "1070-Configuração do canal e, em seguida, clique em **Executar agora**. 

## <a name="view-notifications-in-pos"></a>Exibir notificações no PDV

Depois que as etapas acima forem concluídas, os trabalhadores para quem as notificações forem configuradas poderão exibir notificações no PDV. Para exibir as notificações, clique no ícone de notificação na barra de títulos do PDV. Será exibido um centro de notificação com as notificações da operação de atendimento da ordem. O centro de notificações deve exibir os seguintes grupos na operação de atendimento da ordem: 

- **Ordens pendentes** - Este grupo exibe a contagem de ordens que estão no estado pendente, como as ordens que precisam ser aceitas pelo trabalhador de PDV que têm as permissões necessárias para o atendimento da loja. Clicar no número do grupo abrirá a página **Atendimento da ordem**, filtrada para exibir somente as ordens pendentes atribuídas à loja para atendimento. Se as ordens forem aceitas automaticamente para a loja, a contagem deste grupo será zero.

- **Retirada da loja** - Este grupo exibe a contagem de ordens que têm o modo de entrega **Retirada** e a retirada está agendada na loja atual. Clicar no número do grupo abrirá a página **Atendimento da ordem**, filtrada para exibir as ordens ativas que são configuradas para serem retiradas na loja atual.

- **Remeter da loja** - Este grupo exibe a contagem de ordens que têm o modo de entrega **Remessa** e a remessa está agendada na loja atual. Clicar no número do grupo abrirá a página **Atendimento da ordem**, filtrada para exibir as ordens ativas que são configuradas para serem remetidas da loja atual.

Quando houver novas ordens atribuídas à loja para o atendimento, o ícone de notificação será alterado para indicar que as novas notificações e a contagem de grupos correspondentes serão atualizadas. O usuário também pode clicar no ícone de atualização, ao lado do nome da operação, para atualizar imediatamente a contagem de grupos. A contagem será atualizada também em intervalo predefinido. Qualquer grupo que tenha um novo item, que não é visto pelo trabalhador atual, exibirá um ícone intermitente, indicando que esse grupo tem um novo item. Clicar nos blocos dentro das notificações abrirá a operação específica para a qual essa notificação é configurada. Nos cenários acima, clicar nas notificações abrirá a página **Atendimento da ordem** e informará os parâmetros apropriados: ordens pendentes, retirada na loja e remessa da loja. 

> [!NOTE]
> As notificações de ordens pendentes serão habilitadas em uma próxima atualização do Dynamics 365 for Retail. 


