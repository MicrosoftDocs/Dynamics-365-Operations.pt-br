---
title: Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B
description: Este tópico descreve como adicionar, excluir e editar usuários de parceiros comerciais em sites de comércio eletrônico entre empresas (B2B) no Microsoft Dynamics 365 Commerce e na sede do Commerce.
author: josaw1
ms.date: 04/19/2022
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
ms.openlocfilehash: ef8ae583f18048fc6a36adf38ee7be0fb5b02fcd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686315"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Este tópico descreve como adicionar, excluir e editar usuários de parceiros comerciais em sites de comércio eletrônico entre empresas (B2B) no Microsoft Dynamics 365 Commerce e na sede do Commerce.

> [!NOTE]
> - O tópico [Gerenciar parceiros comerciais B2B usando hierarquias de cliente](partners-customer-hierarchies.md) é um pré-requisito deste documento.
> - Inicialize a entidade de tipos de documento no Commerce Headquarters abrindo o formulário **Tipos de documento** em **Administração da organização \> Gerenciamento de documentos \> Tipos de documento**.

Os sites de comércio eletrônico B2B exigem que as organizações se registrem para que sejam parceiros comerciais. Depois que uma organização envia detalhes de registro para um site de comércio eletrônico B2B, a solicitação de registro passa por um processo de qualificação. Se a organização for qualificada com êxito, ela será integrada como um parceiro comercial.

Depois que uma organização é integrada como um parceiro comercial, o usuário da organização que iniciou a solicitação para se tornar um parceiro comercial é identificado como o usuário administrador e recebe os privilégios para integrar usuários autorizados adicionais do site de comércio eletrônico B2B. Esses usuários autorizados podem fazer pedidos em nome do parceiro comercial.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurar o usuário de administrador para um novo parceiro comercial

Parceiros comerciais potenciais podem iniciar o processo de integração para um site de comércio eletrônico B2B enviando uma solicitação de integração por meio de um link no site B2B. Eles podem usar o formulário personalizável para fornecer os detalhes necessários para integração e inscrição. Após o envio da solicitação, aparecerá uma página de confirmação de envio. Se o envio for aprovado, a empresa para a qual a solicitação foi enviada ser tornará um parceiro de negócios e o solicitante (o usuário que iniciou a solicitação de integração) se tornará o usuário administrador do parceiro de negócios.

Para aprovar uma solicitação de parceiros de negócios na sede do Commerce, siga estas etapas.

1. Acesse **TI de Varejo e Comércio \> Agenda de Distribuição**.
1. Execute o trabalho **P-0001** para receber todas as solicitações de integração de parceiros comerciais na sede do Commerce.
1. Após a execução com êxito do trabalho **P-0001**, acesse **TI de Varejo e Comércio \> Cliente** e execute o trabalho **Sincronizar solicitações de clientes e canais**. Depois que esse trabalho for executado com êxito, as solicitações de integração serão criadas como clientes potenciais do tipo **Cliente potencial B2B** na sede do Commerce. 
1. Vá para **Clientes \> Todos os clientes potenciais** e selecione o registro de cliente potencial do novo parceiro de negócios para abrir a página de detalhes do cliente potencial.
1. Na guia **Geral**, selecione **Converter \> Aprovar/Rejeitar** para aprovar a solicitação de integração. Quando aparecer a mensagem de confirmação, confirme que você deseja continuar com o processo e, depois, aprove a solicitação. A aprovação altera o campo **Status** do registro de cliente potencial para **Aprovado**. Um email será enviado ao endereço de email do solicitante para confirmar que a organização dele foi aprovada como parceiro comercial. Uma hierarquia de cliente também é criada, em que o solicitante é adicionado como um administrador do parceiro de negócios.

    > [!NOTE]
    > No momento, o email de confirmação é enviado imediatamente na aprovação. No entanto, a funcionalidade futura do Commerce permitirá que o administrador dispare os emails manualmente.

1. Acesse **TI de Varejo e Comércio \> Agenda de distribuição** e execute o trabalho **1010 (Clientes)** para enviar novos registros de cliente e de hierarquia do cliente para o banco de dados do canal.

