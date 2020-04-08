---
title: Verifique se a gravação dupla está configurada nos aplicativos Finance and Operations e Common Data Service
description: Este tópico explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Common Data Service.
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
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172636"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="a90d9-103">Verifique se a gravação dupla está configurada nos aplicativos Finance and Operations e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a90d9-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="a90d9-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a90d9-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="a90d9-105">Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a90d9-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="a90d9-106">Verifique se a gravação dupla está configurada em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a90d9-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="a90d9-107">Para determinar se os erros que você vê ao tentar salvar registros para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.</span><span class="sxs-lookup"><span data-stu-id="a90d9-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="a90d9-108">Se você tiver privilégios de administrador no aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="a90d9-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="a90d9-109">Se os detalhes dos ambientes vinculados e a lista de mapas de entidade que estão sendo executados são exibidos, a gravação dupla é configurada.</span><span class="sxs-lookup"><span data-stu-id="a90d9-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![Verificando a conexão do aplicativo Finance and Operations quando você tem privilégios administrativos](media/verify_fin_ops_1.png)

+ <span data-ttu-id="a90d9-111">Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não será possível gravar dados no nome da entidade \< da entidade \>*.</span><span class="sxs-lookup"><span data-stu-id="a90d9-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="a90d9-112">No exemplo da ilustração a seguir, não é possível criar um registro de cliente no aplicativo Finance and Operations, porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a90d9-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![Verificando a conexão do aplicativo Finance and Operations quando você não tem privilégios administrativos](media/verify_fin_ops_2.png)

<span data-ttu-id="a90d9-114">Para obter informações sobre como corrigir problemas ao criar dados em aplicativos Finance and Operations, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="a90d9-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="a90d9-115">Verifique se a gravação dupla está configurada em Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a90d9-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="a90d9-116">Ao criar dados, se você vir o campo **Empresa** em páginas no Common Data Service, a gravação dupla é configurada.</span><span class="sxs-lookup"><span data-stu-id="a90d9-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![Verificando a conexão Common Data Service](media/verify_cds.png)

<span data-ttu-id="a90d9-118">Para obter informações sobre como corrigir problemas ao criar dados em Common Data Service, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="a90d9-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="a90d9-119">Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Common Data Service, consulte [Habilitar e exibir o log de rastreamento de plug-in no Common Data Service para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="a90d9-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
