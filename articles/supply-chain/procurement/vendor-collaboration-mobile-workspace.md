---
title: Espaço de trabalho móvel de colaboração de fornecedor
description: Este artigo fornece informações sobre a área de trabalho móvel de colaboração do Fornecedor. Esta área de trabalho ajuda seus fornecedores a se manter atualizados sobre as ordens de compra que foram enviadas para aprovação. Eles também podem visualizar informações sobre contatos e ordens de compra novos e atualizados.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: gfedorova
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 591d4269a1188ed8f098a342729ba49b9772f42d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851642"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Espaço de trabalho móvel de colaboração de fornecedor

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Este artigo fornece informações sobre a área de trabalho móvel **Colaboração do fornecedor**. Esta área de trabalho ajuda seus fornecedores a se manter atualizados sobre as ordens de compra que foram enviadas para aprovação. Eles também podem visualizar informações sobre contatos e ordens de compra novos e atualizados.

Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel de finanças e operações (Dynamics 365).

## <a name="overview"></a>Visão geral 
O espaço de trabalho móvel **Colaboração do fornecedor** mantém os fornecedores informados sobre novas ordens de compra para que eles possam ver e responder a ordens de compra no cliente Web. 

>[!NOTE]
> O espaço de trabalho móvel deve ser usado como um suplemento para a interface da Web de colaboração do fornecedor, não como uma substituição. 

Seus fornecedores podem usar a área de trabalho móvel **Colaboração de fornecedor** para ver as novas ordens de compra que são enviadas para aprovação. Ele exibe informações sobre pedidos, como produtos, quantidades e datas de remessa solicitadas. As informações de preço estão disponíveis, dependendo da configuração de cada fornecedor. 

Um usuário que faz logon como um fornecedor vê quais pedidos de compra foram respondidos e quais pedidos de compra ainda aguardam ação do cliente. Por exemplo, uma ordem de compra pode aguardar a ação do cliente porque o fornecedor sugeriu outra data de entrega, mas o cliente ainda não concordou com essa data. O fornecedor também verá uma lista de ordens de compra que foram confirmadas, mas ainda não foram entregues. 

Para responder a uma ordem de compra, o fornecedor deve usar a interface da Web de colaboração do fornecedor que está disponível no cliente da web. Lá, o fornecedor também poderá obter mais informações sobre a ordem, como anexos de documentos, endereço de entrega por linha e taxas associadas ao fornecedor. 

Os fornecedores que possuem uma função de segurança especial podem ver quais pessoas de contato estão registradas para uma conta de fornecedor. Com a mesma função de segurança, o fornecedor pode visualizar o status de qualquer solicitação de usuário que tenha sido enviada. 

A interface da web de colaboração do fornecedor no cliente da web deve ser usada para criar novos contatos e enviar novos pedidos de usuários. 

A área de trabalho móvel **Colaboração de fornecedor** permite ao fornecedor realizar essas tarefas:

-   Exiba as novas ordens de compra que são enviadas para o fornecedor.
-   Exiba as ordens de compra que o fornecedor respondeu e está aguardando ação do cliente.
-   Exiba as ordens de compra que foram confirmadas, mas que ainda não foram totalmente recebidas.
-   Exiba as informações da pessoa de contato que está registrada para a conta do fornecedor. (Esta tarefa requer uma função de segurança adicional.)
-   Exiba as informações sobre um pedido de usuário que foi enviado pelo fornecedor e siga o status da solicitação. (Esta tarefa requer uma função de segurança adicional.)

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos variam conforme a versão do Microsoft Dynamics 365 implantada na organização.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Pré-requisito para usar o Supply Chain Management
Se o Supply Chain Management foi implantado para sua organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Colaboração do fornecedor**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Pré-requisitos se você usa a versão 1611 do Microsoft Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior
Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir. 

<table>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>O KB 3216943 deve ser implementado se você estiver usando a atualização da plataforma 3.</td>
<td>Administrador do sistema</td>
<td>KB 3216943 é uma atualização binária que é necessária se você estiver usando a atualização da plataforma 3. Para implementar este KB, o administrador do sistema deve seguir estas etapas.
<ol>
<li>Baixe o KB 3216943 do Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Instale a atualização binária, que é entregue como um pacote implantável. Para obter informações sobre como aplicar um pacote implantável, consulte<a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar um pacote implantável</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>O KB 4013633 deve ser implementado.</td>
<td>Administrador do sistema</td>
<td>o KB 4013633 é um hotfix de metadados ou uma atualização X++ que contém o espaço de trabalho móvel de <strong>Estoque disponível</strong>. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Baixe o hotfix de metadados de LCS</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar o pacote implantável</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>A área de trabalho móvel <strong>Colaboração de fornecedor</strong> deve ser publicada.</td><td>Administrador do sistema</td>
<td>Consulte <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
<tr class="even">
<td>O usuário do fornecedor deve ter acesso à interface da web de colaboração do fornecedor no cliente da web e deve configurar um usuário de colaboração do fornecedor.</td><td>Profissionais de compras e o administrador do sistema</td>
<td>Siga as etapas nos artigos a seguir para configurar e trabalhar com a interface da Web de colaboração do fornecedor.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Use a colaboração do fornecedor para trabalhar com fornecedores externos</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gerenciar usuários de colaboração do fornecedor</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">​Configurar e manter colaboração de fornecedor​</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Usar a colaboração do fornecedor para trabalhar com clientes no Supply Chain Managements</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.

