---
title: Solucionar problemas do Conector de Pagamento do Dynamics 365 para Adyen
description: Este tópico fornece diretrizes de solução de problemas que podem ajudá-lo a obter suporte quando tiver problemas com o Conector de Pagamento do Microsoft Dynamics 365 para Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c779997d530d60f945bee19ee09bdabbff121fa6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801810"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="12386-103">Solucionar problemas do Conector de Pagamento do Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="12386-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12386-104">Este tópico fornece diretrizes de solução de problemas que podem ajudá-lo a obter suporte quando tiver problemas com o Conector de Pagamento do Microsoft Dynamics 365 para Adyen.</span><span class="sxs-lookup"><span data-stu-id="12386-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="12386-105">descrição</span><span class="sxs-lookup"><span data-stu-id="12386-105">Description</span></span>

<span data-ttu-id="12386-106">Você tem problemas com o Conector de Pagamento do Dynamics 365 para Adyen nas seguintes áreas e precisa de suporte da equipe da Adyen:</span><span class="sxs-lookup"><span data-stu-id="12386-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="12386-107">Configuração do PDV (Ponto de venda), Modern point of sale (MPOS), call center ou Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="12386-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="12386-108">O número de referência do Provedor de serviço de pagamento Adyen (PSP) (por exemplo, se tiver perguntas sobre as recusas, incluindo recusas de entrada de chave manual \[MKE\])</span><span class="sxs-lookup"><span data-stu-id="12386-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="12386-109">Tudo o que não estiver funcionando em ambientes de teste ou de comerciante dinâmicos</span><span class="sxs-lookup"><span data-stu-id="12386-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="12386-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="12386-110">Resolution</span></span>

<span data-ttu-id="12386-111">Use o modelo de email a seguir para iniciar o processo de suporte da equipe da Adyen.</span><span class="sxs-lookup"><span data-stu-id="12386-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="12386-112">Para acelerar a solução de problemas, verifique se o email contém todos os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="12386-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="12386-113">Campo</span><span class="sxs-lookup"><span data-stu-id="12386-113">Field</span></span>        | <span data-ttu-id="12386-114">Alíquota</span><span class="sxs-lookup"><span data-stu-id="12386-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="12386-115">Até</span><span class="sxs-lookup"><span data-stu-id="12386-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="12386-116">Cc</span><span class="sxs-lookup"><span data-stu-id="12386-116">Cc</span></span>           | |
| <span data-ttu-id="12386-117">Linha do assunto</span><span class="sxs-lookup"><span data-stu-id="12386-117">Subject line</span></span> | <span data-ttu-id="12386-118">Solicitação de suporte do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="12386-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="12386-119">Corpo</span><span class="sxs-lookup"><span data-stu-id="12386-119">Body</span></span>         | <p><span data-ttu-id="12386-120">Olá, Suporte,</span><span class="sxs-lookup"><span data-stu-id="12386-120">Hi Support,</span></span></p><p><span data-ttu-id="12386-121">Forneça suporte para o seguinte problema:</span><span class="sxs-lookup"><span data-stu-id="12386-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="12386-122">Conta de comerciante</span><span class="sxs-lookup"><span data-stu-id="12386-122">Merchant account</span></span></li><li><span data-ttu-id="12386-123">Ambiente (Teste/Produção)</span><span class="sxs-lookup"><span data-stu-id="12386-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="12386-124">Canal (PDV/call center/Comércio eletrônico do Commerce)</span><span class="sxs-lookup"><span data-stu-id="12386-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="12386-125">O número de referência PSP, se o problema envolvido em uma transação específica (você pode encontrar o número de referência PSP no recibo, na Área de Cliente da Adyen ou no menu transações no terminal de PDV).</span><span class="sxs-lookup"><span data-stu-id="12386-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="12386-126">Captura de tela ou foto da mensagem de erro, se aplicável</span><span class="sxs-lookup"><span data-stu-id="12386-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="12386-127">Logs do Visualizador de Eventos (no formato .txt)</span><span class="sxs-lookup"><span data-stu-id="12386-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="12386-128">Descrição da questão e das etapas de solução de problemas que você tentou</span><span class="sxs-lookup"><span data-stu-id="12386-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="12386-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="12386-129">Additional resources</span></span>

[<span data-ttu-id="12386-130">Aceitar pagamentos com o conector da Adyen para Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="12386-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="12386-131">Conector de Pagamento do Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="12386-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="12386-132">Configurar o conector de pagamento da Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="12386-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
