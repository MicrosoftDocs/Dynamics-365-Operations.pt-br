---
title: Provisionar um ambiente de visualização do Commerce
description: Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b77d2cbbc100aeae5dcd53ddbe69ff2e4435da13
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934739"
---
# <a name="provision-a-commerce-preview-environment"></a>Provisionar um ambiente de visualização do Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.

Antes de começar, recomendamos que você pelo menos olhe a documentação de todo este tópico para ter uma ideia do que o processo implica e do que este tópico contém.

> [!NOTE]
> Se ainda não tiver acesso à visualização do Dynamics 365 Commerce, você pode solicitar o acesso de visualização do [site do Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Visão geral

Para provisionar com êxito o seu ambiente de visualização do Commerce, você deve criar um projeto com um nome e um tipo de produto específicos. O ambiente e o Retail Cloud Scale Unit (RCSU) também têm alguns parâmetros específicos que você deve usar ao provisionar o comércio eletrônico posteriormente. As instruções neste tópico descrevem todas as etapas necessárias que devem ser concluídas e os parâmetros que devem ser usados.

Após o provisionamento bem-sucedido de seu ambiente de visualização do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo. Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar. Você sempre poderá concluir as etapas opcionais posteriormente.

Para obter informações sobre como configurar seu ambiente de visualização do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md). Para obter informações sobre como configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).

