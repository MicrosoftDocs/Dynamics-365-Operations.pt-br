---
title: Instrumentos de teste de gerenciamento de qualidade
description: Este tópico descreve como criar instrumentos de teste que possam ser usados para testes em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021723"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="5ace2-103">Instrumentos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="5ace2-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ace2-104">Este tópico descreve como criar instrumentos de teste que possam ser usados para testes em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5ace2-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="5ace2-105">Use a página **Instrumentos de teste** para definir e exibir detalhes sobre os dispositivos usados para executar testes em ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="5ace2-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="5ace2-106">Os instrumentos de teste são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5ace2-106">Test instruments are optional.</span></span> <span data-ttu-id="5ace2-107">No entanto, eles podem ajudar os trabalhadores de qualidade a saber qual dispositivo ou ferramenta devem usar para executar um teste específico.</span><span class="sxs-lookup"><span data-stu-id="5ace2-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="5ace2-108">Exemplo de instrumento de teste</span><span class="sxs-lookup"><span data-stu-id="5ace2-108">Test instrument example</span></span>

<span data-ttu-id="5ace2-109">Você está executando vários testes em componentes elétricos.</span><span class="sxs-lookup"><span data-stu-id="5ace2-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="5ace2-110">Alguns testes são para a saída de tensão dos componentes, um teste é para a temperatura e um teste é para o peso.</span><span class="sxs-lookup"><span data-stu-id="5ace2-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="5ace2-111">Diferentes ferramentas, dispositivos ou equipamentos são usados para executar cada teste.</span><span class="sxs-lookup"><span data-stu-id="5ace2-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="5ace2-112">Por exemplo, um voltímetro é usado para medir a tensão, um termômetro é usado para medir a temperatura e uma balança é usada para medir o peso.</span><span class="sxs-lookup"><span data-stu-id="5ace2-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="5ace2-113">Você pode configurar cada um desses dispositivos como um instrumento de teste e indicar a unidade de medida na qual os resultados do teste devem ser registrados.</span><span class="sxs-lookup"><span data-stu-id="5ace2-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="5ace2-114">Por exemplo, os resultados do voltímetro são registrados em volts, os resultados do termômetro são registrados em graus Fahrenheit ou graus Celsius e os resultados da balança são registrados em libras ou quilogramas.</span><span class="sxs-lookup"><span data-stu-id="5ace2-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="5ace2-115">Criar um instrumento de teste</span><span class="sxs-lookup"><span data-stu-id="5ace2-115">Create a test instrument</span></span>

1. <span data-ttu-id="5ace2-116">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Instrumentos de teste**.</span><span class="sxs-lookup"><span data-stu-id="5ace2-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="5ace2-117">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="5ace2-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5ace2-118">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="5ace2-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="5ace2-119">**Instrumento de teste** – Insira um nome ou uma ID exclusiva para o instrumento de teste.</span><span class="sxs-lookup"><span data-stu-id="5ace2-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="5ace2-120">**Descrição** – Insira uma descrição detalhada do instrumento de teste.</span><span class="sxs-lookup"><span data-stu-id="5ace2-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="5ace2-121">**Unidade** – Selecione a unidade na qual o instrumento mede os resultados.</span><span class="sxs-lookup"><span data-stu-id="5ace2-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="5ace2-122">O campo **Precisão** é definido automaticamente com base na unidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="5ace2-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="5ace2-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5ace2-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ace2-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5ace2-124">Additional resources</span></span>

- [<span data-ttu-id="5ace2-125">Teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="5ace2-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="5ace2-126">Grupos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="5ace2-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
