---
title: Configuração do débito direto ISO20022 de importação
description: Este procedimento demonstra como importar uma configuração de relatório eletrônico de pagamento de cliente.
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
ms.openlocfilehash: 7eee00021f49ac0110d7bde07faba8095348e1b4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185741"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="851d4-103">Configuração do débito direto ISO20022 de importação</span><span class="sxs-lookup"><span data-stu-id="851d4-103">Import ISO20022 direct debit configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="851d4-104">Este procedimento demonstra como importar uma configuração de relatório eletrônico de pagamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="851d4-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="851d4-105">Este procedimento usa o formato de débito direto ISO 20022 como exemplo.</span><span class="sxs-lookup"><span data-stu-id="851d4-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="851d4-106">Este procedimento foi criado usando a empresa de dados de demonstração DEMF, mas você pode usar qualquer empresa de dados de demonstração para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="851d4-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="851d4-107">Este é o primeiro dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="851d4-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="851d4-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="851d4-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="851d4-109">Na lista de provedores de configuração disponíveis, selecione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="851d4-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="851d4-110">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="851d4-110">Click Set active.</span></span>
4. <span data-ttu-id="851d4-111">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="851d4-111">Click Repositories.</span></span>
5. <span data-ttu-id="851d4-112">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="851d4-112">Click Open.</span></span>
6. <span data-ttu-id="851d4-113">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="851d4-113">Click Show filters.</span></span>
7. <span data-ttu-id="851d4-114">Aplicar os seguintes filtros: inserir um valor de filtro de "Débito direto ISO20022 (DE)", no campo "Nome da configuração" usando o operador de filtro "começa com"</span><span class="sxs-lookup"><span data-stu-id="851d4-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="851d4-115">Opcionalmente, você pode localizar a configuração na lista, selecioná-la e ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="851d4-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="851d4-116">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="851d4-116">Click Import.</span></span>
    * <span data-ttu-id="851d4-117">Se o botão Importar não estiver disponível, significa que a configuração já foi importada.</span><span class="sxs-lookup"><span data-stu-id="851d4-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="851d4-118">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="851d4-118">Click Yes.</span></span>
