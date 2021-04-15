---
title: Não é possível configurar um grupo de segurança para construtor de sites do Commerce durante a implantação inicial
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando o grupo de segurança do Microsoft Azure Active Directory (Azure AD) para o construtor de sites do Commerce aparece como uma opção quando você cria componentes de comércio eletrônico no Microsoft Dynamics Lifecycle Services (LCS) durante a implantação inicial de um novo locatário de comércio eletrônico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: aa00e9331693600ced2f4ead399a0c005b77ad08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801498"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="564b5-103">Não é possível configurar um grupo de segurança para construtor de sites do Commerce durante a implantação inicial</span><span class="sxs-lookup"><span data-stu-id="564b5-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="564b5-104">Este tópico fornece orientação de solução de problemas que pode ser útil quando o grupo de segurança do Microsoft Azure Active Directory (Azure AD) para o construtor de sites do Commerce aparece como uma opção quando você cria componentes de comércio eletrônico no Microsoft Dynamics Lifecycle Services (LCS) durante a implantação inicial de um novo locatário de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="564b5-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="564b5-105">descrição</span><span class="sxs-lookup"><span data-stu-id="564b5-105">Description</span></span>

<span data-ttu-id="564b5-106">Quando você cria os componentes de comércio eletrônico como parte do processo de implantação de um novo locatário de comércio eletrônico que inclui o componente do construtor de sites do Commerce, o grupo de segurança do Azure AD não aparece como uma opção na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="564b5-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="564b5-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="564b5-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="564b5-108">Provisionar o site de comércio eletrônico com um usuário no locatário correto</span><span class="sxs-lookup"><span data-stu-id="564b5-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="564b5-109">Vá para o [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="564b5-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="564b5-110">No locatário para o qual o projeto LCS para seu site de comércio eletrônico foi provisionado, siga as instruções em [Criar um grupo básico e adicionar membros usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="564b5-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="564b5-111">Vá para [LCS](https://lcs.dynamics.com/)e efetue login usando uma conta que compartilhe o mesmo locatário que o grupo de segurança do Azure AD que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="564b5-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="564b5-112">A conta deve ter acesso para exibir o grupo de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="564b5-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="564b5-113">Conclua as etapas de configuração para configurar o site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="564b5-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="564b5-114">Quando você provisiona os componentes de comércio eletrônico, o grupo de segurança deve aparecer agora como uma opção na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="564b5-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="564b5-115">Para garantir que o campo na caixa de diálogo seja preenchido com a lista de grupos de segurança, você deve selecionar **Enter** depois de inserir o nome do grupo de segurança do Azure AD que você criou.</span><span class="sxs-lookup"><span data-stu-id="564b5-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="564b5-116">Os resultados da pesquisa listarão todos os grupos de segurança do Azure AD que começam com o texto de pesquisa e para os quais o usuário tem acesso.</span><span class="sxs-lookup"><span data-stu-id="564b5-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="564b5-117">Você pode usar um termo de pesquisa mais curto para permitir resultados de pesquisa mais amplos.</span><span class="sxs-lookup"><span data-stu-id="564b5-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="564b5-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="564b5-118">Additional resources</span></span>

[<span data-ttu-id="564b5-119">Criar um grupo básico e adicionar membros usando o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="564b5-119">Create a basic group and add members using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="564b5-120">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="564b5-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)
