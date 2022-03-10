---
title: Não é possível configurar um grupo de segurança para construtor de sites do Commerce durante a implantação inicial
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando o grupo de segurança do Microsoft Azure Active Directory (Azure AD) para o construtor de sites do Commerce aparece como uma opção quando você cria componentes de comércio eletrônico no Microsoft Dynamics Lifecycle Services (LCS) durante a implantação inicial de um novo locatário de comércio eletrônico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f930cac61b747037b9fbecc7397a9b1b7db5dabd8a86b63a61c92ac7abe17516
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765161"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Não é possível configurar um grupo de segurança para construtor de sites do Commerce durante a implantação inicial

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientação de solução de problemas que pode ser útil quando o grupo de segurança do Microsoft Azure Active Directory (Azure AD) para o construtor de sites do Commerce aparece como uma opção quando você cria componentes de comércio eletrônico no Microsoft Dynamics Lifecycle Services (LCS) durante a implantação inicial de um novo locatário de comércio eletrônico.

## <a name="description"></a>descrição

Quando você cria os componentes de comércio eletrônico como parte do processo de implantação de um novo locatário de comércio eletrônico que inclui o componente do construtor de sites do Commerce, o grupo de segurança do Azure AD não aparece como uma opção na caixa de diálogo.

## <a name="resolution"></a>Resolução

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Provisionar o site de comércio eletrônico com um usuário no locatário correto

1. Acesse o [portal do Azure](https://portal.azure.com/).
1. No locatário para o qual o projeto LCS para seu site de comércio eletrônico foi provisionado, siga as instruções em [Criar um grupo básico e adicionar membros usando o Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Acesse [LCS](https://lcs.dynamics.com/)e efetue login usando uma conta que compartilhe o mesmo locatário que o grupo de segurança do Azure AD que você acabou de criar. A conta deve ter acesso para exibir o grupo de segurança do Azure AD.
1. Conclua as etapas de configuração para configurar o site de comércio eletrônico. Quando você provisiona os componentes de comércio eletrônico, o grupo de segurança deve aparecer agora como uma opção na caixa de diálogo.

> [!NOTE]
> Para garantir que o campo na caixa de diálogo seja preenchido com a lista de grupos de segurança, você deve selecionar **Enter** depois de inserir o nome do grupo de segurança do Azure AD que você criou. Os resultados da pesquisa listarão todos os grupos de segurança do Azure AD que começam com o texto de pesquisa e para os quais o usuário tem acesso. Você pode usar um termo de pesquisa mais curto para permitir resultados de pesquisa mais amplos.

## <a name="additional-resources"></a>Recursos adicionais

[Criar um grupo básico e adicionar membros usando o Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Implantar um novo locatário de comércio eletrônico](../deploy-ecommerce-site.md)