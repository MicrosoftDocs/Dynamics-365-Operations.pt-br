---
title: Configurar vários locatários B2C em um ambiente do Commerce
description: Este tópico descreve quando e como configurar os locatários business-to-consumer (B2C) do Microsoft Azure Active Directory (Azure AD) por canal para autenticação do usuário em um ambiente dedicado do Dynamics 365 Commerce.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0ad2a86fbc17f107a065330a56da6cdcca69e172
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352557"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Configurar vários locatários B2C em um ambiente do Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve quando e como configurar os locatários business-to-consumer (B2C) do Microsoft Azure Active Directory (Azure AD) por canal para autenticação do usuário em um ambiente dedicado do Dynamics 365 Commerce.

O Dynamics 365 Commerce usa o serviço de identidade de nuvem B2C do Azure AD para oferecer suporte a credenciais do usuário e fluxos de autenticação. Os usuários podem usar os fluxos de autenticação para se inscrever, entrar e redefinir sua senha. O B2C do Azure AD armazena informações confidenciais de autenticação do usuário, como o nome de usuário e a senha. O registro do usuário é exclusivo para cada locatário B2C e usa credenciais de nome de usuário (endereço de email) ou credenciais de provedor de identidade social.

Na maioria dos casos, um único locatário B2C do Azure AD é usado em um ambiente do Commerce. Os clientes do Commerce podem criar e publicar vários sites no mesmo ambiente do Commerce, e as mesmas credenciais do cliente serão usadas nesses sites. No entanto, se os sites no ambiente devem ser tratados como marcas diferentes e parecerem aos usuários como empresas separadas, um locatário B2C poderá ser configurado para o canal usado para a separação site/marca.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Considerações quando vários locatários B2C são configurados por canal

Frequentemente, quando cada canal ou site está sendo tratado como um negócio separado, a melhor opção com relação aos fluxos de autenticação de usuário no Commerce é usar entidades legais separadas. Entretanto, se você deseja manter cada canal/site no mesmo ambiente e entidade legal, mas deseja ter autenticação de usuário separada para cada site, é importante considerar os seguintes pontos antes de continuar:

- Os usuários terão suas próprias credenciais distintas para cada canal/site.

    A mesma pessoa pode ter duas contas separadas por canal/site, porque cada conta será uma entrada exclusiva para um locatário B2C separado.

- No ambiente do Microsoft Dynamics, registros de clientes separados serão retornados para pesquisas de registros globais.

    Se um usuário usar o mesmo endereço de email nos canais/sites, as pesquisas globais de clientes retornarão resultados para cada canal/site. (Um indicador de canal será exibido.)

- O catálogo de endereços pode ser usado para ajudar a agrupar usuários, para que possam ser rastreados por canal.
- O número de registros de clientes por canal pode aumentar e esse aumento pode afetar o desempenho das pesquisas globais de clientes.
- Os locatários B2C devem ser cuidadosamente mapeados para um canal, para ajudar a evitar situações em que os clientes se inscrevem em um locatário incorreto. Caso contrário, podem ocorrer problemas de confusão ou rastreamento.

A ilustração a seguir mostra vários locatários B2C em um ambiente do Commerce.

![Vários locatários B2C em um ambiente do Commerce.](media/MultiB2C_In_Environment.png)

Se você decidir que sua empresa requer locatários B2C distintos por canal no mesmo ambiente do Commerce, execute os procedimentos nas seções a seguir para solicitar esse recurso.

## <a name="configure-b2c-tenants-in-your-environment"></a>Configurar locatários B2C no ambiente

Para configurar os locatários B2C no ambiente, execute os procedimentos relevantes nesta seção.

### <a name="add-an-azure-ad-b2c-tenant"></a>Adicionar um locatário B2C do Azure AD

Para adicionar um locatário B2C do Azure AD ao ambiente, siga as etapas a seguir.

