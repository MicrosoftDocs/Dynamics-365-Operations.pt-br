---
title: Gerenciar usuários de colaboração do fornecedor
description: Este tópico descreve como você pode solicitar o provisionamento de novos usuários de colaboração do fornecedor e como adicionar novos contatos de colaboração do fornecedor.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 50ce332673e130dace38f596020973d37c34b566
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813491"
---
# <a name="manage-vendor-collaboration-users"></a>Gerenciar usuários de colaboração do fornecedor

[!include [banner](../includes/banner.md)]

Este tópico descreve como você pode solicitar o provisionamento de novos usuários de colaboração do fornecedor e como adicionar novos contatos de colaboração do fornecedor. 

A interface de colaboração do fornecedor no Dynamics 365 Supply Chain Management expõe informações sobre ordens de compra, faturas e estoque de consignação para fornecedores externos. Você pode criar novos contatos de colaboração de fornecedor e solicitar que os novos usuários sejam provisionados se você estiver trabalhando com um fornecedor externo com a função de segurança **Administrador do fornecedor (externo)** ou permissões semelhantes. Você também pode executar essas tarefas se estiver trabalhando como um profissional de compras. Neste tópico, essa função se refere a um profissional de compras que esteja trabalhando na empresa responsável pela instância do Supply Chain Management. Para obter mais informações sobre como usar a colaboração de fornecedor se você for um fornecedor externo, consulte [Colaboração do fornecedor com clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para obter mais informações sobre como usar a colaboração de fornecedor se você for um profissional de compras, consulte [Colaboração do fornecedor com fornecedores externos](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Adicionar novos contatos de colaboração do fornecedor
Se você deseja que pessoa tenha acesso à colaboração do fornecedor, primeiramente é preciso adicioná-la como um contato de colaboração do fornecedor. Você também pode querer adicionar contatos para funcionários da sua empresa que não usarão a colaboração do fornecedor. Por exemplo, eles podem ser o ponto de contato para outros tipos de informações de compras. Novos contatos são adicionados na página **Todos os contatos**, que é acessada do menu **Colaboração do fornecedor** &gt; **Contatos**. Para adicionar um novo contato:

1.  Clique em **Novo**.
2.  Insira os detalhes da pessoa de contato.
3.  Indique qual entidade legal ela está representando em sua empresa e com qual entidade legal ela trabalhará na empresa com a qual ela colaborará. Isso é feito selecionando um par **Entidade legal na minha empresa**/**Entidade legal na empresa do cliente**.
4.  Clique em **Criar**.

Se quiser excluir um contato, você poderá excluir somente aqueles que criou.

## <a name="vendor-collaboration-user-requests"></a>Solicitações de usuário de colaboração do fornecedor
Solicitações de usuário de colaboração do fornecedor podem ser feitas por um profissional de compras ou por um administrador de fornecedores externos.

-   Se for um fornecedor externo, você envia solicitações da página **Todos os contatos** no módulo **Colaboração do fornecedor**.
-   Se você for um profissional de compras, envie solicitações da página **Exibir contatos**. Para fazer isso, no registro de fornecedor, na seção **Configuração** no painel Ação, selecione **Contatos** &gt; **Exibir contatos**.

Você pode fazer uma solicitação para provisionar um usuário, desativar um usuário ou modificar funções de segurança. Se você for um administrador de fornecedores externos, você deve estar registrado como uma pessoa de contato para contas de fornecedor para as quais deseja fazer solicitações de usuário e deverá ter acesso à interface de colaboração do fornecedor para essas contas de fornecedor.  

Quando uma solicitação é enviada, ela será adicionada a lista **Solicitações de usuário de colaboração do fornecedor** no módulo **Colaboração do fornecedor** e à lista **Solicitação de usuário de colaboração do fornecedor** no módulo **Compras** (o módulo Compras não é acessível para usuários externos).

### <a name="provision-a-user"></a>Provisionar um usuário

Antes que você possa solicitar que um novo usuário seja provisionado, ele deverá ser configurado como um contato para uma ou mais contas de fornecedor. Para criar uma solicitação para um novo usuário de colaboração do fornecedor:

1. Na página **Todos os contatos**, clique em **Provisionar o usuário fornecedor**.
2. Insira um endereço de email para o usuário. Esse endereço será usado pelo usuário para entrar no Supply Chain Management. Se o endereço de email pertencer a um domínio registrado como um inquilino com Microsoft Azure, o endereço de email deverá ser uma conta do AAD Azure Active Directory existente para que o processo de provisionamento seja concluído com êxito. Se o endereço de email não pertencer a um domínio registrado com o Microsoft Azure, uma conta do AAD será criada como parte do processo de provisionamento e o novo usuário receberá um email de convite. Os endereços de email de consumidores com domínios como @hotmail.com, @gmail.com ou @comcast.net não poderão ser usados para registrar um usuário.
3. Defina a opção **Acesso à colaboração do fornecedor permitido** como **Sim** para todas as entidades legais às quais o usuário precisa ter acesso.
4. Na seção **Atribuir funções de usuário**, marque a caixa de seleção **Atribuir** para as funções de segurança que o novo usuário deve ter.
5. Clique em **Enviar**.

Quando a solicitação do usuário fornecedor é enviada, o campo **Acesso à colaboração do fornecedor permitido** é definido como **Sim** para a conta de fornecedor selecionada e um fluxo de trabalho da solicitação de usuário é iniciado. Como parte do fluxo de trabalho, um novo usuário é criado e as funções de segurança são atribuídas. Além disso, um serviço Azure B2B é ativado, o que inicia a interação com o portal do Azure e associa uma conta do AAD nova ou existente à conta de usuário do Supply Chain Management. Para obter mais informações, consulte [O que é a colaboração B2B do Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

### <a name="inactivate-a-user"></a>Desativar um usuário

Há duas maneiras de remover o acesso à colaboração do fornecedor para um usuário:

-   Na página **Contatos** para o fornecedor, defina a opção **Acesso à colaboração do fornecedor permitido** como **Não** para o contato. Isso pode ser feito individualmente por entidade legal para a qual a pessoa seja um contato. Esta opção pode ser usada somente por profissionais de compras.
-   Desabilitar toda a conta de usuário, enviando uma solicitação **Desativar o usuário o fornecedor**.

Para solicitar que um usuário seja desativado:

1.  Na página **Todos os contatos**, clique em **Desativar** **usuário fornecedor**.
2.  Escreva um comentário no campo **Justificativa comercial**.
3.  Clique em **Enviar**.

### <a name="modify-security-roles"></a>Modificar funções de segurança

A página **Manter funções de usuário fornecedor** é igual à página **Provisionar o usuário fornecedor**, com a exceção de que a lista de funções de segurança pode ser editada.  

Para solicitar que as funções de segurança sejam modificadas para um usuário:

1.  Na página **Todos os contatos**, clique em **Manter** **funções de usuário fornecedor**.
2.  Escreva um comentário no campo **Justificativa comercial**.
3.  Na seção **Manter funções de usuário**, selecione as funções de segurança que você deseja atribuir, ou desmarque as que deseja remover.
4.  Clique em **Enviar**.




