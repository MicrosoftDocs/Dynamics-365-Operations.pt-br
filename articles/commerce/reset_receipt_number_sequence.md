---
title: Redefinir números de recibo
description: Este tópico descreve como redefinir os números de recibo usados para várias ações em uma data desejada (por exemplo, o ano fiscal ou o ano civil).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: fc719348f94ff4a1fb7b4ac96f6f617872c9af92
ms.sourcegitcommit: 437170338c49b61bba58f822f8494095ea1308c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2020
ms.locfileid: "3123937"
---
# <a name="reset-receipt-numbers"></a><span data-ttu-id="e1cdb-103">Redefinir números de recibo</span><span class="sxs-lookup"><span data-stu-id="e1cdb-103">Reset receipt numbers</span></span> 

[!include [banner](includes/banner.md)]


<span data-ttu-id="e1cdb-104">Os varejistas geram números de recibo para várias ações na loja, como transações cash and carry, transações de devolução, ordens de cliente, cotações e pagamentos.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-104">Retailers generate receipt numbers for various actions in the store, such as cash and carry transactions, return transactions, customer orders, quotations, and payments.</span></span> <span data-ttu-id="e1cdb-105">Embora os varejistas definam seus próprios formatos de recibo, alguns países ou regiões têm regulamentos que colocam restrições nesses formatos de recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-105">Although retailers define their own receipt formats, some countries or regions have regulations that put restrictions on these receipt formats.</span></span> <span data-ttu-id="e1cdb-106">Por exemplo, esses regulamentos podem limitar o número de caracteres no recebimento, exigir números de recibo consecutivos, restringir alguns caracteres especiais ou exigir a redefinição de números de recibo no início do ano.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-106">For example, these regulations might limit the number of characters on the receipt, require consecutive receipt numbers, restrict some special characters, or require a reset of receipt numbers at the beginning of the year.</span></span> <span data-ttu-id="e1cdb-107">O Microsoft Dynamics 365 Commerce torna o processo de gerenciar números de recibo muito flexível, para ajudar os varejistas a cumprir requisitos de regulamentação.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-107">Microsoft Dynamics 365 Commerce makes the process of managing receipt numbers very flexible, to help retailers meet regulatory requirements.</span></span> <span data-ttu-id="e1cdb-108">Este tópico explica como usar a funcionalidade para redefinir números de recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-108">This topic explains how to use the functionality for resetting receipt numbers.</span></span>

<span data-ttu-id="e1cdb-109">No Commerce, os formatos de recibo podem ser alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-109">In Commerce, receipt formats can be alphanumeric.</span></span> <span data-ttu-id="e1cdb-110">Você pode colocar conteúdo estático e conteúdo dinâmico neles.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-110">You can put both static content and dynamic content in them.</span></span> <span data-ttu-id="e1cdb-111">O conteúdo estático inclui caracteres alfabéticos, números e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-111">Static content includes alphabetic character, numbers, and special characters.</span></span> <span data-ttu-id="e1cdb-112">O conteúdo dinâmico inclui um ou mais caracteres que representam informações como o número da loja, o número do terminal, a data, o mês, o ano e as sequências numéricas que são incrementadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-112">Dynamic content includes one or more characters that represent information such as the store number, terminal number, date, month, year, and number sequences that are automatically incremented.</span></span> <span data-ttu-id="e1cdb-113">Os formatos são definidos na seção **Numeração do recibo** do perfil de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-113">The formats are defined in the **Receipt numbering** section of the functionality profile.</span></span> <span data-ttu-id="e1cdb-114">A tabela a seguir descreve os caracteres que representam o conteúdo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-114">The following table describes the characters that represent the dynamic content.</span></span>

