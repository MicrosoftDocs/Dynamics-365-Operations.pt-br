---
title: Configurar parâmetros de gerenciamento de benefícios por empresa
description: Configure parâmetros para o gerenciamento de benefícios por empresa no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805649"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="226e5-103">Configurar parâmetros de gerenciamento de benefícios por empresa</span><span class="sxs-lookup"><span data-stu-id="226e5-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="226e5-104">Para cada organização que ofereça benefícios, você deve definir configurações para emails de confirmação de benefícios.</span><span class="sxs-lookup"><span data-stu-id="226e5-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="226e5-105">Definir configurações de email de confirmação</span><span class="sxs-lookup"><span data-stu-id="226e5-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="226e5-106">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="226e5-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="226e5-107">Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="226e5-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="226e5-108">Campo</span><span class="sxs-lookup"><span data-stu-id="226e5-108">Field</span></span> | <span data-ttu-id="226e5-109">descrição</span><span class="sxs-lookup"><span data-stu-id="226e5-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="226e5-110">**Enviar email de confirmação**</span><span class="sxs-lookup"><span data-stu-id="226e5-110">**Send confirmation email**</span></span> | <span data-ttu-id="226e5-111">Quando este recurso estiver ativado, um email de confirmação será enviado aos funcionários quando eles verificarem a experiência de registro de benefícios no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="226e5-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="226e5-112">**Modelo de email de confirmação**</span><span class="sxs-lookup"><span data-stu-id="226e5-112">**Confirmation email template**</span></span> | <span data-ttu-id="226e5-113">Selecione o modelo de email da organização a ser usado quando enviar a confirmação do registro.</span><span class="sxs-lookup"><span data-stu-id="226e5-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="226e5-114">Se você não selecionar um modelo, o seguinte email genérico será enviado:</span><span class="sxs-lookup"><span data-stu-id="226e5-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="226e5-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="226e5-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="226e5-116">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="226e5-116">Congratulations!</span></span> <span data-ttu-id="226e5-117">Você concluiu com êxito o registro de benefícios.</span><span class="sxs-lookup"><span data-stu-id="226e5-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="226e5-118">Obrigado,</span><span class="sxs-lookup"><span data-stu-id="226e5-118">Thank you,</span></span><br><span data-ttu-id="226e5-119">Benefícios de <nome da empresa/organização></span><span class="sxs-lookup"><span data-stu-id="226e5-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="226e5-120">**Endereço de email padrão do remetente**</span><span class="sxs-lookup"><span data-stu-id="226e5-120">**Default email sender address**</span></span> | <span data-ttu-id="226e5-121">O endereço de email a ser usado quando enviar o email de confirmação.</span><span class="sxs-lookup"><span data-stu-id="226e5-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="226e5-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="226e5-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]