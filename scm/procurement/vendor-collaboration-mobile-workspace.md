---
title: "Colaboração de fornecedor móvel disponível em estoque para o aplicativo Microsoft Dynamics 365 for Operations"
description: "Com a área de trabalho móvel de colaboração do fornecedor, os fornecedores podem manter-se atualizados sobre os pedidos que foram enviados a eles para aprovação e exibir informações sobre pedidos e contatos novos e atualizados."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d5157e6f4b10b6158aa08279a9f68dae676f5666
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Colaboração de fornecedor móvel disponível em estoque para o aplicativo Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Com a área de trabalho móvel de colaboração do fornecedor, os fornecedores podem manter-se atualizados sobre os pedidos que foram enviados a eles para aprovação e exibir informações sobre pedidos e contatos novos e atualizados.

<a name="prerequisites"></a>Pré-requisitos
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Leia sobre a plataforma móvel do Microsoft Dynamics 365 for Operations</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Plataforma móvel do Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Verifique se você está usando um ambiente com a versão 1611 do Microsoft Dynamics 365 for Operations e a atualização 3 da plataforma do Microsoft Dynamics for Operations (novembro de 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Dispositivo móvel com o Dynamics 365 for Operations instalado</span></td>
<td><span style="color: #000000">Baixe o aplicativo do Dynamics 365 for Operations na sua loja de aplicativos móveis.</span></td>
</tr>
<tr class="even">
<td>Hotfix KB 4013633</td>
<td>Instale o hotfix para habilitar os espaços de trabalho que são fornecidos no Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Hotfix KB 3216943</span> </span></td>
<td>Instale o hotfix para habilitar o espaço de trabalho do celular de colaboração de fornecedor.</td>
</tr>
<tr class="even">
<td>O usuário do fornecedor deve ter acesso à interface da Web de colaboração do fornecedor no Dynamics 365 for Operations e configurar um usuário de colaboração do fornecedor.</td>
<td>Siga as etapas descritas nos tópicos a seguir para configurar e trabalhar com a interface da Web de colaboração do fornecedor.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Use a colaboração do fornecedor para trabalhar com fornecedores externos</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Gerenciar usuários de colaboração do fornecedor</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Configurar e manter colaboração de fornecedor</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Usar colaboração de fornecedores para trabalhar com clientes no Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Visão Geral
O espaço de trabalho móvel de colaboração de fornecedor mantém os fornecedores informados sobre novas ordens de compra para que eles possam ver e responder a ordens de compra no cliente da Web do Dynamics 365 for Operations. 

**Observação:** O espaço de trabalho móvel deve ser usado como um suplemento para a interface da Web de colaboração do fornecedor, mas não como uma substituição. 

Com a área de trabalho móvel de colaboração de fornecedor, seus fornecedores podem exibir novas ordens de compra enviadas para aprovação. Ele exibe informações sobre pedidos, como produtos, quantidade e datas de remessa solicitadas. As informações de preço estão disponíveis, dependendo da configuração de cada fornecedor. 

Quando um usuário faz logon como um fornecedor, ele vê quais pedidos de compra foram respondidos ou quais pedidos de compra ainda aguardam ação do cliente. O fornecedor pode ter sugerido outra data de entrega que ainda não foi acordada com o cliente para que o pedido esteja aguardando a ação do cliente. O fornecedor também verá uma lista de pedidos confirmados, mas ainda não entregues. 

Para responder a uma ordem de compra, o fornecedor deve usar a interface da Web de colaboração do fornecedor que está disponível no cliente da Web do Dynamics 365 for Operations. Isso também é onde o fornecedor obterá mais informações sobre a ordem, como anexos de documentos, endereço de entrega por linha e taxas associadas ao fornecedor. 

Com um papel de segurança especial, o fornecedor pode ver quais pessoas de contato estão registradas para uma conta de fornecedor. Com a mesma função de segurança, o fornecedor pode visualizar o status de qualquer solicitação de usuário que tenha sido enviada. 

A criação de novos contatos e o envio de novas solicitações de usuário devem ser feitas na interface de colaboração do fornecedor que está disponível no cliente da Web Dynamics 365 for Operations. 

Com o espaço de trabalho móvel, o fornecedor pode:

-   Ver novos pedidos enviados ao fornecedor.
-   Ver ordens de compra que o fornecedor respondeu e está aguardando ação do cliente.
-   Ver pedidos que estão em um estado confirmado e não foram totalmente recebidos.
-   Exibir informações de pessoa de contato que está registrado para a conta do fornecedor (requer uma função de segurança adicional).
-   Visualize informações e siga o status de uma solicitação de usuário enviada pelo fornecedor (requer uma função de segurança adicional).

## <a name="get-started"></a>Introdução
Para começar em seu dispositivo móvel:

1.  Na sua loja de aplicativos móveis, baixe e instale o aplicativo do Microsoft Dynamics 365 for Operations.
2.  Inicie o aplicativo no seu dispositivo.
3.  Insira sua URL do Dynamics 365.
4.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
5.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Microsoft Dynamics 365 for Operations.

Depois de fazer o login no aplicativo, nenhum espaço de trabalho é visível. Para exibir os espaços de trabalho no seu aplicativo móvel, primeiro você deve publicar os espaços de trabalho desejados para o aplicativo do Dynamics 365 for Operations. É necessário permissão do administrador do sistema para publicar a área de trabalho.

1.  Inicie o Dynamics 365 for Operations.
2.  Vá para **Administração do sistema** &gt; **Configuração** &gt; **Parâmetros do sistema**.
3.  Selecione o **Gerenciar aplicativo móvel**.
4.  Selecione o espaço de trabalho **Colaboração de fornecedor** para publicar na plataforma móvel.
5.  Selecione **Publicar espaço de trabalho**.
6.  Atualize seu dispositivo para ver os espaços de trabalho publicados.
7.  Selecione o espaço de trabalho **Colaboração de fornecedor**. Você verá a próxima página.

    [![vendor-collaboration-mobile-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contatos
A página **Contatos** permite ver todos os contatos que foram configurados para a conta do fornecedor. Ele mostra o nome da pessoa de contato, o e-mail principal e o alias do usuário, se disponível. Também mostra se a conta de usuário da pessoa de contato está ativa. Quando você seleciona um contato, você vê os detalhes do contato, como para quais entidades legais a pessoa é um contato, e as informações de contato, como número de telefone ou um endereço de e-mail diferente.

## <a name="user-requests"></a>Solicitações do usuário
A página **Solicitações de usuário** permite ver todas as solicitações de usuário enviadas por meio da interface da Web de colaboração do fornecedor e acompanhar o status. Quando você seleciona uma solicitação de usuário, você pode ver o que foi solicitado, adicionar ou desativar um usuário, alterar a segurança e ver quais funções de segurança foram solicitadas para o usuário.

## <a name="purchase-orders-ready-for-review"></a>Ordens de compra prontas para revisão
A página **Ordens de compra prontas para revisão** permite que você veja todos os pedidos que foram enviados pelo cliente e não foram respondidos. Você pode exibir informações selecionadas sobre a ordem, como quais produtos foram solicitados e quando entregar. As informações de preço só estão disponíveis se estiverem configuradas para o fornecedor. Você pode ver se o pedido tem notas ou anexos. Para abrir anexos, você precisa usar a colaboração do fornecedor no cliente da Web. Selecione **Linha de ordem de compra** para ver todas as linhas com detalhes. Note que para cada linha, um indicador irá mostrar se há notas ou anexos ou se há um endereço de entrega que é diferente do que é mostrado no cabeçalho. Para responder à ordem de compra, você deve usar o cliente da Web de colaboração do fornecedor.

## <a name="awaiting-customer-action"></a>Aguardando ação do cliente
A página **Aguardando ação de clientes** permite que você encontre ordens de compra que você, ou alguém de sua empresa que também tem acesso à colaboração do fornecedor, tenha respondido. As ordens de compra só são visíveis nesta lista se o cliente precisar executar uma das seguintes ações na ordem de compra.

-   Se a ordem de compra foi rejeitada, o cliente precisaria atualizar a ordem enviada e enviá-la novamente, ou cancelar a ordem e reenviá-la. Quando o pedido for enviado novamente, ele desaparecerá da página **Aguardando ação de clientes**.
-   Se a ordem de compra foi aceita com alterações, o cliente precisaria atualizar a ordem original e reenviá-la para revisão ou atualizá-la de acordo com as alterações e confirmá-la imediatamente. Em ambos os casos, a ordem de compra desaparecerá da página **Aguardando ação de clientes**.
-   Se a ordem de compra foi aceita e aparece na página **Aguardando ação de clientes**, é porque o pedido não foi confirmado automaticamente quando a aceitação foi feita. Ele está aguardando que um agente de compras altere a ordem para Confirmado. Normalmente, o pedido será considerado como um acordo entre o cliente e o vendedor assim que o fornecedor aceitar a ordem. Mover a ordem de compra para o estado Confirmado seria uma formalidade.

Ao selecionar a ordem de compra, detalhes adicionais aparecem sobre a resposta. Você pode ver os detalhes da linha e resposta para cada linha. O status da linha mostra quais das respostas a seguir foram dadas.

-   Aceito
-   Rejeitada
-   Aceito com alterações
-   Substituído / Substituto
-   Separação no plano/linha do plano

Observe que um indicador mostra **Entregando**=sim/não, que é usado para indicar que as linhas não serão entregues. Isso pode ser porque a linha foi rejeitada ou substituída onde as linhas originais não devem ser entregues, ou uma linha que foi dividida em várias linhas de agendamento e a linha original não deve ser entregue conforme solicitado na ordem recebida. Todas as alterações feitas na resposta da linha de pedido são exibidas, exceto para as notas e anexos enviados, que você pode ver usando a interface da Web de colaboração do fornecedor.

## <a name="open-confirmed-orders"></a>Abrir ordens confirmadas
Quando a ordem de compra é confirmada pelo cliente, o que significa que a ordem de compra foi alterada para o estado Confirmado, ela aparecerá na ordem confirmada aberta. Ela permanecerá na lista até que seja registrado como recebido pelo cliente.





