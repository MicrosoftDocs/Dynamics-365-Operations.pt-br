---
title: Verificar configuração de gravação dupla nos aplicativos Finance and Operations e Dataverse
description: Este tópico explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: af746d1d20ddd1552bce797288c6d62d69d7bd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748840"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="298c3-103">Verificar configuração de gravação dupla nos aplicativos Finance and Operations e Dataverse</span><span class="sxs-lookup"><span data-stu-id="298c3-103">Verify dual-write configuration in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="298c3-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="298c3-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="298c3-105">Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Dataverse.</span><span class="sxs-lookup"><span data-stu-id="298c3-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="298c3-106">Verifique se a gravação dupla está configurada em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="298c3-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="298c3-107">Para determinar se os erros que você vê ao tentar salvar linhas para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.</span><span class="sxs-lookup"><span data-stu-id="298c3-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="298c3-108">Se você tiver privilégios de administrador no aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="298c3-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="298c3-109">Se os detalhes dos ambientes vinculados e a lista de mapas de tabela que estão sendo executados são exibidos, a gravação dupla é configurada.</span><span class="sxs-lookup"><span data-stu-id="298c3-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Verificando a conexão do aplicativo Finance and Operations quando você tem privilégios administrativos](media/verify_fin_ops_1.png)

+ <span data-ttu-id="298c3-111">Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não é possível gravar dados na entidade \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="298c3-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="298c3-112">No exemplo da ilustração a seguir, não é possível criar uma linha de cliente no aplicativo Finance and Operations, porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="298c3-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Verificando a conexão do aplicativo Finance and Operations quando você não tem privilégios administrativos](media/verify_fin_ops_2.png)

<span data-ttu-id="298c3-114">Para obter informações sobre como corrigir problemas ao criar dados em aplicativos Finance and Operations, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="298c3-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="298c3-115">Verifique se a gravação dupla está configurada em Dataverse</span><span class="sxs-lookup"><span data-stu-id="298c3-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="298c3-116">Ao criar dados, se você vir a coluna **Empresa** em páginas no Dataverse, a gravação dupla está configurada.</span><span class="sxs-lookup"><span data-stu-id="298c3-116">When you create data, if you see the **Company** column on pages in Dataverse, dual-write is configured.</span></span>

![Verificando a conexão Dataverse](media/verify_cds.png)

<span data-ttu-id="298c3-118">Para obter informações sobre como corrigir problemas ao criar dados em Dataverse, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="298c3-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="298c3-119">Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Dataverse, consulte [Habilitar e exibir o log de rastreamento de plug-in no Dataverse para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="298c3-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]