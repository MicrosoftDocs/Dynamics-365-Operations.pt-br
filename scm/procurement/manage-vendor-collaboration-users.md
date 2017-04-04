---
title: "Gerenciar usuários de colaboração do fornecedor"
description: "Este tópico descreve como você pode solicitar o provisionamento de novos usuários de colaboração do fornecedor e como adicionar novos contatos de colaboração do fornecedor."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 380f1bcdf7109dc12fd898199033eac7710d863c
ms.lasthandoff: 03/31/2017


---

# <a name="manage-vendor-collaboration-users"></a>Gerenciar usuários de colaboração do fornecedor

Este tópico descreve como você pode solicitar o provisionamento de novos usuários de colaboração do fornecedor e como adicionar novos contatos de colaboração do fornecedor. 

A interface de colaboração do fornecedor no Microsoft Dynamics 365 for Operations expõe informações sobre ordens de compra, faturas e estoque de consignação para fornecedores externos. Você pode criar novos contatos de colaboração de fornecedor e solicitar que os novos usuários sejam provisionados se você estiver trabalhando com um fornecedor externo com a função de segurança **Administrador do fornecedor (externo)** ou permissões semelhantes. Você também pode executar essas tarefas se estiver trabalhando como um profissional de compras. Neste tópico, esta função se refere um profissional de compras que esteja trabalhando na empresa responsável pela instância do Dynamics 365 for Operations. Para obter mais informações sobre como usar a colaboração de fornecedor se você for um fornecedor externo, consulte [] fornecedor com clientes (vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para obter mais informações sobre como usar a colaboração de fornecedor se você for um profissional de compras, consulte [colaboração de fornecedor com fornecedores externos (vendor-collaboration-work-external-vendors.md]).

## <a name="add-new-vendor-collaboration-contacts"></a>Adicionar novos contatos de colaboração do fornecedor
Se você deseja que pessoa tenha acesso à colaboração do fornecedor, primeiramente é preciso adicioná-la como um contato de colaboração do fornecedor. Você também pode querer adicionar contatos para funcionários da sua empresa que não usarão a colaboração do fornecedor. Por exemplo, eles podem ser o ponto de contato para outros tipos de informações de compras. Novos contatos adicionados ** todos os contatos ** na página, que é acessado ** colaboração fornecedor ** &gt; ** de contatos ** menu. Para adicionar um novo contato:

1.  Clique em **Novo**.
2.  Insira os detalhes da pessoa de contato.
3.  Indique qual entidade legal ela está representando em sua empresa e com qual entidade legal ela trabalhará na empresa com a qual ela colaborará. Você faz isso selecionando ** a entidade legal na empresa/** ** entidade legal na empresa do cliente ** pares.
4.  Clique em **Criar**.

Se quiser excluir um contato, você poderá excluir somente aqueles que criou.

## <a name="vendor-collaboration-user-requests"></a>Solicitações de usuário de colaboração do fornecedor
Solicitações de usuário de colaboração do fornecedor podem ser feitas por um profissional de compras ou por um administrador de fornecedores externos.

-   Se você for um fornecedor externo, enviar solicitações ** todos os contatos ** de página em ** colaboração fornecedor ** de módulo.
-   Se você for um profissional de compras, envie solicitações da página **Exibir contatos**. Para fazer isso, no registro de fornecedor, ** de instalação ** na seção no painel de ações, contatos ** ** ** &gt; selecione contatos ** de exibição.

Você pode fazer uma solicitação para provisionar um usuário, desativar um usuário ou modificar funções de segurança. Se você for um administrador de fornecedores externos, você deve estar registrado como uma pessoa de contato para contas de fornecedor para as quais deseja fazer solicitações de usuário e deverá ter acesso à interface de colaboração do fornecedor para essas contas de fornecedor.  

Quando uma solicitação é enviada, ela será adicionada a lista **Solicitações de usuário de colaboração do fornecedor** no módulo **Colaboração do fornecedor** e à lista **Solicitação de usuário de colaboração do fornecedor** no módulo **Compras** (o módulo Compras não é acessível para usuários externos).

### <a name="provision-a-user"></a>Provisionar um usuário

Antes que você possa solicitar que um novo usuário seja provisionado, ele deverá ser configurado como um contato para uma ou mais contas de fornecedor. Para criar uma solicitação para um novo usuário de colaboração do fornecedor:

1.  ** Todos os contatos ** na página, clique ** usuário fornecedor de provisão **.
2.  Insira um endereço de email para o usuário. Esse endereço será usado pelo usuário para fazer logon no Dynamics 365 for Operations. Se o endereço de email pertencer a um domínio registrado como um inquilino com Microsoft Azure, o endereço de email deverá ser uma conta do ADD (Azure Active Directory) existente para que o processo de provisionamento seja concluído com êxito. Se o endereço de email não pertencer a um domínio registrado com o Microsoft Azure, uma conta do ADD será criada como parte do processo de provisionamento e o novo usuário receberá um email de convite. Os endereços de email de consumo com domínios como @hotmail.com, @gmail.com, @comcast.net e não podem ser usados para registrar uma dynamics 365 para o usuário das operações.
3.  Defina a opção **Acesso à colaboração do fornecedor permitido** como **Sim** para todas as entidades legais às quais o usuário precisa ter acesso.
4.  Na seção **Atribuir funções de usuário**, marque a caixa de seleção **Atribuir** para as funções de segurança que o novo usuário deve ter.
5.  Clique em **Enviar**.

Quando a solicitação do fornecedor for enviada, ** acesso de colaboração fornecedor permitido ** o campo está definido como Sim ** ** para a conta de fornecedor selecionada e o fluxo de trabalho do usuário for iniciada. Como parte do fluxo de trabalho, um novo usuário será criado Dynamics 365 for Operations e as funções de segurança serão atribuídas. Além disso, um serviço Azure B2B é ativado, o que inicia a interação com o portal do Azure e associa uma conta do AAD nova ou existente à conta de usuário do Dynamics 365 for Operations.

### <a name="inactivate-a-user"></a>Desativar um usuário

Há duas maneiras de remover o acesso à colaboração do fornecedor para um usuário:

-   Na página **Contatos** para o fornecedor, defina a opção **Acesso à colaboração do fornecedor permitido** como **Não** para o contato. Isso pode ser feito individualmente por entidade legal para a qual a pessoa seja um contato. Esta opção pode ser usada somente por profissionais de compras.
-   Desabilitar toda a conta de usuário, enviando uma solicitação **Desativar o usuário o fornecedor**.

Para solicitar que um usuário está desativado:

1.  ** Todos os contatos ** na página, clique ** desativar ** ** usuário ** fornecedor.
2.  Escreva um comentário no campo **Justificativa comercial**.
3.  Clique em **Enviar**.

### <a name="modify-security-roles"></a>Modificar funções de segurança

** Manter funções de usuário fornecedor ** a página é idêntico ** usuário fornecedor de provisão ** o página exceto que a lista de funções de segurança podem ser editadas.  

Para solicitar que funções de segurança serão alteradas para um usuário:

1.  ** Todos os contatos ** na página, clique ** manter ** ** funções de usuário ** fornecedor.
2.  Escreva um comentário no campo **Justificativa comercial**.
3.  Na seção **Manter funções de usuário**, selecione as funções de segurança que você deseja atribuir, ou desmarque as que deseja remover.
4.  Click **Submit**.



