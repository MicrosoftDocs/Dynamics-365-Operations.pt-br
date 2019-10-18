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
# <a name="azure-active-directory-users-not-found-in-people-picker"></a>Usuários do Azure Active Directory não encontrados no Seletor de Pessoas

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Emissão

Determinados usuários válidos no Microsoft Azure Active Directory (Azure AD) do locatário não são exibidos durante a pesquisa do nome no Seletor de Pessoas no Dynamics 365 Talent: Attract ou Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Causa

Determinados tipos de usuários atualmente não possuem suporte no Attract e Onboard. Verifique se o usuário não é um usuário convidado do Azure AD Business to Business (B2B). Informações do "Tipo de Usuário" podem ser encontradas na folha do Azure Active Directory no portal do Azure.

Para obter mais informações sobre o Azure B2B, consulte [Qual é o acesso do usuário convidado do Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

Para usuários não-B2B, há determinados usuários que podem ter uma propriedade "Tipo de Usuário" no objeto **Usuário**. Isso pode ser verificado e corrigido usando-se o módulo Azure AD Powershell. Para obter mais informações, consulte [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Resolução

Para concluir as etapas seguintes para resolver o problema, será necessário ter permissões de "Administrador Global" no locatário do Azure Active Directory ou permissões para **User.ReadWrite.All**.

Para verificar o "Tipo de Usuário" do usuário afetado.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
O comando retorna as seguintes informações.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Observe a propriedade **UserType** no usuário. Se o **UserType** estiver em branco, por exemplo, não for "Membro" ou "Convidado", atualize o **UserType** usando o seguinte comando.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
