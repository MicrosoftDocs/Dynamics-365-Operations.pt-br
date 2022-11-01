---
title: Regulatory Configuration Service
description: Este artigo fornece uma visão geral dos recursos do Regulatory Configuration Service (RCS) e explica como acessar o serviço.
author: kfend
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
ms.openlocfilehash: c04b13ef05424b27b5abcc2ac7490a7b75797bf5
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713908"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

O Regulatory Configuration Service (RCS) é um designer autônomo e um serviço de gerenciamento do ciclo de vida para recurso de globalização sem código/baixo código. As partes interessadas de globalização do RCS estendem e personalizam as principais áreas de globalização de imposto, faturamento eletrônica, relatórios de regulamentação, bancos e documentos de negócios sem precisar envolver desenvolvedores. Essa abordagem de globalização sem código/pouco código facilita a globalização e a torna mais rápida e mais econômica para criar ou estender.

o RCS oferece os seguintes recursos:

- Suporte a todos os recursos fornecidos pelo Relatório Eletrônico (ER).
- Um pré-requisito para configurar novos microsserviços de globalização.
- Suporte para faturamento eletrônico. Para obter mais informações, consulte [Faturamento Eletrônico](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Suporte para cálculo de imposto. Para obter mais informações, consulte [Serviço de imposto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Suporte à nova funcionalidade do recurso de globalização que simplifica o gerenciamento do ciclo de vida de recursos de vários componentes e oferece capacidade extra para configurar ações e definir parâmetros do recurso. Para obter mais informações, consulte [Regulatory Configuration Service — gerenciamento do recurso de globalização simplificado para serviços de globalização](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Suporte à publicação centralizada, ao armazenamento e ao compartilhamento de configurações personalizadas no repositório Global para simplificar o gerenciamento da configuração sem precisar do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Acesse o RCS

Você pode inscrever-se ou entrar no RCS na [página do Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Inscrever-se/entrar no RCS.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Na página **Regulatory Configuration Service**, reveja e aceite os termos e condições adicionais para uso do serviço e selecione um destes botões:

- **Inscrever-se**, se você for um usuário do serviço pela primeira vez e estiver usando um endereço de email comercial para provisionar sua organização um ambiente de serviço
- **Entrar**, se você já se inscreveu no serviço e deseja acessar seu ambiente de organização

> [!NOTE] 
> Depois de se inscrever, recomendamos que você adicione outro usuário SysAdmin ao ambiente do RCS. Esse usuário será provisionado como coadministrador do ambiente. Isso ajudará a dar estabilidade de acesso ao ambiente do RCS, uma vez que a função SysAdmin é gerenciar usuários para esse ambiente. Você pode adicionar usuários usando o **espaço de trabalho do RCS > Administração do Sistema**.

## <a name="regional-availability"></a>Disponibilidade regional

O RCS está geralmente disponível nas seguintes regiões:

- Estados Unidos
- Índia
- França
- Europa

Para ver uma lista completa de regiões, consulte [Dynamics 365 e Power Platform: disponibilidade, local de dados, idioma e localização](https://aka.ms/dynamics_365_international_availability_deck).

> [!NOTE] 
> No momento, o RCS não está disponível para a Nuvem da Comunidade Governamental (GCC).

## <a name="rcs-default-company"></a>Empresa padrão do RCS

A funcionalidade de tempo de design que é usada no RCS é compartilhada entre todas as empresas. Não existe uma funcionalidade específica a uma empresa. Portanto, recomendamos que você use uma empresa, **DAT**, com o seu ambiente do RCS.

No entanto, em alguns cenários, talvez você queira que os formatos do ER usem os parâmetros relacionadas a uma entidade legal específica. Somente nesses cenários, você deve usar o alternador da empresa padrão. Para ver um exemplo, consulte [Configurar o formato do ER para usar parâmetros específicos a uma entidade legal](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Documentação do RCS relacionado

Para obter mais informações sobre componentes relacionados, consulte os seguintes tópicos:

- **RCS:**

    - [Criar configurações ER no RCS e carregá-las no repositório Global](rcs-global-repo-upload.md)

- **Repositório global:**

    - [Criar configuração de ER e carregar no repositório global](rcs-global-repo-upload.md)
    - [Compartilhar configuração no repositório global](rcs-global-repo-share-configuration.md)
    - [Filtragem avançada no repositório global](enhanced-filtering-global-repo.md)
    - [Baixar configurações ER do repositório global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Descontinuar configurações no repositório global](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Recurso de globalização:**

    - [Regulatory Configuration Service(RCS) — Recursos de globalização](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Solução de problemas de inscrição no RCS

Quando você se inscreve no RCS em uma página de serviço, você pode encontrar um problema relacionado ao Azure Active Directory (Azure AD). A mensagem de erro que você recebe indica que a inscrição no RCS está temporariamente desativada e deve ser reativada para que você conclua o processo de inscrição.

![Mensagem de erro de inscrição no RCS.](media/01_RCSSignUpError.jpg)

O problema ocorre porque você não pode se inscrever em assinaturas ad-hoc, e a propriedade `AllowAdHocSubscriptions` deve ser habilitada no seu locatário. 

- Se o seu departamento de TI gerenciar os locatários do Azure da sua organização, entre em contato com esse departamento para relatar o problema.
- Se você for responsável por gerenciar os locatários do Azure, você pode corrigir os problemas seguindo as etapas em [O que é a autoinscrição para o Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
