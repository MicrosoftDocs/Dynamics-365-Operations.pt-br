---
title: Solucionar problemas relacionados ao reconhecimento da solução
description: Este tópico fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 013e37269ec3df2bede15b28cffcc175967de9a3
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172612"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="f118a-103">Solucionar problemas relacionados ao reconhecimento da solução</span><span class="sxs-lookup"><span data-stu-id="f118a-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="f118a-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f118a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="f118a-105">Especificamente, ele fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.</span><span class="sxs-lookup"><span data-stu-id="f118a-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f118a-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f118a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="f118a-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="f118a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="f118a-108">Erro na página de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="f118a-108">Error on the Dual-write page</span></span>

<span data-ttu-id="f118a-109">Na página **Gravação dupla**, você pode receber uma mensagem de erro parecida com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="f118a-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="f118a-110">*A entidade com um nome "msdyn\_dualwriteentitymap" with namemapping="Logical" não foi encontrada no MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="f118a-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="f118a-111">Para corrigir o problema, verifique se a solução principal de gravação dupla está instalada no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f118a-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="f118a-112">A solução principal de gravação dupla é um pré-requisito para o reconhecimento da solução.</span><span class="sxs-lookup"><span data-stu-id="f118a-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