| <span data-ttu-id="e1cdb-115">Caracteres</span><span class="sxs-lookup"><span data-stu-id="e1cdb-115">Characters</span></span> | <span data-ttu-id="e1cdb-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1cdb-116">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="e1cdb-117">S</span><span class="sxs-lookup"><span data-stu-id="e1cdb-117">S</span></span>          | <span data-ttu-id="e1cdb-118">O caractere **S** é usado para o número da loja.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-118">The character **S** is used for the store number.</span></span> <span data-ttu-id="e1cdb-119">Por exemplo, se uma loja for numerada HOUSTON1, o formato **SSS** mostrará "ON1" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-119">For example, if a store is numbered HOUSTON1, the format **SSS** shows "ON1" on the receipt.</span></span> <span data-ttu-id="e1cdb-120">O formato **SSSSS** mostra "STON1" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-120">The format **SSSSS** shows "STON1" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-121">T</span><span class="sxs-lookup"><span data-stu-id="e1cdb-121">T</span></span>          | <span data-ttu-id="e1cdb-122">O caractere **T** é usado para o número do terminal.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-122">The character **T** is used for the terminal number.</span></span> <span data-ttu-id="e1cdb-123">Por exemplo, se um terminal for numerado 0001, o formato **TTTT** mostrará "0001" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-123">For example, if a terminal is numbered 0001, the format **TTTT** shows "0001" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-124">C</span><span class="sxs-lookup"><span data-stu-id="e1cdb-124">C</span></span>          | <span data-ttu-id="e1cdb-125">O caractere **C** é usado para o número da ID da equipe.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-125">The character **C** is used for the staff ID number.</span></span> <span data-ttu-id="e1cdb-126">Por exemplo, se um membro da equipe tiver uma ID de 000160, o formato **CCCC** mostrará "0160" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-126">For example, if a staff member has an ID of 000160, the format **CCCC** shows "0160" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-127">ddd</span><span class="sxs-lookup"><span data-stu-id="e1cdb-127">ddd</span></span>        | <span data-ttu-id="e1cdb-128">Os caracteres **ddd** correspondem ao dia do ano, de 1 a 366.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-128">The characters **ddd** correspond to the day of the year, from 1 through 366.</span></span> <span data-ttu-id="e1cdb-129">Por exemplo, em 15 de Janeiro, o formato **ddd** mostra "015" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-129">For example, on January 15, the format **ddd** shows "015" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-130">MM</span><span class="sxs-lookup"><span data-stu-id="e1cdb-130">MM</span></span>         | <span data-ttu-id="e1cdb-131">Os caracteres **MM** são usados para o mês de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-131">The characters **MM** are used for the two-digit month.</span></span> <span data-ttu-id="e1cdb-132">Por exemplo, em janeiro, o formato **MM** mostra "01" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-132">For example, in January, the format **MM** show "01" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-133">DD</span><span class="sxs-lookup"><span data-stu-id="e1cdb-133">DD</span></span>         | <span data-ttu-id="e1cdb-134">Os caracteres **DD** são usados para o dia do mês de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-134">The characters **DD** are used for the two-digit day of the month.</span></span> <span data-ttu-id="e1cdb-135">Por exemplo, em 15 de janeiro, o formato **DD** mostra "15" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-135">For example, on January 15, the format **DD** shows "15" on the receipt.</span></span> |
| <span data-ttu-id="e1cdb-136">AA</span><span class="sxs-lookup"><span data-stu-id="e1cdb-136">YY</span></span>         | <span data-ttu-id="e1cdb-137">Os caracteres **AA** são usados para o ano de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-137">The characters **YY** are used for the two-digit year.</span></span> <span data-ttu-id="e1cdb-138">Por exemplo, em qualquer mês durante o ano de 2020, o formato **AA** mostra "20" no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-138">For example, in any month during the year 2020, the format **YY** shows "20" on the receipt.</span></span> |
| \#         | <span data-ttu-id="e1cdb-139">Um sinal numérico (**\#**) é usado na numeração sequencial.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-139">A number sign (**\#**) is used for sequential numbering.</span></span> <span data-ttu-id="e1cdb-140">Por exemplo, o formato **####** mostra "0001", "0002", "0003" e assim por diante no recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-140">For example, the format **####** shows "0001," "0002," "0003," and so on, on the receipt.</span></span> |

<span data-ttu-id="e1cdb-141">Você pode redefinir a numeração sequencial do recibo em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-141">You can reset the sequential numbering of the receipt on a specific date.</span></span> <span data-ttu-id="e1cdb-142">Em seguida, para a primeira transação que ocorre após 12:00 AM na data de redefinição selecionada, o sistema redefine a sequência numérica do recibo como 1.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-142">Then, for the first transaction that occurs after 12:00 AM on the selected reset date, the system resets the receipt's number sequence to 1.</span></span> <span data-ttu-id="e1cdb-143">Você também pode especificar se a redefinição ocorre apenas uma vez ou se ela se repete a cada ano.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-143">You can also specify whether the reset occurs only one time, or whether it recurs every year.</span></span> <span data-ttu-id="e1cdb-144">Se a recorrência anual for especificada, a redefinição ocorrerá automaticamente a cada ano até que o varejista decida pará-la.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-144">If yearly recurrence is specified, the reset automatically occurs every year until the retailer chooses to stop it.</span></span> 

<span data-ttu-id="e1cdb-145">Para ativar a redefinição, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-145">To turn on the reset, follow these steps.</span></span>

1. <span data-ttu-id="e1cdb-146">Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="e1cdb-147">Na Guia Rápida **Numeração de recibo**, selecione **Redefinir data de redefinição de número**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-147">On the **Receipt numbering** FastTab, select **Reset number reset date**.</span></span>
1. <span data-ttu-id="e1cdb-148">Na caixa de diálogo suspensa, no campo **Redefinir data**, selecione uma data futura em que a redefinição deverá ocorrer.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-148">In the drop-down dialog box, in the **Reset date** field, select a future date when the reset should occur.</span></span>
1. <span data-ttu-id="e1cdb-149">No campo **Redefinir tipo de recibo**, selecione **Apenas uma vez** ou **Anual**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-149">In the **Reset receipt type** field, select **One time only** or **Yearly**.</span></span>
1. <span data-ttu-id="e1cdb-150">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-150">Select **OK**.</span></span>

