---
title: Provisionar um ambiente de visualização do Dynamics 365 Commerce
description: Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/31/2020
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
ms.openlocfilehash: cbd4c118de2e91c8849461b20a01403049a07e66
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024627"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Provisionar um ambiente de visualização do Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

Este tópico explica como provisionar um ambiente de visualização do Dynamics 365 Commerce.

Antes de começar, recomendamos que você faça uma verificação rápida deste tópico para ter uma ideia do que o processo requer.

> [!NOTE]
> Se ainda não tiver acesso à visualização do Dynamics 365 Commerce, você poderá solicitar o acesso de visualização do [site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Visão geral

Para provisionar com êxito o seu ambiente de visualização do Commerce, você deve criar um projeto com um nome e um tipo de produto específicos. O ambiente e o commerce scale unit (CSU) também têm alguns parâmetros específicos que você deve usar ao provisionar o comércio eletrônico posteriormente. As instruções neste tópico descrevem todas as etapas necessárias para concluir o provisionamento e os parâmetros que devem ser usados.

Após o provisionamento bem-sucedido de seu ambiente de visualização do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo. Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar. Você sempre poderá concluir as etapas opcionais posteriormente.

Para obter informações sobre como configurar seu ambiente de visualização do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md). Para obter informações sobre como configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).

Se tiver dúvidas sobre as etapas de provisionamento ou detectar problemas, informe à Microsoft em [Visualização do Microsoft Dynamics 365 Commerce - grupo do Yammer](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem estar disponíveis para que você possa provisionar o seu ambiente de visualização do Commerce:

- Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.
- Você é um parceiro ou cliente do Microsoft Dynamics 365 existente e consegue criar um projeto do Dynamics 365 Commerce.
- Você foi aceito no programa de Visualização do Dynamics 365 Commerce.
- Você tem as permissões necessárias para criar um projeto para **Migrar, criar soluções e conhecer**.
- Você é membro da função **Gerente de ambiente** ou **Proprietário do projeto** no projeto no qual você irá provisionar o ambiente.
- Você tem acesso de administrador à sua assinatura do Microsoft Azure ou entra em contato com um administrador de assinatura que pode concluir as duas etapas que exigem permissões de administrador em seu nome.
- Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível. (Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).

## <a name="provision-your-commerce-preview-environment"></a>Provisionar seu ambiente de visualização do Commerce

Estes procedimentos explicam como provisionar um ambiente de visualização do Commerce. Depois de concluí-los com êxito, o ambiente de visualização do Commerce estará pronto para a configuração. Todas as atividades descritas aqui ocorrem no portal do LCS.

> [!IMPORTANT]
> O acesso de visualização está vinculado à conta e à organização do LCS que você especificou no aplicativo de visualização do Commerce. Você deve usar a mesma conta para provisionar o ambiente de visualização do Commerce. Se for necessário usar uma conta ou um locatário diferentes da LCS para o ambiente de visualização do Commerce, forneça esses detalhes à Microsoft. Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support) posteriormente neste tópico.

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
> Talvez não seja necessário concluir as etapas 6, 7 e/ou 8, porque as páginas que têm uma única opção são ignoradas. Quando estiver na exibição de **Parâmetros do ambiente**, confirme se o texto **Dynamics 365 Commerce - Demonstração (10.0.* x* com atualização de plataforma *xx*)** aparece diretamente acima do campo **Nome do ambiente**. Para obter detalhes, consulte a ilustração que aparece após a etapa 8.

1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione **Adicionar** para adicionar um ambiente.
1. No campo **Versão do aplicativo**, selecione a versão mais recente. Se você tiver uma necessidade específica de selecionar uma versão de aplicativo diferente da versão mais atual, não selecione uma versão antes de **10.0.8.**
1. No campo **Versão da plataforma**, use a versão da plataforma que é escolhida automaticamente para a versão do aplicativo selecionada. 

    ![Seleção das versões do aplicativo e da plataforma](./media/project1.png)

1. Selecione **Avançar**.
1. Selecione **Demonstração** como a topologia do ambiente.

    ![Selecionar a topologia de ambiente 1](./media/project2.png)

1. Selecione **Dynamics 365 Commerce - Demonstração** como a topologia do ambiente. Se você configurou um único Conector do Azure anteriormente, isso será usado para este ambiente. Se você configurou vários Conectores do Azure, é possível selecionar qual conector usar: **Leste dos EUA**, **Leste dos EUA 2,** **Oeste dos EUA**, ou **Oeste dos EUA 2**. (Para obter o melhor desempenho de ponta a ponta, recomendamos que você selecione **Oeste dos EUA 2**.)

    ![Selecionando a topologia de ambiente 2](./media/project3.png)

1. Na página **Implantar ambiente**, insira um nome de ambiente. Deixe as configurações avançadas como estão.

    ![Implantar página do ambiente](./media/project4.png)

1. Ajuste o tamanho da VM, conforme necessário. (Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)
1. Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.
1. Selecione **Avançar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**. Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.

    Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado. Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos. Portanto, verifique novamente depois de aproximadamente seis a nove horas.

1. Antes de continuar, verifique se o status de ambiente está **Implantado**.

### <a name="initialize-the-commerce-scale-unit-csu"></a>Inicializar o commerce scale unit (CSU)

Para inicializar sua CSU, siga estas etapas.

1. Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.
1. Nas visualização do ambiente à direita, selecione **Detalhes completos**. A visualização de detalhes do ambiente é exibida.
1. Em **Recursos do ambiente**, selecione **Gerenciar**.
1. Na guia **Commerce**, selecione **Inicializar**. A visualização dos parâmetros de inicialização do CSU será exibida.
1. No campo **Região**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.
1. No campo **Versão**, selecione **Especificar uma versão** na lista e, em seguida, especifique **9.18.20014.4** no campo que é exibido. Certifique-se de especificar a versão exata indicada aqui. Caso contrário, será necessário atualizar a RCSU para a versão correta posteriormente.
1. Ative a opção **Aplicar extensão**.
1. Na lista de extensões, selecione **Extensão da Demonstração da Versão Prévia do Commerce**.
1. Selecione **Inicializar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**. O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio** é selecionada. Sua CSU foi enfileirada para provisionamento.
1. Antes de continuar, verifique se o status de CSU é **Êxito**. A inicialização leva cerca de duas a cinco horas.

### <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico

Para inicializar o comércio eletrônico, siga estas etapas.

1. Na guia **Comércio eletrônico**, revise o consentimento da visualização e, depois, selecione **Configurar**.
1. No campo **Nome do locatário de comércio eletrônico**, informe um nome. No entanto, observe que este nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.
1. No campo **Nome de commerce scale unit**, selecione o seu CSU na lista. (A lista deve ter apenas uma opção).

    O **Geografia de comércio eletrônico** é definido automaticamente, e o valor não pode ser alterado.

1. Selecione **Avançar** para continuar.
1. No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.
1.  No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você deseja usar. Selecione o ícone de lupa para exibir os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
2.  No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você deseja usar. Selecione o ícone de lupa para exibir os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
1. Deixe a opção **Habilitar classificações e examinar o serviço** ativada.
1. Selecione **Inicializar**. O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio eletrônico** é selecionada. A inicialização de Comércio eletrônico começou.
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

[Visão geral do ambiente de visualização do Dynamics 365 Commerce](cpe-overview.md)

[Configurar um ambiente de visualização do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar recursos opcionais para um ambiente de visualização do Dynamics 365 Commerce](cpe-optional-features.md)

[Perguntas frequentes do ambiente de visualização do Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

