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
ms.openlocfilehash: a6d916f87ca30aa7405a51841e56ab31bbe31ac8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460374"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a><span data-ttu-id="b3cc6-103">Usuário não encontrado no Seletor de Pessoas no Attract ou Onboard</span><span class="sxs-lookup"><span data-stu-id="b3cc6-103">User not found in People Picker in Attract or Onboard</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="b3cc6-104">Emissão</span><span class="sxs-lookup"><span data-stu-id="b3cc6-104">Issue</span></span>

<span data-ttu-id="b3cc6-105">Determinados usuários válidos no Microsoft Azure Active Directory (Azure AD) do locatário não são exibidos durante a pesquisa do nome no Seletor de Pessoas no Dynamics 365 Talent: Attract ou Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="b3cc6-106">Causa</span><span class="sxs-lookup"><span data-stu-id="b3cc6-106">Cause</span></span>

<span data-ttu-id="b3cc6-107">Determinados tipos de usuários atualmente não possuem suporte no Attract e Onboard.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="b3cc6-108">Verifique se o usuário não é um usuário convidado do Azure AD Business to Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="b3cc6-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="b3cc6-109">Informações do "Tipo de Usuário" podem ser encontradas na folha do Azure Active Directory no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="b3cc6-110">Para obter mais informações sobre o Azure B2B, consulte [Qual é o acesso do usuário convidado do Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="b3cc6-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="b3cc6-111">Para usuários não-B2B, há determinados usuários que podem ter uma propriedade "Tipo de Usuário" no objeto **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="b3cc6-112">Isso pode ser verificado e corrigido usando-se o módulo Azure AD Powershell.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="b3cc6-113">Para obter mais informações, consulte [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="b3cc6-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="b3cc6-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="b3cc6-114">Resolution</span></span>

<span data-ttu-id="b3cc6-115">Para concluir as etapas seguintes para resolver o problema, será necessário ter permissões de "Administrador Global" no locatário do Azure Active Directory ou permissões para **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="b3cc6-116">Para verificar o "Tipo de Usuário" do usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="b3cc6-117">O comando retorna as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="b3cc6-118">Observe a propriedade **UserType** no usuário.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="b3cc6-119">Se o **UserType** estiver em branco, por exemplo, não for "Membro" ou "Convidado", atualize o **UserType** usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
