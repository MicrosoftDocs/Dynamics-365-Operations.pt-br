---
title: Usuário não encontrado no Seletor de Pessoas no Attract ou Onboard
description: Este tópico explica o que fazer quando os usuários do locatário da empresa não estão sendo mostrados nos aplicativos Dynamics 365 for Talent Attract ou Onboard.
author: ChrisChua
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: chrichua
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2d4a74ee2cc65153c1f9fdc1b42c2fc440d188d6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303322"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a><span data-ttu-id="1c1e5-103">Usuários do Azure Active Directory não encontrados no Seletor de Pessoas</span><span class="sxs-lookup"><span data-stu-id="1c1e5-103">Azure Active Directory users not found in People Picker</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="1c1e5-104">Saída</span><span class="sxs-lookup"><span data-stu-id="1c1e5-104">Issue</span></span>

<span data-ttu-id="1c1e5-105">Determinados usuários válidos no Azure Active Directory (Azure AD) do locatário não aparecerão durante a pesquisa do nome do Seletor de Pessoas nos aplicativos Dynamics 365 for Talent Attract ou Onboard.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in the Dynamics 365 for Talent Attract or Onboard applications.</span></span>

## <a name="cause"></a><span data-ttu-id="1c1e5-106">Causa</span><span class="sxs-lookup"><span data-stu-id="1c1e5-106">Cause</span></span>

<span data-ttu-id="1c1e5-107">Determinados tipos de usuários atualmente não são suportados nos aplicativos Attract e Onboard.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-107">Certain user types are not currently supported in the Attract and Onboard applications.</span></span> <span data-ttu-id="1c1e5-108">Verifique se o usuário não é um usuário convidado do Azure AD Business to Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="1c1e5-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="1c1e5-109">Informações do "Tipo de Usuário" podem ser encontradas na folha do Azure Active Directory no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="1c1e5-110">Para obter mais informações sobre o Azure B2B, consulte [Qual é o acesso do usuário convidado do Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="1c1e5-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="1c1e5-111">Para usuários não-B2B, há determinados usuários que podem ter uma propriedade "Tipo de Usuário" no objeto **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="1c1e5-112">Isso pode ser verificado e corrigido usando-se o módulo Azure AD Powershell.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="1c1e5-113">Para obter mais informações, consulte [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="1c1e5-113">For more information, see [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="1c1e5-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="1c1e5-114">Resolution</span></span>

<span data-ttu-id="1c1e5-115">Para concluir as etapas seguintes para resolver o problema, será necessário ter permissões de "Administrador Global" no locatário do Azure Active Directory ou permissões para **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="1c1e5-116">Para verificar o "Tipo de Usuário" do usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="1c1e5-117">O comando retorna as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="1c1e5-118">Observe a propriedade **UserType** no usuário.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="1c1e5-119">Se o **UserType** estiver em branco, por exemplo, não for "Membro" ou "Convidado", atualize o **UserType** usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="1c1e5-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```