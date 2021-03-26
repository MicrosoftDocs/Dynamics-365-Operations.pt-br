---
title: Desabilitar regras no verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade para desabilitar as regras do verificador de consistência das transações no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: abd97819d44963d22269efc9536f746c3c0b3812
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230581"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="5560e-103">Desabilitar regras no verificador de consistência das transações de varejo</span><span class="sxs-lookup"><span data-stu-id="5560e-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5560e-104">Os varejistas podem ter os cenários comerciais e processos que são exclusivos deles.</span><span class="sxs-lookup"><span data-stu-id="5560e-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="5560e-105">Portanto, nem todas as regras incluídas por padrão no verificador de consistência das transações comerciais são aplicáveis a todos os varejistas.</span><span class="sxs-lookup"><span data-stu-id="5560e-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="5560e-106">Para acomodar diferenças, o Microsoft Dynamics 365 Commerce fornece uma funcionalidade que pode ser usada para desabilitar as regras que não são aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="5560e-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="5560e-107">Para exibir a lista de regras que estão disponíveis no verificador de consistência das transações de varejo em seu ambiente e para consultar e o status de cada regra, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e selecione a guia **Validação da transação**.</span><span class="sxs-lookup"><span data-stu-id="5560e-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="5560e-108">Por padrão, o status de cada regra é definido como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="5560e-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="5560e-109">Portanto, todas as regras são usadas para validar transações de varejo antes que elas sejam incluídas nos demonstrativos comerciais.</span><span class="sxs-lookup"><span data-stu-id="5560e-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="5560e-110">Para desabilitar uma regra, altere seu status para **Desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="5560e-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="5560e-111">As regras desabilitadas não serão consideradas quando as transações forem validadas durante o processo de cálculo do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="5560e-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="5560e-112">Para ignorar o processo de validação inteiro, independentemente das regras que estão habilitadas, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e, na guia **Validação da transação**, defina a opção **Desativar verificador de consistência das transações do Commerce** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5560e-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="5560e-113">Depois que essa opção for definida como **Não**, ela não poderá ser redefinida como **Sim** na interface do usuário (IU).</span><span class="sxs-lookup"><span data-stu-id="5560e-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]