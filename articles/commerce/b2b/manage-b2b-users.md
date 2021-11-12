---
title: Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B
description: Este tópico descreve como administradores podem adicionar, editar e excluir usuários de parceiros comerciais em sites de comércio eletrônico entre empresas (B2B).
author: josaw1
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 090dc9af49840e559b4c1ad1500718fde9764aa2
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713684"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Este tópico descreve como administradores podem adicionar, editar e excluir usuários de parceiros comerciais em sites de comércio eletrônico entre empresas (B2B).

Os sites de comércio eletrônico B2B exigem que as organizações se registrem para que sejam parceiros comerciais. Depois que uma organização envia detalhes de registro para um site de comércio eletrônico B2B, ela passa por um processo de qualificação. Se a organização for qualificada com êxito, ela será integrada como um parceiro comercial.

Depois que uma organização é integrada como um parceiro comercial, o usuário da organização que iniciou a solicitação para se tornar um parceiro comercial é identificado como o usuário administrador e recebe os privilégios para integrar usuários autorizados adicionais do site de comércio eletrônico B2B. Esses usuários autorizados podem fazer pedidos em nome do parceiro comercial.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Ativar recursos de comércio eletrônico B2B na sede do Commerce

Os recursos de comércio eletrônico B2B na sede do Commerce permitem que as organizações integrem parceiros comerciais e definam usuários administradores. Esse recurso também permite que os administradores criem e gerenciem usuários e equipes de parceiros comerciais e atribuam funções específicas a eles. Por fim, ele permite que os usuários de parceiros comerciais criem modelos de pedidos e usem ordens existentes para reordenar produtos.

Para ativar recursos de comércio eletrônico B2B na sede do Commerce, siga estas etapas.

1. Acesse **Espaços de trabalho \> Gerenciamento de Recursos**.
1. Na guia **Tudo**, filtre o campo **Módulo** usando o termo **Varejo e comércio**.
1. Localize e selecione o recurso chamado **Habilitar o uso de recursos de comércio eletrônico B2B** e selecione **Habilitar agora**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Criar uma sequência numérica e adicioná-la a parâmetros compartilhados do Commerce