<span data-ttu-id="e1cdb-151">![Selecionando uma data de redefinição de recibo](media/Enable_receipt_reset.png "Seleção de uma data de redefinição de recibo")</span><span class="sxs-lookup"><span data-stu-id="e1cdb-151">![Selecting a receipt reset date](media/Enable_receipt_reset.png "Selecting a receipt reset date")</span></span>

<span data-ttu-id="e1cdb-152">Depois que você seleciona uma data, ela aparece na coluna **Próxima data de redefinição do número do recibo**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-152">After you select a date, it appears in the **Next receipt number reset date** column.</span></span> <span data-ttu-id="e1cdb-153">A data de redefinição é aplicável a todos os tipos de transação de recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-153">The reset date is applicable to all receipt transaction types.</span></span> <span data-ttu-id="e1cdb-154">Portanto, a sequência numérica do recibo será redefinida para todos os tipos de recibo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-154">Therefore, the receipt number sequence will be reset for all receipt types.</span></span>

<span data-ttu-id="e1cdb-155">Quando a data de redefinição chega, o número do recibo é redefinido para a primeira transação de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-155">When the reset date arrives, the receipt number is reset for the first transaction of each type.</span></span> <span data-ttu-id="e1cdb-156">Além disso, no perfil de funcionalidade, a data de redefinição é movida da coluna **Próxima data de redefinição do número do recibo** para a coluna **Data de redefinição de número de recibo atual**.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-156">In addition, in the functionality profile, the reset date is moved from the **Next receipt number reset date** column to the **Current receipt number reset date** column.</span></span> <span data-ttu-id="e1cdb-157">Essa alteração indica que, se um registro não for usado na data de redefinição, o número do recibo será redefinido na próxima vez que esse registro *for* usado.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-157">This change indicates that if a register isn't used on the reset date, the receipt number will be reset the next time that the register *is* used.</span></span> <span data-ttu-id="e1cdb-158">Por exemplo, em 3 de dezembro de 2019, você seleciona **1º de janeiro de 2020** como a data de redefinição.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-158">For example, on December 3, 2019, you select **January 1, 2020**, as the reset date.</span></span> <span data-ttu-id="e1cdb-159">Em 1º de janeiro, quando os registradores fazem a primeira transação, o número do recibo é redefinido.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-159">On January 1, when the registers make their first transaction, the receipt number are reset.</span></span> <span data-ttu-id="e1cdb-160">No entanto, um registro não é usado em dezembro e janeiro, mas começa a ser usada em fevereiro.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-160">However, one register isn't used at all during December and January, but then starts to be used in February.</span></span> <span data-ttu-id="e1cdb-161">Nesse caso, como uma ação de redefinição foi definida, o número do recibo desse registro será redefinido quando o registro fizer a primeira transação em fevereiro.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-161">In this case, because a reset action was defined, the receipt number for that register will be reset when the register makes its first transaction in February.</span></span>

<span data-ttu-id="e1cdb-162">Você pode usar a funcionalidade **Limpar data de redefinição** para limpar datas de redefinição futuras.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-162">You can use the **Clear reset date** functionality to clear future reset dates.</span></span> <span data-ttu-id="e1cdb-163">No entanto, se a data de redefinição tiver ocorrido no passado, ela não poderá ser desfeita.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-163">However, if the reset date occurred in the past, it can't be undone.</span></span> <span data-ttu-id="e1cdb-164">Portanto, a redefinição ainda ocorrerá para todos os registros em que a redefinição ainda não ocorreu.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-164">Therefore, the reset will still occur for all registers where the reset hasn't yet occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="e1cdb-165">Dependendo da data de redefinição selecionada e do formato de recibo, você pode ter números de recibo duplicados.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-165">Depending on the reset date that you select, and the receipt format, you might have duplicate receipt numbers.</span></span> <span data-ttu-id="e1cdb-166">Embora o sistema do ponto de venda (PDV) possa lidar com essas situações, elas aumentam o tempo exigido para processar devoluções, pois parceiros de vendas devem selecionar entre os recibos duplicados.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-166">Although the point of sale (POS) system can handle these situations, they increase the amount of time that is required to process returns, because sales associates must select among the duplicate receipts.</span></span> <span data-ttu-id="e1cdb-167">Outras complicações relativas à limpeza de dados poderiam ocorrer se os recibos duplicados não fossem uma consequência planejada.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-167">Other complications that are related to data cleanup can occur if the duplicate receipts weren't a planned consequence.</span></span> <span data-ttu-id="e1cdb-168">Portanto, é recomendável usar caracteres de data dinâmica (por exemplo **ddd**, **MM**, **DD** e **AA**) para ajudar a evitar números de recebo duplicados após uma redefinição.</span><span class="sxs-lookup"><span data-stu-id="e1cdb-168">Therefore, we recommend that you use dynamic date characters (for example, **ddd**, **MM**, **DD**, and **YY**) to help prevent duplicate receipt numbers after a reset.</span></span>