---
title: Configuração de transferência de crédito ISO20022 de importação
description: Este procedimento mostra como importar uma configuração de relatório eletrônico de pagamento de fornecedor.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee7e69611d31d2577ebafdfc059b0936aef0520b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174761"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="02a13-103">Configuração de transferência de crédito ISO20022 de importação</span><span class="sxs-lookup"><span data-stu-id="02a13-103">Import ISO20022 credit transfer configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02a13-104">Este procedimento mostra como importar uma configuração de relatório eletrônico de pagamento de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="02a13-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="02a13-105">O formato alemão de transferência de crédito ISO 20022 é usado como exemplo.</span><span class="sxs-lookup"><span data-stu-id="02a13-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="02a13-106">Este procedimento pode ser usado para outros formatos de relatório eletrônico disponíveis.</span><span class="sxs-lookup"><span data-stu-id="02a13-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="02a13-107">Esta tarefa foi criada usando a empresa de dados de demonstração DEMF, mas você pode usar qualquer empresa de dados de demonstração para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="02a13-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="02a13-108">Esta é a primeira de cinco tarefas que, juntas, ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="02a13-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="02a13-109">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="02a13-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="02a13-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="02a13-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="02a13-111">Na lista de provedores de configuração disponíveis, selecione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="02a13-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="02a13-112">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="02a13-112">Click Set active.</span></span>
4. <span data-ttu-id="02a13-113">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="02a13-113">Click Repositories.</span></span>
5. <span data-ttu-id="02a13-114">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="02a13-114">Click Open.</span></span>
6. <span data-ttu-id="02a13-115">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="02a13-115">Click Show filters.</span></span>
7. <span data-ttu-id="02a13-116">Aplicar os seguintes filtros: inserir um valor de filtro de "Transferência de Crédito ISO20022 (DE)", no campo "Nome da configuração" usando o operador de filtro "começa com"</span><span class="sxs-lookup"><span data-stu-id="02a13-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="02a13-117">Como alternativa, você pode localizar a configuração na lista, selecioná-la e movê-la para a tarefa de importação.</span><span class="sxs-lookup"><span data-stu-id="02a13-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="02a13-118">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="02a13-118">Click Import.</span></span>
    * <span data-ttu-id="02a13-119">Se o botão Importar não estiver disponível, significa que a configuração já foi importada.</span><span class="sxs-lookup"><span data-stu-id="02a13-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="02a13-120">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="02a13-120">Click Yes.</span></span>