1. Entre no assistente para criação de sites do Commerce do ambiente como administrador do sistema. Para configurar os locatários B2C do Azure AD, você deve ser um administrador do sistema para o ambiente do Commerce.
1. No painel de navegação esquerdo, selecione **Configurações de Locatário** para expandi-lo.
1. Selecione **Configurações do B2C** e, em seguida, selecione **Gerenciar**.
1. Selecione **Adicionar Aplicativo B2C** e insira as seguintes informações:

    - **Nome do Aplicativo**: insira o nome que deve ser usado para o aplicativo no contexto de gerenciamento no Commerce. Recomendamos que você use o nome do aplicativo que você escolheu ao configurar o aplicativo B2C do Azure AD no portal do Azure. Dessa forma, você pode ajudar a reduzir a confusão ao gerenciar locatários B2C no Commerce.
    - **Nome do locatário**: digite o nome do locatário B2C como aparece no portal do Azure.
    - **ID da Política de Esquecer Senha**: digite a ID da política (o nome da política no portal do Azure).
    - **ID da Política de Inscrição e Logon**: digite a ID da política (o nome da política no portal do Azure).
    - **GUID do Cliente**: digite a ID do locatário B2C do Azure AD como ela aparece no portal do Azure (não a ID do aplicativo do locatário B2C).
    - **Editar ID da Política de Perfil**: digite a ID da política (o nome da política no portal do Azure).

1. Quando terminar de inserir essas informações, selecione **OK** para salvar suas alterações. Seu novo locatário B2C do Azure AD agora deve aparecer na lista em **Gerenciar Aplicativos B2C**.

> [!NOTE]
> Você deve deixar campos como **Escopo**, **ID da Política Não Interativa**, **ID do Cliente Não Interativa**, **Domínio Personalizado de Logon** e **ID da Política de Inscrição** em branco, a menos que você seja orientado pela equipe do Dynamics 365 Commerce a defini-los.


### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Gerenciar ou excluir um locatário B2C do Azure AD

1. Entre no assistente para criação de sites do Commerce do ambiente como administrador do sistema. Para configurar os locatários B2C do Azure AD, você deve ser um administrador do sistema para o ambiente do Commerce.
1. No painel de navegação esquerdo, selecione **Configurações de Locatário** para expandi-lo.
1. Selecione **Configurações do B2C** e, em seguida, selecione **Gerenciar**.
1. Para editar um locatário B2C, selecione o símbolo do lápis ao lado dele. Para excluir um locatário B2C, selecione o símbolo da lata de lixo ao lado dele.
1. Selecione **Salvar** e selecione **Publicar** para ativar suas alterações.

> [!WARNING]
> Quando um locatário B2C é configurado para um site ativo/publicado, os usuários podem se inscrever usando contas presentes no locatário. Se você excluir um locatário configurado no menu **Configurações do Locatário \> Locatário B2C**, removerá a associação desse locatário B2C dos sites associados a qualquer canal do locatário. Nesse caso, talvez seus usuários não consigam mais acessar suas contas. Portanto, tenha muito cuidado ao excluir um locatário configurado.
>
> Quando um locatário configurado é excluído, os registros e o locatário B2C continuarão sendo mantidos, mas a configuração do sistema do Commerce desse locatário será alterada ou removida. Os usuários que tentarem se inscrever ou entrar no site criarão um registro de conta no locatário B2C padrão ou recém-associado que está configurado para o canal do site.

## <a name="configure-your-channel-with-a-b2c-tenant"></a>Configurar seu canal com um locatário B2C

1. Entre no assistente para criação de sites do Commerce do ambiente como administrador do sistema. Para configurar os locatários B2C do Azure AD, você deve ser um administrador do sistema para o ambiente do Commerce.
1. No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.
1. Selecione **Canais** e, em seguida, selecione o canal a ser configurado.
1. No painel de propriedades à direita, no campo **Selecionar Aplicativo B2C**, selecione o locatário B2C do Azure AD configurado para usar nesse canal.
1. Na barra de comandos, selecione **Salvar e publicar** para confirmar a configuração nova ou atualizada.

> [!WARNING]
> Se você alterar o aplicativo B2C atribuído ao canal, removerá as referências atuais que foram estabelecidas para todos os usuários que já se inscreveram no ambiente. Nesse caso, quaisquer credenciais associadas ao aplicativo B2C atribuído no momento não estarão disponíveis para os usuários. Portanto, altere a configuração B2C do Azure AD do canal apenas se você estiver configurando o canal pela primeira vez e se nenhum usuário tiver conseguido se inscrever. Caso contrário, os usuários talvez precisem se inscrever novamente para estabelecer um registro no novo locatário B2C do Azure AD.
## <a name="additional-resources"></a>Recursos adicionais

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
