---
title: Analisar documentos de entrada no formato JSON
description: Este tópico explica como configurar formatos de relatórios eletrônicos (ER) para analisar documentos de entrada no formato de Notação de Objeto de JavaScript (JSON).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 8be4e225507a18a92d642ff0f3a6ca3d0ff68564
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772526"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="ded0c-103">Analisar documentos de entrada no formato JSON</span><span class="sxs-lookup"><span data-stu-id="ded0c-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ded0c-104">Você pode criar formatos de relatórios eletrônicos (ER) para analisar documentos eletrônicos de entrada que representam dados em um formato do texto com base em JavaScript (ou seja, arquivos no formato de Notação de Objeto de JavaScript \[JSON\]).</span><span class="sxs-lookup"><span data-stu-id="ded0c-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="ded0c-105">Para saber mais sobre este recurso, baixe arquivos na tabela a seguir e execute o ER Criar uma configuração de formato para importar dados de uma guia externa de tarefas de arquivo JSON.</span><span class="sxs-lookup"><span data-stu-id="ded0c-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="ded0c-106">Este guia de tarefas mostra como um formato ER pode ser usado para analisar um arquivo de entrada JSON para atualizar dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ded0c-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="ded0c-107">Cargo</span><span class="sxs-lookup"><span data-stu-id="ded0c-107">Title</span></span>                                  | <span data-ttu-id="ded0c-108">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="ded0c-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="ded0c-109">Configuração de formato ER</span><span class="sxs-lookup"><span data-stu-id="ded0c-109">ER format configuration</span></span>                | [<span data-ttu-id="ded0c-110">Formatar para importar trans_JSON.xml de fornecedores</span><span class="sxs-lookup"><span data-stu-id="ded0c-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="ded0c-111">Amostra de arquivo de entrada no formato .csv</span><span class="sxs-lookup"><span data-stu-id="ded0c-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="ded0c-112">1099entries_JSON.txt</span><span class="sxs-lookup"><span data-stu-id="ded0c-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="ded0c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ded0c-113">Requirements</span></span>

<span data-ttu-id="ded0c-114">Antes de concluir o ER Criar uma configuração de formato para importar dados de uma guia externa de tarefas de arquivo JSON, é necessário atender ao seguinte requisito:</span><span class="sxs-lookup"><span data-stu-id="ded0c-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="ded0c-115">Elementos pai no arquivo JSON só podem ser elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="ded0c-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="ded0c-116">Elementos aninhados para um objeto devem ser elementos de propriedade, de forma que uma estrutura JSON válida seja criada.</span><span class="sxs-lookup"><span data-stu-id="ded0c-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="ded0c-117">Matrizes JSON só podem ser elementos aninhados dos elementos de propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="ded0c-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="ded0c-118">Matrizes JSON só podem conter objetos JSON.</span><span class="sxs-lookup"><span data-stu-id="ded0c-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="ded0c-119">Elas não podem conter cadeias de caracteres diretas/valores numéricos e matrizes aninhadas.</span><span class="sxs-lookup"><span data-stu-id="ded0c-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="ded0c-120">Os elementos nessas matrizes serão analisados em ordem, como são especificados no formato.</span><span class="sxs-lookup"><span data-stu-id="ded0c-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="ded0c-121">As configurações de multiplicidade em cada objeto JSON serão consideradas.</span><span class="sxs-lookup"><span data-stu-id="ded0c-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="ded0c-122">Além disso, você deverá concluir o guia de tarefas [ER Criar as configurações necessárias para importar dados de um arquivo externo](tasks/er-required-configurations-import-data.md) se ele ainda não tiver sido concluído.</span><span class="sxs-lookup"><span data-stu-id="ded0c-122">Additionally, you must complete the [ER Create required configurations to import data from an external file](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="ded0c-123">Baixe o arquivo a seguir para concluir o guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ded0c-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="ded0c-124">Cargo</span><span class="sxs-lookup"><span data-stu-id="ded0c-124">Title</span></span>                  | <span data-ttu-id="ded0c-125">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="ded0c-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="ded0c-126">Configuração de modelo ER</span><span class="sxs-lookup"><span data-stu-id="ded0c-126">ER model configuration</span></span> | [<span data-ttu-id="ded0c-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="ded0c-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