As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores. Para obter mais informações sobre sequências numéricas, consulte [Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Para criar uma sequência numérica e adicioná-la a parâmetros compartilhados do Commerce na sede do Commerce, siga estas etapas.

1. Acesse **Varejo e comércio \> Configuração da sede \> Sequências numéricas \> Sequências numéricas** e crie uma sequência numérica.
1. Acesse **Varejo e comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados do Commerce** e adicione a nova sequência numérica à referência **ID da hierarquia do cliente**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurar o usuário de administrador para um novo parceiro comercial

Parceiros comerciais potenciais podem iniciar o processo de integração para um site de comércio eletrônico B2B enviando uma solicitação de integração por meio de um link no site. Depois que um usuário parceiro comercial em potencial seleciona o link, eles podem fornecer os detalhes necessários para integração e inscrição. Após o envio da solicitação, aparecerá uma página de confirmação de envio. Se o envio for aprovado, o solicitante (ou seja, o usuário que iniciou a solicitação de integração) se tornará o usuário administrador do parceiro comercial.

Para aprovar e configurar um usuário administrador de parceiro comercial na sede do Commerce, siga estas etapas.

1. Acesse **TI de Varejo e Comércio \> Agenda de Distribuição**.
1. Execute o trabalho **P-0001** para receber todas as solicitações de integração de parceiros comerciais na sede do Commerce.
1. Após a execução com êxito do trabalho **P-0001**, acesse **TI de Varejo e Comércio \> Cliente** e execute o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono**. Depois que esse trabalho for executado com êxito, as solicitações de integração serão criadas como registros de clientes potenciais na sede do Commerce. O campo **ID de tipo** desses registros é definido como **Cliente potencial B2B**.
1. Acesse **Clientes \> Todos os clientes potenciais** e abra a página de clientes potenciais.
1. Selecione o registro de cliente potencial do novo parceiro comercial para abrir a página de detalhes do cliente potencial.
1. Na guia **Geral**, selecione **Converter \> Aprovar/Rejeitar** para aprovar ou rejeitar a solicitação de integração. Quando for exibida uma mensagem de confirmação, confirme que você deseja continuar com o processo e aprove a solicitação. Um email será enviado ao endereço de email do solicitante para confirmar que a organização dele foi aprovada como parceiro comercial.

    Depois que você aprovar a solicitação, o campo **Status** do registro de cliente potencial será definido como **Aprovado**. Além disso, dois novos registros de clientes são criados no sistema: um registro de cliente de **Tipo Organização** para a organização de parceiros comerciais e um registro de cliente de **Tipo Pessoa** para o solicitante. Também é criado um registro de hierarquia do cliente para o parceiro comercial. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Acesse **TI de Varejo e Comércio \> Agenda de distribuição** e execute o trabalho **1010** (**Clientes**) para enviar os registros de cliente recém-criado e de hierarquia cliente para o banco de dados do canal.

Depois que a solicitação for aprovada, e os registros de cliente e de hierarquia do cliente forem sincronizados com o banco de dados do canal, o solicitante poderá entrar no site de comércio eletrônico B2B usando o endereço de email fornecido ao enviar a solicitação. Os usuários podem usar o fluxo de inscrição para definir a senha da conta. Para habilitar o registro de provedor de identidade (Azure AD B2C) a ser vinculado ao registro de cliente B2B criado na inscrição ou na entrada, siga as instruções em [Habilitar vinculação automática de registros de identidade a contas de clientes](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notificar clientes potenciais B2B quando forem aprovados ou rejeitados

Ao aprovar ou rejeitar uma solicitação de integração de clientes potenciais B2B, você pode enviar automaticamente uma notificação por email ao cliente potencial. 

Para configurar notificações por email no Commerce Headquarters para eventos do tipo de notificação de cliente potencial B2B aprovado ou rejeitado, siga estas etapas.

1. Crie modelos para emails que serão enviados para clientes potenciais quando o tipo de notificação de cliente potencial B2B aprovado ou rejeitado for disparado.

    Para obter informações sobre os espaços reservados com suporte dos tipos de notificação de cliente potencial B2B aprovado ou rejeitado, consulte [Tipos de notificação](../email-templates-transactions.md#notification-types). Para obter informações sobre como criar modelos de email, consulte [Criar um modelo de email](../email-templates-transactions.md#create-an-email-template). 

1. Adicione os tipos de notificação de cliente potencial B2B aprovado e rejeitado ao seu perfil de notificação por email e mapeie-os para os modelos de email que você criou. Para obter mais informações sobre perfis de notificação, consulte [Configurar um perfil de notificação por email](../email-notification-profiles.md). 

## <a name="onboard-additional-business-partner-users"></a>Integrar usuários adicionais do parceiro comercial

O usuário administrador do parceiro comerciais pode integrar usuários de parceiros comerciais adicionais no site de comércio eletrônico B2B, conforme necessário.

Para integrar usuários de parceiros comerciais a um site de comércio eletrônico B2B, siga estas etapas.

1. Entre no site de comércio eletrônico B2B como administrador.
1. Acesse **Minha conta \> Usuários da organização \> Exibir detalhes** e selecione **Adicionar um usuário**.
1. Insira as informações necessárias e selecione **Salvar**. O status do novo usuário é definido como **Pendente**.

    Após a execução dos trabalhos **P-0001** e **Sincronizar clientes e parceiros comerciais do modo assíncrono**, um registro de cliente de **Tipo Pessoa** para o novo usuário é criado na sede do Commerce. Esse registro de cliente também está associado ao registro de hierarquia de clientes do parceiro comercial relevante. Além disso, um email é enviado ao novo endereço de email do usuário para notificá-lo de que foi adicionado como um usuário da organização parceira comercial e pode agora entrar no site de comércio eletrônico B2B.

1. Execute o trabalho **1010** (**Clientes**) para sincronizar o novo usuário parceiro comercial com o banco de dados do canal.

Depois que o registro do cliente é sincronizado, o status do usuário no site de comércio eletrônico B2B é definido como **Ativo**, e o novo usuário pode entrar no site de comércio eletrônico B2B usando o endereço de email dele. Os usuários podem usar o fluxo de inscrição para definir a senha da conta. Para habilitar o registro de provedor de identidade (Azure AD B2C) a ser vinculado ao registro de cliente B2B criado na inscrição ou na entrada, siga as instruções em [Habilitar vinculação automática de registros de identidade a contas de clientes](../identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Editar detalhes do usuário parceiro comercial

Para editar os detalhes de usuários de parceiros comerciais, siga estas etapas.

1. Entre no site de comércio eletrônico B2B como administrador.
1. Acesse **Minha conta \> Usuários da organização \> Exibir detalhes**, selecione o botão **Editar** (símbolo de lápis), faça as alterações necessárias e selecione **Salvar**. As alterações só são efetivadas após a execução dos trabalhos **P-0001**, **Sincronizar clientes e parceiros comerciais do modo assíncrono** e **1010** (**Clientes**).

## <a name="remove-a-business-partner-user"></a>Remover um usuário parceiro comercial

Conforme necessário, um administrador pode remover os usuários existentes de uma organização de parceiro comercial da lista de usuários que podem acessar o site de comércio eletrônico B2B.

Para remover um usuário parceiro comercial, siga estas etapas.

1. Entre no site de comércio eletrônico B2B como administrador.
1. Acesse **Minha Conta \> Usuários da organização \> Exibir detalhes** e selecione o botão **Remover** (símbolo "X"). Quando uma mensagem de confirmação for exibida, confirme se deseja remover o usuário. A alteração só será efetivada após a execução dos trabalhos **P-0001**, **Sincronizar clientes e parceiros comerciais do modo assíncrono** e **1010** (**Clientes**).

> [!NOTE]
> Quando você remover um usuário da lista de usuários que podem acessar o site de comércio eletrônico B2B, o registro do cliente correspondente será removido do registro da hierarquia de clientes do parceiro comercial. No entanto, o próprio registro do cliente não é excluído da sede do Commerce.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Integrar parceiro comercial e usuários na sede do Commerce

Os administradores podem integrar parceiros comerciais e usuários diretamente na sede do Commerce.

Para integrar parceiros comerciais e usuários na sede do Commerce, siga estas etapas.

1. Crie um registro de cliente de **Tipo Organização** para a organização do parceiro comercial.
1. Crie registros de clientes do **Tipo Pessoa** para usuários de parceiros comerciais. Verifique se um endereço de email principal foi especificado para cada cliente.
1. Para cada registro de cliente de **Tipo Pessoa** que deva ser designado como um usuário administrador da organização do parceiro comercial, na Guia Rápida **Retail**, defina a opção **Administrador de B2B** como **Sim**.
1. Crie uma ID de hierarquia do cliente. No campo **Nome**, insira um nome.
1. No campo **Organização**, insira o cliente da organização do parceiro comercial.
1. Selecione **Adicionar** e, depois, selecione um cliente no campo **Nome**.
1. Repita este processo para adicionar clientes adicionais à hierarquia.

## <a name="additional-information"></a>Informações adicionais da Nf-e

- Todos os trabalhos mencionados neste tópico podem ser configurados para serem executados em uma agenda em um formato de lote. A expectativa é de que os parceiros comerciais configurem trabalhos em lotes conforme necessário.
- No momento, somente um registro de usuário/cliente pode ser designado como um usuário administrador, e essa função pode ser alterada somente na sede do Commerce. Não há suporte a recursos de autoatendimento que permitam a parceiros comerciais designar vários administradores ou alterar administradores de sites de comércio eletrônico B2B.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Embora os limites de gastos possam ser definidos para usuários, a imposição de limites de gastos durante o processo de entrada de ordem ainda não foi implementada.
- Toda a lógica comercial e a validação da experiência de um usuário em um site de comércio eletrônico B2B são baseadas na configuração do registro do cliente que é mapeado para o usuário na sede do Commerce.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Criar hierarquias de modelagem de organização para organizações B2B](org-model.md)

[Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B](payment-method.md)

[Definir limites de quantidade de produto para sites de comércio eletrônico B2B](quantity-limits.md)

[Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
