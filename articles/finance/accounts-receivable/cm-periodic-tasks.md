---
title: Tarefas periódicas de gerenciamento de crédito
description: Este tópico descreve as tarefas periódicas que são necessárias no processo de gerenciamento dos limites de crédito de clientes.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b41b87cd3e2e80b87318c5c771d45a4d0e5d4b85
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971694"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="bf278-103">Tarefas periódicas de gerenciamento de crédito</span><span class="sxs-lookup"><span data-stu-id="bf278-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf278-104">Este tópico descreve as tarefas periódicas que são necessárias no processo de gerenciamento dos limites de crédito de clientes.</span><span class="sxs-lookup"><span data-stu-id="bf278-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="bf278-105">Atualizar pontuações de risco</span><span class="sxs-lookup"><span data-stu-id="bf278-105">Update risk scores</span></span>

<span data-ttu-id="bf278-106">À medida que as empresas evoluem e as circunstâncias mudam, os riscos de crédito de um determinado cliente também podem mudar.</span><span class="sxs-lookup"><span data-stu-id="bf278-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="bf278-107">Para ajudar a manter os limites de crédito adequados para seus clientes, periodicamente você deve revisar os critérios de cada pontuação de risco e atualizar as pontuações de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="bf278-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="bf278-108">É possível atualizar as pontuações a seguir usando a página **Atualizar pontuações de risco** (**Crédito e cobranças \> Tarefas periódicas \> Gerenciamento de crédito \> Atualizar pontuações de risco**).</span><span class="sxs-lookup"><span data-stu-id="bf278-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="bf278-109">Todos os cálculos definidos pelo usuário também são processados.</span><span class="sxs-lookup"><span data-stu-id="bf278-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="bf278-110">**Média de dias de pagamento** – Esta pontuação é o número médio de dias que um cliente leva para pagar as faturas.</span><span class="sxs-lookup"><span data-stu-id="bf278-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="bf278-111">**Cliente desde** – Esta pontuação representa o número de anos que um cliente é cliente da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bf278-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="bf278-112">**Na empresa desde** – Esta pontuação é o número de anos durante os quais o cliente está na empresa.</span><span class="sxs-lookup"><span data-stu-id="bf278-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="bf278-113">Ela usa o valor do campo **Início do negócio** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="bf278-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="bf278-114">**Vendas diárias pendentes** – Esta pontuação se baseia no saldo de contas a receber, na receita de vendas e no número de dias do período de 12 meses anterior.</span><span class="sxs-lookup"><span data-stu-id="bf278-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="bf278-115">**Saldo médio** – Esta pontuação se baseia no saldo de contas a receber do período de 12 meses anterior.</span><span class="sxs-lookup"><span data-stu-id="bf278-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="bf278-116">**Grupo de gerenciamento de crédito**, **Status da conta** e **País** – Estas pontuações usam informações do cliente.</span><span class="sxs-lookup"><span data-stu-id="bf278-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="bf278-117">Atualizar estatísticas de saldo de cliente</span><span class="sxs-lookup"><span data-stu-id="bf278-117">Update customer balance statistics</span></span>

<span data-ttu-id="bf278-118">Você pode executar o processo **Atualizar estatísticas de saldo de cliente** para atualizar o cálculo de estatísticas de saldo mostrado na página **Consulta de estatísticas de saldo**.</span><span class="sxs-lookup"><span data-stu-id="bf278-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="bf278-119">Essas informações são usadas para calcular as pontuações de risco e os valores que são mostrados nos Quadro de Fatos de estatísticas da página **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="bf278-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="bf278-120">Quando você executa o processo, ele atualiza as estatísticas de saldo de um único cliente.</span><span class="sxs-lookup"><span data-stu-id="bf278-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="bf278-121">Para configurar um trabalho em lotes para executar o processo para vários clientes, você pode usar a página **Calcular estatísticas de saldo** (**Gerenciamento de crédito \> Tarefas periódicas \> Calcular estatísticas de saldo**).</span><span class="sxs-lookup"><span data-stu-id="bf278-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>