Baixe e instale o aplicativo móvel de finanças e operações (Dynamics 365):

-   [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel
1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira a URL do Microsoft Dynamics 365.
4.  Na primeira vez que você iniciar a sessão, será solicitado a você o nome de usuário e senha. Insira suas credenciais.
5.  Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

    [![Efetue pull para atualizar.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Use a área de trabalho móvel de colaboração de fornecedor
Quando você selecionar a área de trabalho **Colaboração de fornecedor**, você verá as seguintes opções.

![Espaço de trabalho móvel de colaboração de fornecedor.](./media/vendor-collaboration-mobile-app.png)

A área de trabalho **Colaboração de fornecedor** inclui as seguintes páginas.

### <a name="contacts"></a>Contatos
A página **Contatos** permite ver todos os contatos que foram configurados para a conta do fornecedor. Mostra o nome da pessoa de contato, o endereço de e-mail principal, e apelido de usuário, se o contato tiver um apelido. Esta página também mostra se a conta de usuário da pessoa de contato está ativa. Quando você seleciona um contato, você vê os detalhes do contato, como as entidades legais para as quais uma pessoa é um contato. Você também vê informações de contato, como um número de telefone ou um endereço de e-mail alternativo.

### <a name="user-requests"></a>Solicitações do usuário
A página **Solicitações de usuário** permite ver todas as solicitações de usuário enviadas por meio da interface da web de colaboração do fornecedor. Você também pode acompanhar o status desses pedidos. Quando você seleciona uma solicitação de usuário, você pode ver o que foi solicitado, adicionar ou desativar um usuário, alterar a segurança e ver quais funções de segurança foram solicitadas para o usuário.

### <a name="purchase-orders-ready-for-review"></a>Ordens de compra prontas para revisão
A página **Ordens de compra prontas para revisão** permite que você veja todas as ordens de compra que o cliente enviou, mas que ainda não foram respondidas. Você pode ver as informações selecionadas sobre a ordem, como quais produtos foram solicitados e quando esses produtos devem ser entregues. As informações de preço estão disponíveis, dependendo da configuração do fornecedor.

Você também pode ver se o pedido tem notas ou anexos. No entanto, para abrir notas e anexos, você deve usar a interface da web de colaboração do fornecedor no cliente da web. Selecione **Linha de ordem de compra** para ver todas as linhas juntamente com seus detalhes. Para cada linha, um indicador mostrará se há notas ou anexos ou se o endereço de entrega difere do endereço de entrega que é mostrado no cabeçalho.

Para responder à ordem de compra, você deve usar a interface da web de colaboração do fornecedor no cliente da web.

### <a name="awaiting-customer-action"></a>Aguardando ação do cliente
A página **Aguardando ação de clientes** permite que você ache pedidos de compra que você ou outra pessoa da sua empresa com acesso à colaboração de fornecedores tenha respondido. As ordens de compra estão visíveis nessa lista somente se o cliente precisar tomar uma das seguintes ações no pedido:

-   Se a ordem de compra foi rejeitado, o cliente deve atualizar ou cancelar a ordem original e, em seguida, enviá-la novamente. Quando a ordem de compra for enviada novamente, ela não aparecerá mais na página **Aguardando ação de clientes**.
-   Se a ordem de compra foi aceita com alterações, o cliente deve atualizar a ordem original e depois enviá-la novamente para revisão, ou atualizar a ordem de acordo com as mudanças solicitadas e, em seguida, confirmá-la imediatamente. Em ambos os casos, a ordem de compra não aparece mais na página **Aguardando ação de clientes**.
-   Se a ordem foi aceita, mas ainda aparece na página **Aguardando ação de clientes**, a ordem de compra não foi confirmada automaticamente quando foi aceita. Agora está aguardando que um agente de compras altere o status da ordem para **Confirmado**. Normalmente, uma ordem de compra é considerado um acordo entre o cliente e o fornecedor assim que o fornecedor aceitar a ordem. Portanto, a atualização para o status **Confirmado** é normalmente apenas uma formalidade.

Quando você seleciona uma ordem de compra, detalhes adicionais aparecem sobre a resposta. Você pode ver os detalhes da linha e resposta para cada linha. O status da linha mostra quais das respostas a seguir foram dadas:

-   Aceito
-   Rejeitada
-   Aceito com alterações
-   Substituído / Substituto
-   Separação no plano/linha do plano

Observe que o campo **Entrega** é definido para **Sim** ou **Não** para indicar se as linhas serão entregues. Uma linha pode não ser entregue porque, pelas seguintes razões:

- A linha foi rejeitada.
- Foi feita uma substituição, e a linha original não deve ser entregue conforme solicitado na ordem recebida.
- A linha foi dividida em várias linhas de cronograma, e a linha original não deve ser entregue conforme solicitado na ordem recebida.

Todas as alterações feitas na resposta da linha de ordem são mostradas. No entanto, as notas e anexos carregados não são mostrados. Para ver notas e anexos, você deve usar a interface da web de colaboração do fornecedor no cliente da web.

### <a name="open-confirmed-orders"></a>Abrir ordens confirmadas
Quando a ordem de compra é confirmada pelo cliente (ou seja, o status da ordem de compra é alterado para **Confirmado**), ela aparece na ordem confirmada aberta. Ela permanecerá na lista até que seja registrado como recebido pelo cliente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
