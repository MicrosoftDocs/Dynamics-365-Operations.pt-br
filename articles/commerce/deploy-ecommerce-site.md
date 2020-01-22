---
title: Implantar um novo locatário de comércio eletrônico
description: Este tópico descreve como implantar um novo locatário de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 10dab1e62446ff7f60ad48fd0841bde5cfd29e12
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945504"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Implantar um novo locatário de comércio eletrônico

[!include [banner](includes/preview-banner.md)]
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

[!NOTE]
Essas informações podem ser adicionadas posteriormente, com uma solicitação de serviço.

Depois que coletou informações obrigatórias, siga essas etapas para inicializar o comércio online.

1. Entre no [LCS](https://lcs.dynamics.com).
1. Abra o projeto que contém o ambiente onde você deseja inicializar o comércio online.
1. Na seção **Ambientes**, selecione o ambiente.
1. Em **Recursos de ambiente**, selecione o link **Gerente de retail**.
1. Na guia **Comércio eletrônico**, selecione **Configuração**. É exibida uma caixa de diálogo, onde você pode inserir as informações que são necessárias para provisionamento.
1. Preencha as informações necessárias, e vá para a próxima página.
1. Na página a seguir, preencha as informações necessárias e depois envie o formulário. Você volta para a guia **Comércio online**, onde você pode ver que a inicialização foi iniciada.
1. Para exibir o status de inicialização, **Atualize** ou retorne para a guia **Comércio online** posteriormente.
    
Quando o comércio online é inicializado do LCS, o sistema provisiona vários componentes necessários para o comércio online para associá-los ao ambiente. Após provisionar ser concluído, a guia **Comércio online** na guia **Gerenciamento de retail** é atualizada para refletir o provisionamento. A página mostra as últimas implantações de personalização e o status de quaisquer outras implantações em andamento. Também inclui links para site de comércio eletrônico e a ferramenta de gerenciamento de site de comércio online (a ferramenta de criação).

## <a name="access-the-authoring-environment"></a>Acessar o ambiente de criação

Para acessar o ambiente de criação, vá para a guia **Comércio online** na página **Gerenciamento de retail**. Nele, você encontrará os links para o site de comércio online e a ferramenta de gerenciamento de site.

## <a name="additional-resources"></a>Recursos adicionais

[Configure seu nome de domínio](configure-your-domain-name.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
