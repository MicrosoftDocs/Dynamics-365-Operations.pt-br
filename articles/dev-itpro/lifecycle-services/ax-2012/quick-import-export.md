---
title: "Utilizar importação/exportação rápida"
description: "A finalidade da Importação/Exportação Rápida é permitir que você realize a importação ou exportação em menos etapas."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4bb5bf73210abfc3fc06f7f291ae60fdf4298b71
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a><span data-ttu-id="f07fe-103">Execute a ferramenta de transferência de dados de teste (beta) para Dynamics AX (AX 2012)</span><span class="sxs-lookup"><span data-stu-id="f07fe-103">Run the Test Data Transfer Tool (beta) for Dynamics AX (AX 2012)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f07fe-104">A finalidade da Importação/Exportação Rápida é permitir que você realize a importação ou exportação em menos etapas.</span><span class="sxs-lookup"><span data-stu-id="f07fe-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="f07fe-105">Adicionamos o recurso Importação/Exportação Rápida para permitir que os usuários importem ou exportem trabalhos simples que desejam executar rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f07fe-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="f07fe-106">Idealmente, esse recurso é usado em cenários nos quais um arquivo se mapeia automaticamente ao sistema e o usuário não precisa passar pelo mapeamento avançado ou criar trabalhos repetidos de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="f07fe-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

- <span data-ttu-id="f07fe-107">Este recurso oferece suporte para trabalhar tanto com entidades fora-da-caixa, quanto personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f07fe-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
- <span data-ttu-id="f07fe-108">Você pode importar de arquivos, e se você estiver usando uma fonte de dados ODBC, você pode selecionar uma consulta a ser usada para definir sua importação.</span><span class="sxs-lookup"><span data-stu-id="f07fe-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
- <span data-ttu-id="f07fe-109">Você deve ter formatos de dados fonte previamente definidos para ambos AX e Arquivo, e saber onde eles estão localizados.</span><span class="sxs-lookup"><span data-stu-id="f07fe-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
- <span data-ttu-id="f07fe-110">Não é necessário criar um grupo de processamento para utilizar a importação/exportação rápida, ele será criado automaticamente pelo sistema durante a execução do trabalho de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="f07fe-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="f07fe-111">Você também pode escolher manter o histórico de dados importados pela importação/exportação rápida.</span><span class="sxs-lookup"><span data-stu-id="f07fe-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="f07fe-112">Observe que a Importação/Exportação Rápida presume que você esteja familiarizado com os conceitos de DIXF.</span><span class="sxs-lookup"><span data-stu-id="f07fe-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>




