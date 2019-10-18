---
title: Usuário não encontrado no Seletor de Pessoas no Attract ou Onboard
description: Este tópico explica o que fazer quando os usuários do locatário da empresa não estiverem sendo exibidos no Seletor de Pessoas no Dynamics 365 Talent - Attract ou Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2a3c83fcc3f48aa235ffb2db2dc492b34a306c4c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024175"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a><span data-ttu-id="f51c1-103">Usuários do Azure Active Directory não encontrados no Seletor de Pessoas</span><span class="sxs-lookup"><span data-stu-id="f51c1-103">Azure Active Directory users not found in People Picker</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="f51c1-104">Emissão</span><span class="sxs-lookup"><span data-stu-id="f51c1-104">Issue</span></span>

<span data-ttu-id="f51c1-105">Determinados usuários válidos no Microsoft Azure Active Directory (Azure AD) do locatário não são exibidos durante a pesquisa do nome no Seletor de Pessoas no Dynamics 365 Talent: Attract ou Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="f51c1-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="f51c1-106">Causa</span><span class="sxs-lookup"><span data-stu-id="f51c1-106">Cause</span></span>

<span data-ttu-id="f51c1-107">Determinados tipos de usuários atualmente não possuem suporte no Attract e Onboard.</span><span class="sxs-lookup"><span data-stu-id="f51c1-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="f51c1-108">Verifique se o usuário não é um usuário convidado do Azure AD Business to Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="f51c1-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="f51c1-109">Informações do "Tipo de Usuário" podem ser encontradas na folha do Azure Active Directory no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f51c1-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="f51c1-110">Para obter mais informações sobre o Azure B2B, consulte [Qual é o acesso do usuário convidado do Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="f51c1-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="f51c1-111">Para usuários não-B2B, há determinados usuários que podem ter uma propriedade "Tipo de Usuário" no objeto **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="f51c1-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="f51c1-112">Isso pode ser verificado e corrigido usando-se o módulo Azure AD Powershell.</span><span class="sxs-lookup"><span data-stu-id="f51c1-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="f51c1-113">Para obter mais informações, consulte [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="f51c1-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="f51c1-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="f51c1-114">Resolution</span></span>

<span data-ttu-id="f51c1-115">Para concluir as etapas seguintes para resolver o problema, será necessário ter permissões de "Administrador Global" no locatário do Azure Active Directory ou permissões para **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="f51c1-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="f51c1-116">Para verificar o "Tipo de Usuário" do usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="f51c1-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="f51c1-117">O comando retorna as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="f51c1-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="f51c1-118">Observe a propriedade **UserType** no usuário.</span><span class="sxs-lookup"><span data-stu-id="f51c1-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="f51c1-119">Se o **UserType** estiver em branco, por exemplo, não for "Membro" ou "Convidado", atualize o **UserType** usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="f51c1-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
