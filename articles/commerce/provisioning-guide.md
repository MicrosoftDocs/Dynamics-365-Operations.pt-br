---
title: Provisionar um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como provisionar um ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: e5ce2002c66a1c36d5647d3c76684b394fc1ff79
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599841"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Provisionar um ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico explica como provisionar um ambiente de avaliação do Microsoft Dynamics 365 Commerce.

Antes de começar, recomendamos que você faça uma verificação rápida deste tópico para ter uma ideia do que o processo requer.

> [!NOTE]
> Os ambientes de avaliação do Commerce não estão disponíveis para o público geral e são concedidos a parceiros e clientes por solicitação. Para obter mais informações, fale com o contato do seu parceiro Microsoft.

## <a name="overview"></a>Visão Geral

Para provisionar um ambiente de avaliação do Commerce com êxito, você deve criar um projeto que tenha um nome e um tipo de produto específicos. O ambiente e o Commerce Scale Unit (CSU) também têm alguns parâmetros específicos que você deve usar quando espera provisionar o comércio eletrônico posteriormente. As instruções neste tópico descrevem todas as etapas que são necessárias para concluir o provisionamento e os parâmetros que devem ser usados.

Após o provisionamento bem-sucedido do ambiente de avaliação do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo para uso. Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar. Você sempre poderá concluir as etapas opcionais posteriormente.

Para obter informações sobre como configurar seu ambiente de avaliação do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de avaliação do Commerce](cpe-post-provisioning.md). Para obter informações sobre como configurar recursos opcionais para o ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem estar em vigor para que você possa provisionar seu ambiente de avaliação do Commerce:

- Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.
- Você é um parceiro ou cliente do Microsoft Dynamics 365 existente e consegue criar um projeto do Dynamics 365 Commerce.
- Você tem acesso de administrador à assinatura do Microsoft Azure ou está em contato com um administrador de assinaturas que poderá ajudar se for necessário.
- Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.
- Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível. (Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).

Esta lista não é exaustiva. Se tiver problemas, fale com o contato do seu parceiro Microsoft para obter ajuda.

## <a name="provision-your-commerce-evaluation-environment"></a>Provisionar seu ambiente de avaliação do Commerce

Estes procedimentos explicam como provisionar um ambiente de avaliação do Commerce. Depois que você concluí-los com êxito, o ambiente de avaliação do Commerce estará pronto para a configuração. Todas as atividades descritas aqui ocorrem no portal do LCS.

### <a name="create-a-new-project"></a>Criar um novo projeto

Para criar um novo projeto no LCS, siga estas etapas.

1. Na home page do LCS, selecione o sinal de mais (**+**) para criar um projeto.
1. No painel à direita, siga uma destas etapas:

    - Se você for um parceiro, selecione **Migrar, criar soluções e conhecer**.
    - Se for um cliente, selecione **Pré-vendas de clientes potenciais**.

1. Inserir um nome, descrição e setor.
1. No campo **Nome do produto**, selecione **Dynamics 365 Commerce**.
1. No campo **Versão do produto**, selecione **Dynamics 365 Commerce**.
1. No campo **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.
1. Opcional: você pode importar funções e usuários de um projeto existente.
1. Selecione **Criar**. A exibição do projeto é exibida.

### <a name="add-the-azure-connector"></a>Adicione o Conector do Azure

Para adicionar o Conector do Azure ao projeto do LCS, siga as etapas em [Concluir o processo de integração do Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).

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

1. Na página **Implantar ambiente**, insira um nome de ambiente. Deixe as configurações avançadas como estão.

    ![Implantar página do ambiente](./media/project4.png)

1. Ajuste o tamanho da VM, conforme necessário. (Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)
1. Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.
1. Selecione **Avançar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**. Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.

    Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado. Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos. Portanto, verifique novamente depois de aproximadamente seis a nove horas.

1. Antes de continuar, verifique se o status de ambiente está **Implantado**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicializar o Commerce Scale Unit (nuvem)

Para inicializar sua CSU, siga estas etapas.

1. Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.
1. Nas visualização do ambiente à direita, selecione **Detalhes completos**. A visualização de detalhes do ambiente é exibida.
1. Em **Recursos do ambiente**, selecione **Gerenciar**.
1. Na guia **Commerce**, selecione **Inicializar**. A visualização dos parâmetros de inicialização do CSU será exibida.
1. No campo **Região**, selecione a região que é igual ou próxima à região na qual você implantou o ambiente.
1. Deixe o campo **Versão** como está.
1. Selecione **Inicializar**.
1. Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**. O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio** é selecionada. Sua CSU foi enfileirada para provisionamento.
1. Antes de continuar, verifique se o status de CSU é **Êxito**. A inicialização leva cerca de duas a cinco horas.

Se não conseguir encontrar o link **Gerenciar** na exibição de detalhes do ambiente, fale com seu contato da Microsoft para obter ajuda.

### <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico

Para inicializar o comércio eletrônico, siga estas etapas.

1. Na guia **Comércio eletrônico**, revise o consentimento da avaliação e selecione **Configurar**.
1. No campo **Nome do ambiente de comércio eletrônico**, insira um nome. Observe que esse nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.
1. No campo **Nome do Commerce Scale Unit**, selecione o seu CSU na lista. (A lista deve ter apenas uma opção).

    O campo **Geografia de comércio eletrônico** é definido automaticamente.

1. Selecione **Avançar** para continuar.
1. No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.
1. No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
1.  No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
1. Deixe a opção **Habilitar serviço de classificações e opiniões** como **Sim**.
1. Selecione **Inicializar**. O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio eletrônico** é selecionada. A inicialização de Comércio eletrônico começou.
1. Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **Inicialização com êxito**.
1. Em **Links** no canto inferior direito, anote as URLs dos seguintes links:

    * **Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.
    * **Construtor de sites do Commerce** – O link para a ferramenta de gerenciamento de sites.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de provisionamento e configuração de seu ambiente de avaliação do Commerce, consulte [Configurar um ambiente de avaliação do Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de avaliação do Dynamics 365 Commerce](cpe-overview.md)

[Configurar um ambiente de avaliação do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce](cpe-optional-features.md)

[Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (nuvem)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
