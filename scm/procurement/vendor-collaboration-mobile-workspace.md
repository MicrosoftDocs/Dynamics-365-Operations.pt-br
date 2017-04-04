---
title: "O espaço de trabalho móvel de colaboração de fornecedor do Microsoft Dynamics 365 para o descritivo de operações"
description: "Com espaço de trabalho de colaboração móvel do fornecedor, os fornecedores podem ficar atualizados em ordens de compra que lhes foram enviados para aprovação e exibem informações sobre novas ordens de compra e atualizados e contatos."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>O espaço de trabalho móvel de colaboração de fornecedor do Microsoft Dynamics 365 para o descritivo de operações

Com espaço de trabalho de colaboração móvel do fornecedor, os fornecedores podem ficar atualizados em ordens de compra que lhes foram enviados para aprovação e exibem informações sobre novas ordens de compra e atualizados e contatos.

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
<td>Leia sobre o Microsoft Dynamics 365 para o preparo de celular de operações</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 para o preparo de celular de operações</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Verifique se está usando um ambiente com Microsoft Dynamics 365 para a versão 1611 de operações e o Microsoft Dynamics para atualização 3 de preparo operações (). em novembro de 2016</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Dispositivo móvel que tem o dynamics 365 para o descritivo instalado de operações</span></td>
<td><span style="color: #000000;">Baixe o dynamics 365 para o descritivo de operações do armazenamento móvel descritivo.</span></td>
</tr>
<tr class="even">
<td>3215650 KB de Hotfix</td>
<td>Instalar o hotfix para habilitar espaços de trabalho fornecidos em dynamics 365 para as operações.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">3216943 KB de Hotfix</span></span></td>
<td>Instalar o hotfix para habilitar o espaço de trabalho do celular de colaboração de fornecedor.</td>
</tr>
<tr class="even">
<td>O usuário o fornecedor deverá ter acesso à interface da Web de colaboração de fornecedor em dynamics 365 para operações e configurados um usuário de colaboração de fornecedor.</td>
<td>Rastrear as etapas descritas nos tópicos seguintes para configurar e trabalhar com a interface da Web de colaboração de fornecedor.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Use a colaboração de fornecedor para trabalhar com fornecedores externos</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gerenciar usuários de colaboração do fornecedor</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Configurar e manter colaboração de fornecedor</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Use a colaboração de fornecedor para trabalhar com os clientes em dynamics 365 para operações</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Visão Geral
O espaço de trabalho de colaboração móvel do fornecedores mantém informados sobre novas ordens de compra para que possam exibir e responder ordens de compra em dynamics para o 365 clientes web de operações.  

** Observação: ** O espaço de trabalho móvel deve ser usado como manuais suplementam interface da Web para a colaboração de fornecedor, mas não uma substituição.  

Com espaço de trabalho de colaboração móvel do fornecedor, os fornecedores podem exibir as ordens de compra que são enviados para aprovação. Exibe informações de ordem de compra, como produto, quantidade, e datas de entrega solicitada. O preço está disponível, dependendo da configuração de cada fornecedor.  

Quando um usuário fizer logon como um fornecedor, que outras ordens de compra foram respondidos, ou as ordens de compra ainda estão aguardando a ação do cliente. O fornecedor pode ter sugerido outra data de entrega que não foi concordada ainda ao cliente para que a ordem de compra está aguardando a ação do cliente. O fornecedor também verá uma lista de ordens de compra que forem confirmados mas que ainda.  

Responda a ordem de compra, o fornecedor tem que o uso da interface Web para a colaboração de fornecedor disponíveis em dynamics para o 365 clientes web de operações. Isso também é o local onde o fornecedor obterão mais informações sobre a ordem, como anexos de documentos, o endereço de entrega, por linha e os encargos ao fornecedor.  

Com uma função de segurança especial, o fornecedor pode exibir as pessoas de contato são registradas para uma conta de fornecedor. Com a mesma função de segurança, o fornecedor pode exibir o status de qualquer solicitação de usuário que é enviada.  

Criar novos contatos e enviar solicitações novas do usuário deve ser realizadas na interface de colaboração de fornecedor disponíveis em dynamics para o 365 clientes web de operações.  

Com espaço de trabalho móvel, o fornecedor pode:

-   Ordens de compra de exibição enviados para o fornecedor.
-   Ordens de compra de exibição que respondeu ao fornecedor e está aguardando a ação do cliente.
-   Exibir ordens de compra que estão no estado confirmado e fim não foram recebidos.
-   Exiba informações da pessoa de contato registrada para a conta de fornecedor (necessário uma função de segurança adicionais.)
-   Exibir informações e para rastrear o status de uma solicitação de usuário por fornecedor (enviada requer uma função de segurança adicionais.)

## <a name="get-started"></a>Introdução
Para obter iniciado no dispositivo móvel:

1.  No armazenamento móvel descritivo, baixar e instalar o Microsoft Dynamics 365 para o descritivo de operações.
2.  Inicie a descritivo no dispositivo.
3.  Insira a URL do 365.
4.  Insira a empresa para conectar-se. Por exemplo, insira USMF ** **.
5.  A primeira vez que que se conectar, será solicitado para o nome de usuário e a senha para o Microsoft Dynamics 365 para a conta de operações. 