Se tiver dúvidas sobre as etapas de provisionamento ou detectar problemas, informe à Microsoft em [Visualização do Microsoft Dynamics 365 Commerce - grupo do Yammer](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem estar disponíveis para que você possa provisionar o seu ambiente de visualização do Commerce:

- Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.
- Você foi aceito no programa de Visualização do Dynamics 365 Commerce.
- Você tem as permissões necessárias para criar um projeto para **Pré-vendas de clientes potenciais** ou **Migrar, criar soluções e conhecer**
- Você é membro da função **Gerente de ambiente** ou **Proprietário do projeto** no projeto no qual você irá provisionar o ambiente.
- Você tem acesso de administrador à sua assinatura do Microsoft Azure ou entra em contato com um administrador de assinatura que pode concluir as duas etapas que exigem permissões de administrador em seu nome.
- Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível. (Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).

### <a name="find-your-azure-ad-tenant-id"></a>Como encontrar sua ID do locatário de Azure AD

Sua ID de locatário do Azure AD é um identificador exclusivo globalmente (GUID) que é semelhante a este exemplo: **72f988bf-86f1-41af-91ab-2d7cd011db47**.

#### <a name="find-your-azure-ad-tenant-id-by-using-the-azure-portal"></a>Localizar sua ID de locatário do Azure AD usando o portal do Azure

1. Entre no [portal do Azure](https://portal.azure.com/).
1. Verifique se o diretório correto foi selecionado.
1. No menu à esquerda, selecione **Azure Active Directory**.
1. Em **Gerenciar**, selecione **Propriedades**. Sua ID de locatário do Azure AD aparece em **ID do Diretório**.

#### <a name="find-your-azure-ad-tenant-id-by-using-openid-connect-metadata"></a>Encontre sua ID de locatário do Azure AD usando os metadados de Conexão de OpenID

Crie uma URL de OpenID substituindo **\{YOUR\_DOMAIN\}** com seu domínio, como `microsoft.com`. Por exemplo, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` ficará `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.

1. Vá para o URL do OpenID que contém o seu domínio.

    Você pode localizar sua ID de locatário do Azure AD em vários valores da propriedade.

1. Localize **authorization\_endpoint** e extraia a GUID que aparece imediatamente após `login.microsoftonline.com/`.

### <a name="find-your-azure-ad-security-group-id"></a>Localizar a ID do grupo de segurança do Azure AD

A ID do grupo de segurança do Azure AD é um GUID semelhante a este exemplo: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.

Este procedimento pressupõe que você seja membro do grupo para o qual você está tentando encontrar a ID.

1. Abra o [Gerenciador de Gráficos](https://developer.microsoft.com/graph/graph-explorer#).
1. Selecione **Entrar com a conta da Microsoft** e entre usando suas credenciais.
1. À esquerda, selecione **mostrar mais exemplos.**
1. No painel à direita, habilite **Grupos**.
1. Feche o painel direito.
1. Selecione **todos os grupos aos quais eu pertenço**.
1. No campo **Visualização de Resposta**, localize seu grupo. A ID do grupo de segurança aparece na propriedade **id**.

## <a name="provision-your-commerce-preview-environment"></a>Provisionar seu ambiente de visualização do Commerce

Estes procedimentos explicam como provisionar um ambiente de visualização do Commerce. Depois de concluí-los com êxito, o ambiente de visualização do Commerce estará pronto para a configuração. Todas as atividades descritas aqui ocorrem no portal do LCS.

> [!IMPORTANT]
> O acesso de visualização está vinculado à conta e à organização do LCS que você especificou no aplicativo de visualização. Você deve usar a mesma conta para provisionar o ambiente de visualização do Commerce. Se for necessário usar uma conta ou um locatário diferentes da LCS para o ambiente de visualização do Commerce, você deverá fornecer esses detalhes à Microsoft. Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support) posteriormente neste tópico.

### <a name="grant-access-to-e-commerce-applications"></a>Conceder acesso aos aplicativos de comércio eletrônico

> [!IMPORTANT]
> A pessoa que faz logon deve ser um administrador de locatário do Azure AD que tem a ID do locatário do Azure AD. Se essa etapa não for concluída com êxito, as etapas de provisionamento restantes falharão.

Para autorizar os aplicativos de comércio eletrônico a acessarem sua assinatura do Azure, siga estas etapas.

1. Monte uma URL no seguinte formato:

    `https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345`

1. Copie e cole a URL no seu navegador ou editor de texto e substitua **\{AAD\_TENANT\_ID\}** por sua ID de locatário do Azure AD. Em seguida, abra a URL.
1. Na caixa de diálogo de logon do Azure AD, faça logon e confirme se você deseja conceder acesso ao **Dynamics 365 Commerce (Versão prévia)** à sua assinatura. Você será redirecionado a uma página que indica se a operação foi bem-sucedida.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Confirme se os recursos de visualização estão disponíveis e habilitados no LCS

Para confirmar se os recursos de visualização estão disponíveis e habilitados no LCS, siga estas etapas.

1. Entre no [portal do LCS](https://lcs.dynamics.com) usando a mesma conta da LCS que você usou para solicitar acesso à visualização.
1. Na página inicial do LCS, role para a direita e selecione o bloco **Gerenciamento de recursos de visualização**.

    ![Bloco de gerenciamento de visualização](./media/preview1.png)

1. Role para baixo até **Recursos de visualização privada** e confirme se os seguintes recursos estão disponíveis e ativados:

    - Avaliação de Comércio eletrônico
    - Ambientes do Programa de Visualização do Comércio

    ![Recursos de visualização privada](./media/preview2.png)

1. Se esses recursos não aparecerem na lista, contate a Microsoft e forneça seu endereço de email de trabalho, sua conta LCS e os detalhes do locatário. Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support).

### <a name="create-a-new-project"></a>Criar um novo projeto

Para criar um novo projeto no LCS, siga estas etapas.

1. Na home page do LCS, selecione o sinal de mais (**+**) para criar um projeto.
1. No painel à direita, siga uma destas etapas:

    - Se você for um parceiro, selecione **Migrar, criar soluções e conhecer**.
    - Se for um cliente, selecione **Pré-vendas de clientes potenciais**.

1. Inserir um nome, descrição e setor.
1. No campo **Nome do produto**, selecione **Dynamics 365 Retail**.
1. No campo **Versão do produto**, selecione **Dynamics 365 Retail**.
1. No campo **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.
1. Opcional: você pode importar funções e usuários de um projeto existente.
1. Selecione **Criar**. A exibição do projeto é exibida.

### <a name="add-the-azure-connector"></a>Adicione o Conector do Azure

Para adicionar o Conector do Azure ao seu projeto LCS, siga estas etapas.

1. Siga uma destas etapas:

    - Se você for um parceiro, selecione o bloco **Configurações do projeto** na extrema direita.
    - Se for um cliente, selecione **Configurações do projeto** no menu superior.

1. Selecione **Conectores do Azure**.
1. Selecione **Adicionar** para adicionar o Conector do Azure.
1. Insira um nome.
1. Digite sua ID da Assinatura do Azure.
1. Ativa a opção **Configurar para usar o gerente de recursos do Azure (ARM)**.
1. Verifique se o valor **Domínio (ou ID) de Locatário do AAD de assinatura do Azure** está correto. Consulte seu administrador de assinatura do Azure, se necessário.
1. Selecione **Avançar**.
1. Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura. Consulte seu administrador de assinatura do Azure, se necessário.

    1. Entre no [portal do Azure](https://portal.azure.com/).
    1. Verifique se o diretório correto está selecionado e, no menu à esquerda, selecione **Assinaturas**.
    1. Localize a assinatura correta da lista e selecione-a. Use a funcionalidade de pesquisa, conforme necessário.
    1. No menu, selecione **Controle de acesso (IAM)**.
    1. À direita, em **Adicionar uma atribuição da função**, selecione **Adicionar**. O painel **Adicionar atribuição da função** é aberto.
    1. No campo **Função**, selecione **Colaborador**.
    1. No campo **Atribuir acesso a**, mantenha o valor padrão, **usuário, grupo ou entidade de serviço do Azure AD**.
    1. Em **Selecionar**, insira **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Selecione **Serviços de Implantação do Dynamics \[ativado por wsfed\]** na lista.
    1. Selecione **Salvar**.

1. Selecione **Avançar**.
1. Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura. Consulte seu administrador de assinatura do Azure, se necessário.
1. Selecione **Avançar**.
1. No campo **região do Azure**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.
1. Selecione **Conectar**. Seu Conector do Azure deverá aparecer na lista.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importar a Extensão da Demonstração da Versão Prévia do Commerce

Para importar a extensão da demonstração da versão prévia do Commerce para seu projeto, siga estas etapas.

1. Abra a home page do seu projeto selecionando o nome do projeto na parte superior.
1. Siga uma destas etapas:

    - Se você for um parceiro, selecione o bloco **Biblioteca de ativos** na extrema direita.
    - Se for um cliente, selecione **Biblioteca de ativos** no menu superior.

1. Na lista à esquerda, selecione **Pacote de software implantável**.
1. Selecione **Importar**.
1. Em **Biblioteca de ativos compartilhados**, selecione **Extensão da Demonstração da Versão Prévia do Commerce** na lista de ativos.
1. Escolha **Separar**. Você retornará à biblioteca de Ativos e deverá ver a extensão na lista.

A ilustração a seguir mostra as ações que devem ser executadas na página **Biblioteca de ativos** do LCS.

![Importando a Extensão Base da Demonstração da Versão Prévia do Commerce](./media/import.png)

### <a name="deploy-the-environment"></a>Implantar o ambiente

Para implantar o ambiente, siga estas etapas.

> [!NOTE]
> Talvez não seja necessário concluir as etapas 6, 7 e/ou 8, porque as páginas que têm uma única opção são ignoradas. Quando estiver na exibição de **Parâmetros do ambiente**, confirme se o texto **Dynamics 365 Commerce (Versão prévia) Demonstração (10.0.6 com atualização de plataforma 30**) aparece diretamente acima do campo **Nome do ambiente**. Consulte a ilustração que aparece após a etapa 8.

1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione **Adicionar** para adicionar um ambiente.
1. No campo **Versão do aplicativo**, selecione **10.0.6**.
1. No campo **Versão da plataforma**, selecione **Atualização da Plataforma 30**.

    ![Selecionando as versões do aplicativo e da plataforma](./media/project1.png)

1. Selecione **Avançar**.
1. Selecione **Demonstração** como a topologia do ambiente.

    ![Selecionar a topologia de ambiente 1](./media/project2.png)

1. Selecione **Dynamics 365 Commerce (Versão prévia) - Demonstrativo** como a topologia do ambiente. Se você configurou um único Conector do Azure anteriormente, isso será usado para este ambiente. Se você configurou vários Conectores do Azure, é possível selecionar qual conector usar: **Leste dos EUA**, **Leste dos EUA 2,** **Oeste dos EUA**, ou **Oeste dos EUA 2**. (Para obter o melhor desempenho de ponta a ponta, recomendamos que você selecione **Oeste dos EUA 2**.)

    ![Selecionando a topologia de ambiente 2](./media/project3.png)

1. Na página **Implantar ambiente**, insira um nome de ambiente. Deixe as configurações avançadas como estão.

    ![Implantar página do ambiente](./media/project4.png)

1. Ajuste o tamanho da VM, conforme necessário. (Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)
1. Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.
1. Selecione **Avançar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**. Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.

    Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado. Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos. Portanto, verifique novamente depois de aproximadamente seis a nove horas.

1. Antes de continuar, verifique se o status de ambiente está **Implantado**.

### <a name="initialize-rcsu"></a>Inicialize o RCSU

Para inicializar sua RCSU, siga estas etapas.

1. Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.
1. Nas visualização do ambiente à direita, selecione **Detalhes completos**. A visualização de detalhes do ambiente é exibida.
1. Em **Recursos do ambiente**, selecione **Gerenciar**.
1. Na guia **Varejo**, selecione **Inicializar**. A visualização dos parâmetros de inicialização do RCSU será exibida.
1. No campo **Região**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.
1. No campo **Versão**, selecione **Especificar uma versão** na lista e, em seguida, especifique **9.16.19262.5** no campo que é exibido. Certifique-se de especificar a versão exata indicada aqui. Caso contrário, será necessário atualizar a RCSU para a versão correta posteriormente.
1. Ative a opção **Aplicar extensão**.
1. Na lista de extensões, selecione **Extensão da Demonstração da Versão Prévia do Commerce**.
1. Selecione **Inicializar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**. Você retornará à visualização **Gerenciamento de varejo** com a guia **Varejo** selecionada. Sua RCSU foi enfileirada para provisionamento.
1. Antes de continuar, verifique se o status de RCSU é **Êxito**. A inicialização leva cerca de duas a cinco horas.

### <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico

Para inicializar o comércio eletrônico, siga estas etapas.

1. Na guia **Comércio eletrônico (Versão prévia)**, revise o consentimento da visualização e, em seguida, selecione **Configurar**.
1. No campo **Nome do locatário de comércio eletrônico**, informe um nome. No entanto, observe que este nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.
1. No campo **Nome da Retail cloud scale unit**, selecione o RCSU na lista. (A lista deve ter apenas uma opção).

    O **Geografia de comércio eletrônico** é definido automaticamente, e o valor não pode ser alterado.

1. Selecione **Avançar** para continuar.
1. No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.
1.  No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você deseja usar. Selecione o ícone de lupa para exibir os resultados da pesquisa. Selecione um grupo de segurança na lista.
2.  No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você deseja usar. Selecione o ícone de lupa para exibir os resultados da pesquisa. Selecione um grupo de segurança na lista.
1. Deixe a opção **Habilitar classificações e examinar o serviço** ativada.
1. Se você já tiver concluído a etapa de consentimento do Microsoft Azure Active Directory (Azure AD), conforme descrito na seção "Conceder acesso a aplicativos de comércio eletrônico", marque a caixa de seleção para confirmar seu consentimento. Se ainda não tiver concluído essa etapa, você precisará fazer isso antes de continuar com a inicialização. Selecione o link no texto ao lado da caixa de seleção para abrir a caixa de diálogo de consentimento e concluir a etapa.
1. Selecione **Inicializar**. Você retornará à visualização **Gerenciamento de varejo** na qual a guia **Comércio eletrônico (Versão prévia)** está ativada. A inicialização de Comércio eletrônico começou.
1. Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **Inicialização com êxito**.
1. Em **Links** no canto inferior direito, anote as URLs dos seguintes links:

    * **Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.
    * **Ferramenta de gerenciamento de site de comércio eletrônico** – o link para a ferramenta de gerenciamento de site.

## <a name="commerce-preview-environment-support"></a>Suporte ao ambiente de visualização do Commerce

Se você tiver problemas ao concluir as etapas de provisionamento, visite [Visualização do Microsoft Dynamics 365 Commerce - grupo Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) para obter ajuda.

Se tiver problemas ao tentar acessar o grupo Yammer, poderá contatar a Microsoft por email em <Dynamics365Commerce@microsoft.com>. Esse endereço de email não está ativamente monitorado. Portanto, espere um atraso na resposta.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de provisionamento e configuração de seu ambiente de visualização do Commerce, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de visualização do Commerce](cpe-overview.md)

[Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md)

[Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md)

[Perguntas frequentes do ambiente de visualização do Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Recursos de ajuda do Dynamics 365 Retail](../retail/index.md)
