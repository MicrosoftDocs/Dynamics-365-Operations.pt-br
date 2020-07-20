---
title: Implantar um novo locatário de comércio eletrônico
description: Este tópico descreve como implantar um novo locatário de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00f35b516dbf6ab4d4d9171c84a16b89f6afe832
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533266"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Implantar um novo locatário de comércio eletrônico


[!include [banner](includes/banner.md)]

Este tópico descreve como implantar um novo site de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).

## <a name="overview"></a>Visão geral

Microsoft Dynamics Lifecycle Services (LCS) é um espaço de trabalho colaborativo baseado em nuvem que parceiros e clientes podem usar para gerenciar seus produtos e ambientes, exibir as informações mais recentes de produtos e serviços do Microsoft Dynamics, e criar, rastrear e navegar em incidentes de suporte. Os recursos de gerenciamento de comércio online são integrados no LCS.

Para saber mais sobre LCS, consulte [Guia do usuário do Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Comece a usar

Antes de poder iniciar o comércio online, você deve inicializar um projeto, um ambiente e um Retail Cloud Scale Unit (RCSU). Para realizar a inicialização em LCS, você deve ter permissões para a função do gerente Proprietário do Projeto ou de Ambiente. As topologias de produção e do ambiente do sandbox são suportadas.

Para obter mais informações sobre os ambientes, consulte [Planejamento de ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Para obter mais informações sobre RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico

Use este procedimento para inicializar o recurso de comércio online em um ambiente existente.

Antes de começar, verifique se você tem as seguintes informações necessárias:

- O RCSU que será usado.
- O grupo de segurança do Microsoft Azure Active Directory que será usado para administradores de sistemas de eletrônicos online.
- O grupo de segurança do Microsoft Azure Active Directory que será usado para moderadores de avaliações e opiniões.
- Os domínios que serão associados com o ambiente.

Além disso, você pode coletar as seguintes informações opcionais:

- Informações de business-to-consumer (B2C) do Azure AD:

    - Nome do locatário.
    - ID do Cliente.
    - Domínio Personalizado de Logon.
    - Resposta de URL.
    - ID da Política de Entrada da Inscrição.
    - ID da política de senha de redefinição.
    - Editar ID da Política de Perfil.

> [!NOTE]
> Essas informações podem ser adicionadas posteriormente, com uma solicitação de serviço.

Depois que coletou informações obrigatórias, siga essas etapas para inicializar o comércio online.

1. Entre no [LCS](https://lcs.dynamics.com).
1. Abra o projeto que contém o ambiente onde você deseja inicializar o comércio online.
1. Na seção **Ambientes**, selecione o ambiente.
1. Em **Recursos de ambiente**, selecione o link **Gerente de retail**.
1. Na guia **Comércio eletrônico**, selecione **Configuração**. É exibida uma caixa de diálogo, onde você pode inserir as informações que são necessárias para provisionamento.
1. Preencha as informações necessárias, e vá para a próxima página.
1. Na página a seguir, preencha as informações necessárias e depois envie o formulário. Você volta para a guia **Comércio online**, onde você pode ver que a inicialização foi iniciada.
1. Para exibir o status de inicialização, **Atualize** ou retorne para a guia **Comércio online** posteriormente.
    
Quando o comércio online é inicializado do LCS, o sistema provisiona vários componentes necessários para o comércio online para associá-los ao ambiente. Depois que o provisionamento é concluído, a guia **Comércio eletrônico** na página **Gerenciamento de varejo** é atualizada para refletir o provisionamento. A página mostra as últimas implantações de personalização e o status de quaisquer outras implantações em andamento. Ela também inclui links para o site de comércio eletrônico e o assistente para criação de sites de comércio eletrônico, onde os sites são criados.

## <a name="access-site-builder"></a>Acessar o assistente para criação de sites

Para acessar o assistente para criação de sites, vá para a guia **Comércio eletrônico** na página **Gerenciamento de varejo** no LCS e selecione o link **Ferramenta de gerenciamento de site de comércio eletrônico**. A página de aterrissagem do assistente para criação de sites mostra uma exibição no nível de locatário. Nesta página, você pode:

- Modifique configurações no nível de locatário.
- Navegar para qualquer site que você criou e tem permissão para exibir. 
- Acessar recursos de Revisões, como relatórios e moderação.
- Criar um novo site. Para obter mais informações sobre como criar um novo site, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Recursos adicionais

[Configure seu nome de domínio](configure-your-domain-name.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
