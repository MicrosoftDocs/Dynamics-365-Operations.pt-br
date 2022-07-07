---
title: Provisionar um ambiente de área restrita do Dynamics 365 Commerce
description: Este artigo explica como provisionar um ambiente de área restrita do Microsoft Dynamics 365 Commerce para uso de demonstração ou área restrita com dados de demonstração internos.
author: psimolin
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013125"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Provisionar um ambiente de área restrita do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artigo explica como provisionar um ambiente de área restrita do Microsoft Dynamics 365 Commerce para uso de demonstração com dados de demonstração internos. O processo de configuração de um ambiente de produção é semelhante, porém mais elaborado, uma vez que muitos dos pré-requisitos do ambiente de área restrita já são fornecidos nos dados de demonstração.

Antes de começar, recomendamos que você faça uma verificação rápida deste artigo para ter uma ideia do que o processo requer.

Para configurar com êxito um ambiente de área restrita do Commerce, você deve especificar alguns parâmetros para o ambiente e a CSU (Commerce Scale Unit) que será usada quando você provisionar o Commerce posteriormente. As instruções neste artigo descrevem todas as etapas que são necessárias para concluir o provisionamento e os parâmetros que devem ser usados.

Após o provisionamento com êxito do ambiente do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo para uso. Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja usar. Você sempre poderá concluir as etapas opcionais posteriormente.

Para obter informações sobre como configurar seu ambiente do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de área restrita do Commerce](cpe-post-provisioning.md). Para obter informações sobre como configurar recursos opcionais de seu ambiente do Commerce, consulte [Configurar recursos opcionais para um ambiente de área restrita do Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem estar disponíveis para que você possa provisionar seu ambiente do Commerce:

- Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.
- Você ser um parceiro ou cliente existente do Microsoft Dynamics 365 e ter um projeto de implementação já criado e disponível para uso no LCS.  
- Você ter criado um grupo de segurança do Azure Active Directory (Azure AD) que pode ser usado como um grupo de administradores de sistema do Commerce e ter sua ID disponível.
- Você ter criado grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de classificações e opiniões e ter sua ID disponível. (Esse grupo de segurança pode ser o mesmo que o grupo de administradores de sistema do Commerce).
- Você ter implantado uma instância da sede no LCS. Para obter mais informações, consulte [Implantar um novo ambiente](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Esta lista não é exaustiva. Se tiver problemas, fale com o contato do seu parceiro Microsoft para obter ajuda.

## <a name="provision-your-commerce-environment"></a>Provisionar seu ambiente do Commerce

Os procedimentos a seguir explicam como provisionar um ambiente do Commerce. Depois que você concluir as etapas com êxito, o ambiente do Commerce estará pronto para a configuração. Todas as etapas descritas abaixo ocorrem no portal do LCS.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicializar o Commerce Scale Unit (nuvem)

Para inicializar a CSU, siga estas etapas.

1. No LCS, selecione seu ambiente na lista.
1. Nas exibição **AMBIENTES** à direita, selecione **Detalhes completos**. A visualização de detalhes do ambiente é exibida.
1. Na seção **Gerenciar ambiente**, em **RECURSOS DO AMBIENTE**, selecione **Gerenciar**.
1. Na guia **Commerce Scale Units**, selecione **Inicializar**. A exibição **Adicionar a unidade de escala** será aberta.
1. No campo **REGIÃO**, selecione a região que seja igual ou próxima à região na qual você implantou o ambiente.
1. Na lista suspensa **Versão**, selecione a versão mais recente disponível.
1. Selecione **Inicializar**.
1. Na caixa de diálogo de aviso que solicita que você confirme a inicialização da Commerce Scale Unit, selecione **Sim**. A CSU agora foi enfileirada para provisionamento.
1. Antes de continuar, verifique se o status da CSU é **ÊXITO**. A inicialização leva cerca de duas a cinco horas.

Se não conseguir encontrar o link **Gerenciar** na exibição de detalhes do ambiente, fale com seu contato da Microsoft para obter ajuda.

### <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico

Para inicializar o Commerce, siga estas etapas.

1. Na guia **Comércio eletrônico**, selecione **Configuração**.
1. No campo **Nome do ambiente de comércio eletrônico**, insira um nome. Observe que esse nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.
1. No campo **Nome do Commerce Scale Unit**, selecione o seu CSU na lista. (A lista deve ter apenas uma opção).

    O campo **Geografia de comércio eletrônico** é definido automaticamente.

1. Selecione **Avançar** para continuar.
1. No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.
1. No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
1.  No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa. Selecione o grupo de segurança correto na lista.
1. Deixe a opção **Habilitar serviço de classificações e opiniões** como **Sim**.
1. Selecione **Inicializar**. O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio eletrônico** é selecionada. A inicialização de Comércio eletrônico começou.
1. Antes de continuar, aguarde até que o status de inicialização do Commerce seja **INICIALIZAÇÃO COM ÊXITO**.
1. Em **Links** no canto inferior direito, anote as URLs dos seguintes links:

    * **Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.
    * **Construtor de sites do Commerce** – O link para a ferramenta de gerenciamento de sites.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de provisionamento e configuração de seu ambiente do Commerce, consulte [Configurar um ambiente de área restrita do Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um ambiente de área restrita do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS em um ambiente de área restrita do Dynamics 365 Commerce](cpe-bopis.md)

[Configurar recursos opcionais para um ambiente de área restrita do  Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (nuvem)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