> [!NOTE]
> Para garantir que os novos registros de cliente sejam enviados para o banco de dados de canal, pelo menos um dos catálogos de endereços associados ao cliente deve ser incluído no catálogo de endereços do cliente associado à loja online. Você pode automatizar esse processo configurando o catálogo de endereços no cliente padrão da loja online para que o sistema copie o valor do catálogo de endereços para todos os novos clientes.

Depois que os registros de hierarquia do cliente forem sincronizados com o banco de dados do canal, o solicitante poderá entrar no site de comércio eletrônico B2B usando o endereço de email fornecido ao enviar a solicitação de integração. Os usuários podem usar o fluxo de inscrição para definir a senha da conta. Para obter informações sobre como habilitar o registro do provedor de identidade B2C do Azure Active Directory (Azure AD) a ser vinculado ao registro de cliente B2B criado na aprovação do cliente potencial, consulte [Habilitar vinculação automática](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notificar clientes potenciais B2B quando forem aprovados ou rejeitados

Ao aprovar ou rejeitar uma solicitação de integração de clientes potenciais B2B, uma notificação por email pode ser enviada automaticamente ao cliente potencial.

Para configurar notificações por email na sede do Commerce para eventos do tipo de notificação **Cliente potencial B2B aprovado** ou **Cliente potencial B2B rejeitado**, siga estas etapas.

1. Crie modelos para emails que serão enviados para clientes potenciais quando o tipo de notificação **Cliente potencial B2B aprovado** ou **Cliente potencial B2B rejeitado** for disparado. Para obter informações sobre os espaços reservados com suporte desses tipos de notificação, consulte [Tipos de notificação](../email-templates-transactions.md#notification-types). Para obter informações sobre como criar modelos de email, consulte [Criar um modelo de email](../email-templates-transactions.md#create-an-email-template).
1. Adicione os tipos de notificação **Cliente potencial B2B aprovado** e **Cliente potencial B2B rejeitado** ao seu perfil de notificação por email e, depois, mapeie-os para os modelos de email que você criou. Para obter mais informações sobre perfis de notificação, consulte [Configurar um perfil de notificação por email](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Integrar usuários adicionais do parceiro comercial

O usuário administrador do parceiro comerciais pode integrar usuários de parceiros comerciais adicionais no site de comércio eletrônico B2B, conforme necessário.

Para integrar usuários de parceiros comerciais a um site de comércio eletrônico B2B, siga estas etapas.

1. Entre no site de comércio eletrônico B2B como administrador.
1. Acesse **Minha conta \> Usuários da organização \> Exibir detalhes** e selecione **Adicionar um usuário**.
1. Insira as informações necessárias e selecione **Salvar**. O status do novo usuário é definido como **Pendente**.

Após a execução dos trabalhos **P-0001** e **Sincronizar solicitações de clientes e canais**, um registro de cliente do tipo **Pessoa** será criado para o novo usuário na sede do Commerce. Esse registro de cliente também está associado ao registro de hierarquia de clientes do parceiro comercial relevante. Além disso, um email é enviado ao novo endereço de email do usuário para notificá-lo de que foi adicionado como um usuário da organização parceira comercial e pode agora entrar no site de comércio eletrônico B2B.

Execute o trabalho **1010 (Clientes)** para sincronizar o novo usuário parceiro de negócios com o banco de dados do canal.

Depois que o registro do cliente é sincronizado, o status do usuário no site de comércio eletrônico B2B é definido como **Ativo**, e o novo usuário pode entrar no site de comércio eletrônico B2B usando o endereço de email dele. Os usuários podem usar o fluxo de inscrição para definir a senha da conta. Para obter informações sobre como habilitar o registro do provedor de identidade B2C do Azure AD a ser vinculado ao registro de cliente B2B criado na sede do Commerce, consulte [Habilitar vinculação automática](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Editar detalhes do usuário parceiro comercial

Para editar os detalhes de usuários de parceiros comerciais, siga estas etapas.

1. Entre no site de comércio eletrônico B2B como administrador.
1. Acesse **Minha conta \> Usuários da organização \> Exibir detalhes**, selecione o botão **Editar** (símbolo de lápis), faça as alterações necessárias e selecione **Salvar**. As alterações só são efetivadas após a execução dos trabalhos **P-0001**, **Sincronizar solicitações de clientes e canais** e **1010 (Clientes)**.

## <a name="remove-a-business-partner-user"></a>Remover um usuário parceiro comercial

Conforme necessário, um administrador pode remover os usuários existentes de uma organização de parceiro comercial da lista de usuários que podem acessar o site de comércio eletrônico B2B.
Para remover um usuário parceiro comercial, siga estas etapas.
- Entre no site de comércio eletrônico B2B como administrador.
- Acesse **Minha Conta > Usuários da organização \> Exibir detalhes** e selecione o botão **Remover** (símbolo "X"). Quando uma mensagem de confirmação for exibida, confirme se deseja remover o usuário. A alteração só será efetivada após a execução dos trabalhos **P-0001**, **Sincronizar solicitações de clientes e canais** e **1010 (Clientes)**.

> [!NOTE]
> Quando você remover um usuário da lista de usuários que podem acessar o site de comércio eletrônico B2B, o registro do cliente correspondente será removido do registro da hierarquia de clientes do parceiro comercial. No entanto, o próprio registro do cliente não é excluído da sede do Commerce.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Integrar clientes existentes como parceiros de negócios no site de comércio eletrônico B2B

Os administradores podem integrar parceiros comerciais e usuários diretamente na sede do Commerce. Esse recurso é útil para a integração de parceiros de negócios existentes no site de comércio eletrônico B2B.

Para integrar parceiros comerciais e usuários na sede do Commerce, siga estas etapas.

1. Crie ou selecione um cliente do tipo **Organização** para adicionar como um parceiro de negócios.
1. Crie ou selecione um cliente do tipo **Pessoa** a ser adicionado como administrador ou usuário para o parceiro de negócios. Verifique se os endereços de email principais estão associados aos clientes. Esses endereços de email são usados para entrar no site. 

    > [!NOTE]
    > O sistema deve ser capaz de localizar um registro de cliente exclusivo para usuários que possam entrar no site. Se o sistema encontrar mais de um cliente com o mesmo endereço de email principal na entidade legal, o usuário não poderá entrar no site.

1. Crie uma ID de hierarquia do cliente.
1. No campo **Nome**, insira um nome.
1. No campo **Organização**, insira o cliente da organização do parceiro comercial.
1. Na FastTab **Hierarquia**, selecione **Adicionar**.
1. No campo **Nome**, selecione um cliente do tipo **Pessoa**.
1. Selecione a função **Administrador** do cliente que deve ser designado como o administrador.
1. Repita este processo para adicionar mais clientes à hierarquia.

## <a name="additional-information"></a>Outras informações

- Todos os trabalhos mencionados neste tópico podem ser configurados para serem executados em uma agenda em um formato de lote. A expectativa é de que os parceiros comerciais configurem trabalhos em lotes conforme necessário.
- No momento, somente um registro de usuário/cliente pode ser designado como um usuário administrador, e essa função pode ser alterada somente na sede do Commerce. Não há suporte a recursos de autoatendimento que permitam a parceiros comerciais designar vários administradores ou alterar administradores de sites de comércio eletrônico B2B.
- Embora os limites de gastos possam ser definidos para usuários, a imposição de limites de gastos durante o processo de entrada de ordem ainda não foi implementada.
- Toda a lógica comercial e a validação da experiência de um usuário em um site de comércio eletrônico B2B são baseadas na configuração do registro do cliente que é mapeado para o usuário na sede do Commerce.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Gerenciar parceiros de negócios B2B usando hierarquias do cliente](partners-customer-hierarchies.md)

[Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B](payment-method.md)

[Definir limites de quantidade de produto para sites de comércio eletrônico B2B](quantity-limits.md)

[Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
