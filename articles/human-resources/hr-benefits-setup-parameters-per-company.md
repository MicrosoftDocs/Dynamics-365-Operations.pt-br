---
title: Configurar parâmetros de gerenciamento de benefícios por empresa
description: Configure parâmetros para o gerenciamento de benefícios por empresa no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "4984591"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="85492-103">Configurar parâmetros de gerenciamento de benefícios por empresa</span><span class="sxs-lookup"><span data-stu-id="85492-103">Configure Benefits management parameters per company</span></span>

<span data-ttu-id="85492-104">Para cada organização que ofereça benefícios, você deve definir configurações para emails de confirmação de benefícios.</span><span class="sxs-lookup"><span data-stu-id="85492-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="85492-105">Definir configurações de email de confirmação</span><span class="sxs-lookup"><span data-stu-id="85492-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="85492-106">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="85492-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="85492-107">Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="85492-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="85492-108">Campo</span><span class="sxs-lookup"><span data-stu-id="85492-108">Field</span></span> | <span data-ttu-id="85492-109">descrição</span><span class="sxs-lookup"><span data-stu-id="85492-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="85492-110">**Enviar email de confirmação**</span><span class="sxs-lookup"><span data-stu-id="85492-110">**Send confirmation email**</span></span> | <span data-ttu-id="85492-111">Quando este recurso estiver ativado, um email de confirmação será enviado aos funcionários quando eles verificarem a experiência de registro de benefícios no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="85492-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="85492-112">**Modelo de email de confirmação**</span><span class="sxs-lookup"><span data-stu-id="85492-112">**Confirmation email template**</span></span> | <span data-ttu-id="85492-113">Selecione o modelo de email da organização a ser usado quando enviar a confirmação do registro.</span><span class="sxs-lookup"><span data-stu-id="85492-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="85492-114">Se você não selecionar um modelo, o seguinte email genérico será enviado:</span><span class="sxs-lookup"><span data-stu-id="85492-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="85492-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="85492-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="85492-116">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="85492-116">Congratulations!</span></span> <span data-ttu-id="85492-117">Você concluiu com êxito o registro de benefícios.</span><span class="sxs-lookup"><span data-stu-id="85492-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="85492-118">Obrigado,</span><span class="sxs-lookup"><span data-stu-id="85492-118">Thank you,</span></span><br><span data-ttu-id="85492-119">Benefícios de <nome da empresa/organização></span><span class="sxs-lookup"><span data-stu-id="85492-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="85492-120">**Endereço de email padrão do remetente**</span><span class="sxs-lookup"><span data-stu-id="85492-120">**Default email sender address**</span></span> | <span data-ttu-id="85492-121">O endereço de email a ser usado quando enviar o email de confirmação.</span><span class="sxs-lookup"><span data-stu-id="85492-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="85492-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="85492-122">Select **Save**.</span></span>