Depois que você insere descritivo, nenhum espaço de trabalho estará visível. Exibir espaços de trabalho do celular descritivo, primeiramente publicar espaços de trabalho o dynamics desejados para o 365 descritivo de operações. Você precisa permissão de administração de sistema publicar o espaço de trabalho.

1.  Dynamics 365 Inicial para as operações.
2.  Ir ** administração de sistema ** &gt; ** de instalação ** &gt; ** ** parâmetros do sistema.
3.  Selecione ** gerenciamento descritivo móvel **.
4.  Selecione o espaço de trabalho ** colaboração fornecedor ** publicar a plataforma móvel.
5.  ** Publicar selecione o espaço de trabalho. **
6.  Atualizar o dispositivo para consultar espaços de trabalho publicados.
7.  ** Colaboração selecionar fornecedor ** o espaço de trabalho. Você a próxima página.

[fornecedor-colaboração-celular- descritivo![(]. /media/vendor-collaboration-mobile-app.png)](. /media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contatos
** Contatos ** o página permite ver todos os contatos que foram configurados para a conta de fornecedor. Mostra o nome da pessoa de contato, email principal, apelidos e de usuários, se disponível. Também mostra se a conta de usuário da pessoa de contato ativa. Quando você seleciona um contato, é possível ver os detalhes de contato, como entidades legais que a pessoa é um contato de, e informações de contato como número de telefone ou um endereço de email a outro.

## <a name="user-requests"></a>Solicitações do usuário
** Solicitações de usuário ** o página permite ver todas as solicitações de usuário que enviou através da interface da Web de colaboração de fornecedor e rastrear status. Quando você seleciona uma solicitação de usuário, você pode ver o que foi solicitado, adicionar ou neutraliza um usuário, alterar a consulta e segurança, funções de segurança que foi solicitada para o usuário.

## <a name="purchase-orders-ready-for-review"></a>Ordens de produção prontas para revisão
** Ordens de produção prontas para revisão ** o página permite que todas as ordens de compra que foram enviados por cliente e ter ser atendido. Você pode exibir informações sobre a ordem selecionada, como ao produto foram solicitados e quando entregar. O preço está disponível apenas se for configurada para o fornecedor.  

Você veja se a ordem de compra tiver notas ou todos. Para abrir anexos, você precisará usar a colaboração de fornecedor em clientes web. ** Selecione linha de ordem de compra ** para ver todas as linhas com detalhes. Lembre-se que para cada linha, um indicador mostrará se houver um ou notas anexos ou se houver um endereço de entrega que é diferente do que é exibido no cabeçalho.  

Responda à ordem de compra, você deve usar a web client de colaboração de fornecedor.

## <a name="awaiting-customer-action"></a>Aguardando ação do cliente
** Aguardando ação de clientes ** permite localizar a página ordens de compra a que você, alguém ou na empresa também que tem acesso a colaboração de fornecedor, responderam. Ordens de compra só estão visíveis nesta lista se o cliente precisa executar uma destas ações na ordem de compra.

-   Se a ordem de compra foi rejeitado, cliente ou precisaria atualizar a ordem de remessa e enviado novamente, ou cancele a ordem e envie-o novamente. Quando a ordem de compra é enviado novamente, desaparecerá ** aguardando ação de clientes ** de página.
-   Se a ordem de compra foi aceita alterações com, cliente precisaria atualizar a ordem original e de enviá-lo novamente para revisão, atualizar ou de acordo com as alterações e confirme-a imediatamente. Em ambos os casos, a ordem de compra desaparecerá ** aguardando ação de clientes ** de página.
-   Se a ordem de compra foi aceita e aparece ** aguardando ação ** de cliente na página, é como a ordem de compra não foi confirmada automaticamente quando a aceitação foi feita. Estiver aguardando um agente de compras para alterar a ordem para confirmado. Normalmente, a ordem de compra será considerado como um contrato entre o cliente e fornecedor assim o fornecedor aceitasse a ordem. Mova a ordem de compra ao estado confirmado é uma formalidade.

Marcando a ordem de compra, os detalhes são exibidos sobre a resposta. Você pode ver detalhes da linha e a resposta para cada linha. A linha de status a seguir mostra que recebeu respostas.

-   Aceito
-   Rejeitada
-   Aceito com alterações
-   Substituto substituído/
-   Separação no plano/linha do plano

Observe que mostra um indicador ** ** =yes/no entregues, usado para indicar que as linhas não serão entregues. Isso pode ocorrer porque a linha foi rejeitada, substituído ou em linhas original não deve ser entregues, ou uma linha que é dividida em várias linhas do plano e a linha original não deverá ser entregue como solicitado na ordem recebidas.  

Todas as alterações feitas na linha da resposta são exibidas, exceto as observações de anexos cobrados, que você pode perceber usando a interface da Web de colaboração de fornecedor.

## <a name="open-confirmed-orders"></a>Abra confirmados ordens
Quando a ordem de compra for confirmada pelo cliente, que significa que a ordem de compra será alterado para o estado confirmado, aparecerá confirmado a ordem em aberto. Ficará na lista até seja registrado como recebida pelo cliente.


