---
title: Ordens de serviço criadas automaticamente
description: Você pode gerar ordens de serviço com base em um contrato de serviço para o período de vigência do contrato de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53369ef2b7ff93ae4f0523accbc31cc88575a383
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010663"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="dcdaf-103">Ordens de serviço criadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="dcdaf-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="dcdaf-104">Você pode gerar ordens de serviço com base em um contrato de serviço para o período de vigência do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="dcdaf-105">As ordens de serviço geradas a partir de um contrato de serviço são todas anexadas ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="dcdaf-106">As ordens de serviço são geradas automaticamente a partir destas configurações:</span><span class="sxs-lookup"><span data-stu-id="dcdaf-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="dcdaf-107">O intervalo do contrato de serviço que é definido nas linhas do contrato.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="dcdaf-108">Esse intervalo indica a frequência com que são criadas linhas de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="dcdaf-109">Para obter mais informações, consulte [Intervalos de serviço](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="dcdaf-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="dcdaf-110">O período especificado para definir o período de serviço nos campos **Data de início** e **Data de término** no formulário **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="dcdaf-111">Para obter mais informações, consulte [Criar ordens de serviço automaticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="dcdaf-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="dcdaf-112">A opção **Combinar ordens de serviço** no cabeçalho do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="dcdaf-113">Essa opção define se as linhas de ordem de serviço geradas a partir de um contrato de serviço incluem ordens de serviço de acordo com funcionário, tarefa de serviço, objeto de serviço ou contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="dcdaf-114">Para obter mais informações, consulte [Combinar ordens de serviço](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="dcdaf-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="dcdaf-115">A opção **Janela de tempo** na linha de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="dcdaf-116">A janela de tempo define até que ponto uma linha de ordem de serviço pode se mover em relação à data de cálculo.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="dcdaf-117">Para obter mais informações, consulte [Janelas de horas](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="dcdaf-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="dcdaf-118">Se o dia especificado para uma ordem de serviço não estiver aberto no calendário selecionado no formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>, uma mensagem indicará que há um conflito de calendário.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="dcdaf-119">Você pode ignorar essa mensagem com segurança; a ordem de serviço será criada mesmo que o dia esteja fechado no calendário.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="dcdaf-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="dcdaf-120">Example 1</span></span>

<span data-ttu-id="dcdaf-121">O contrato de serviço vigora desde de 1º de janeiro de 2012 até 31 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="dcdaf-122">Se o período de serviço especificado no formulário **Criar ordens de serviço** é de 1º de novembro de 2012 até 1º de fevereiro de 2013, ordens de serviço serão criadas desde 1º de novembro de 2012 até 31 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="dcdaf-123">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="dcdaf-123">Example 2</span></span>

<span data-ttu-id="dcdaf-124">O contrato de serviço vigora desde de 1º de janeiro de 2012 até 31 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="dcdaf-125">Duas linhas de contrato de serviço são anexadas ao contrato.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="dcdaf-126">A primeira linha de contrato de serviço tem uma data inicial de 2 de janeiro de 2012 e final de 1º de março de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="dcdaf-127">A segunda linha de contrato de serviço tem uma data inicial de 1º de abril de 2012 e final de 31 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="dcdaf-128">Especifique um período no formulário **Criar ordens de serviço** que é de 1º de outubro de 2012 a 31 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="dcdaf-129">Portanto, as ordens de serviço serão geradas somente para a segunda linha de contrato de serviço porque as datas de início e fim da primeira linha são anteriores ao período especificado para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  


