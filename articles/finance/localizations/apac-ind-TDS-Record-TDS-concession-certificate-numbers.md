---
title: Registrar os números dos certificados de concessão de TDS
description: Este tópico explica como registrar os números de certificados de concessão do Imposto Deduzido na Origem (Tax Deducted at Source, TDS) que são emitidos para os fornecedores.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023016"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="23d78-103">Registrar os números dos certificados de concessão de TDS</span><span class="sxs-lookup"><span data-stu-id="23d78-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23d78-104">Este tópico explica como registrar os números de certificados de concessão do Imposto Deduzido na Origem (Tax Deducted at Source, TDS) que são emitidos para os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="23d78-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="23d78-105">Vá para **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Concessões de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="23d78-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="23d78-106">No campo **Tipo de imposto**, selecione **TDS** para registrar os certificados de concessão para o tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="23d78-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="23d78-107">Na guia **Visão geral**, selecione **Alt+N** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="23d78-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="23d78-108">[![Cabeçalho da nova linha](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="23d78-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="23d78-109">No campo **Código do imposto retido na fonte**, selecione o código de imposto TDS para o qual os certificados de concessão do fornecedor são emitidos.</span><span class="sxs-lookup"><span data-stu-id="23d78-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="23d78-110">O campo **Nome do código do imposto retido na fonte** mostra o nome do código do imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="23d78-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="23d78-111">Nos campos **De** e **Até**, defina o período de validade para o certificado de concessão que usa o código de imposto TDS para calcular o TDS para o fornecedor como uma concessão.</span><span class="sxs-lookup"><span data-stu-id="23d78-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="23d78-112">No campo **Comentários**, insira qualquer comentário.</span><span class="sxs-lookup"><span data-stu-id="23d78-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="23d78-113">No campo **Seção**, insira o código da seção legal sob o qual o certificado de concessão TDS está disponível.</span><span class="sxs-lookup"><span data-stu-id="23d78-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="23d78-114">Se o código de seção for 197, o valor "A" aparecerá na coluna "Motivo para não dedução/menor dedução" no Formulário 26Q e na coluna "Motivo para não dedução/menor dedução/extrapolação (se houver)" no Formulário 27Q.</span><span class="sxs-lookup"><span data-stu-id="23d78-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="23d78-115">Se o código de seção for 197A, o valor "B" aparecerá em ambos os locais.</span><span class="sxs-lookup"><span data-stu-id="23d78-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="23d78-116">Selecione a FastTab **Certificado** para registrar os números dos certificados de concessão TDS para os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="23d78-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="23d78-117">No campo **Conta de fornecedor**, selecione a conta do fornecedor para a qual o certificado de concessão TDS foi emitido.</span><span class="sxs-lookup"><span data-stu-id="23d78-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="23d78-118">Nos campos **De** e **Até**, defina o período de validade do certificado de concessão TDS.</span><span class="sxs-lookup"><span data-stu-id="23d78-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="23d78-119">O cálculo do TDS como uma concessão é baseado no período em que o certificado é criado para o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="23d78-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="23d78-120">No campo **Certificado**, insira o número do certificado de concessão TDS.</span><span class="sxs-lookup"><span data-stu-id="23d78-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="23d78-121">[![FastTab Certificado](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="23d78-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="23d78-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="23d78-122">Close the page.</span></span>
