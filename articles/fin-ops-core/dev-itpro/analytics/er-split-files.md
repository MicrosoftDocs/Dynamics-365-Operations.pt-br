---
title: Dividir os arquivos XML gerados com base no tamanho do arquivo e na quantidade de conteúdo
description: Este tópico fornece informações sobre como dividir os arquivos gerados com base tamanho do arquivo e na quantidade de itens de conteúdo
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
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
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 804878150f035adc051e89ec6be44457ad58e87e
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771182"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a><span data-ttu-id="db914-103">Dividir os arquivos XML gerados com base no tamanho do arquivo e na quantidade de conteúdo</span><span class="sxs-lookup"><span data-stu-id="db914-103">Split generated XML files based on file size and content quantity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="db914-104">Você pode criar os formatos de relatórios eletrônicos (ER) para gerar documentos de saída no formato XML.</span><span class="sxs-lookup"><span data-stu-id="db914-104">You can design Electronic reporting (ER) formats to generate outgoing documents in XML format.</span></span> <span data-ttu-id="db914-105">Às vezes, esses documentos podem ser aceitos somente quando atendem a critérios específicos, como um tamanho máximo do arquivo ou número máximo de alguns nós de XML.</span><span class="sxs-lookup"><span data-stu-id="db914-105">Sometimes, those documents can be accepted only when they meet specific criteria, such a maximum file size or a maximum number of some XML nodes.</span></span> <span data-ttu-id="db914-106">Você pode criar formatos de ER para gerar documentos eletrônicos que satisfazem aos requisitos que os destinatários desses documentos especificam.</span><span class="sxs-lookup"><span data-stu-id="db914-106">You can design ER formats to generate electronic documents that satisfy the requirements that the recipients of those documents specify.</span></span>

- <span data-ttu-id="db914-107">Para o elemento de formato de arquivo, você poderá definir um limite de tamanho de arquivo como uma expressão de ER.</span><span class="sxs-lookup"><span data-stu-id="db914-107">For the FILE format element, you can define a limit on the file size as an ER expression.</span></span> <span data-ttu-id="db914-108">Se o limite definido for excedido quando um relatório de ER for gerado, o ER termina a criação do arquivo atual e, em seguida, move-se para criar o próximo arquivo.</span><span class="sxs-lookup"><span data-stu-id="db914-108">If the defined limit is exceeded when an ER report is generated, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="db914-109">Para qualquer formato de elemento XML, você pode definir um limite sobre o número de elementos como uma expressão de ER.</span><span class="sxs-lookup"><span data-stu-id="db914-109">For any XML ELEMENT format, you can define a limit on the number of elements as an ER expression.</span></span> <span data-ttu-id="db914-110">Se o número de nós de XML no arquivo que foi gerado exceder o limite definido quando um relatório de ER for executado, o ER finaliza a criação do arquivo atual e move-se para criar o próximo arquivo.</span><span class="sxs-lookup"><span data-stu-id="db914-110">If the number of XML nodes in the file that is generated exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="db914-111">Para qualquer elemento de formato de sequência de XML, você pode definir um limite sobre o número de elementos filhos como uma expressão de ER.</span><span class="sxs-lookup"><span data-stu-id="db914-111">For any XML SEQUENCE format element, you can define a limit on the number of child elements as an ER expression.</span></span> <span data-ttu-id="db914-112">Se o número de nós de XML aninhados do elemento do formato no arquivo gerado exceder o limite definido quando um relatório de ER for executado, o ER finaliza a criação do arquivo atual e move-se para criar o próximo arquivo.</span><span class="sxs-lookup"><span data-stu-id="db914-112">If the number of nested XML nodes of the format element in the generated file exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="db914-113">Você pode marcar qualquer formato de elemento XML como sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="db914-113">You can mark any XML ELEMENT format element as non-breakable.</span></span> <span data-ttu-id="db914-114">Assim, você pode manter itens aninhados dos XML gerados no elemento de formato em um único arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="db914-114">In this way, you can keep the nested items of XML nodes that are generated under the format element in a single generated file.</span></span>

<span data-ttu-id="db914-115">Além de usar os elementos de formato do Elemento XML e da Sequência de XML para adicionar nós XML ao arquivo gerado, você pode usar o elemento de formato XML de RAW.</span><span class="sxs-lookup"><span data-stu-id="db914-115">In addition to using the XML ELEMENT and XML SEQUENCE format elements to add XML nodes to the generated file, you can use the RAW XML format element.</span></span> <span data-ttu-id="db914-116">Porém, os nós adicionados usando o elemento de formato XML bruto não são considerados quando o número de nós é calculado para avaliar os limites sobre o número de elementos.</span><span class="sxs-lookup"><span data-stu-id="db914-116">However, nodes that you add by using the RAW XML format element aren't considered when the number of nodes is calculated to evaluate the limits on the number of elements.</span></span>

<span data-ttu-id="db914-117">Se você configurou destinos de arquivo para um elemento de formato de arquivo que foi configurado para dividir a saída gerada, sempre que os limites específicos forem excedidos, cada parte da saída gerada será enviada para o destino de arquivo configurado como um arquivo individual.</span><span class="sxs-lookup"><span data-stu-id="db914-117">If you configured file destinations for a FILE format element that has been configured to split the generated output whenever specific limits are exceeded, each piece of generated output is sent to the configured file destination as an individual file.</span></span> <span data-ttu-id="db914-118">Para nomear exclusivamente os arquivos que foram criados dividindo a saída, você deve configurar uma expressão de EX para o elemento de formato de arquivo.</span><span class="sxs-lookup"><span data-stu-id="db914-118">To uniquely name the files that are created by splitting the output, you must configure an ER expression for the FILE format element.</span></span> <span data-ttu-id="db914-119">Se você incluir uma fonte de dados de ER de tipo da sequência de número, a sequência numérica será incrementada para cada parte da saída da divisão.</span><span class="sxs-lookup"><span data-stu-id="db914-119">If you include an ER data source of the NUMBER SEQUENCE type, the number sequence will be incremented for each piece of the split output.</span></span>

<span data-ttu-id="db914-120">Para saber mais sobre esse recurso, execute os guias de tarefa **ER Dividir arquivos XML com base do tamanho do arquivo ou na quantidade do item de conteúdo**, que faz parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)** e podem ser baixados do [Centro de Download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="db914-120">To learn more about this feature, play the **ER Split XML files based on the file size or content item quantity** task guide, which is part of the **7.5.4.3 Acquire/Develop IT service/solution components (10677)** business process and can be downloaded from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span> <span data-ttu-id="db914-121">Este guia de tarefas o orienta pelo processo de configuração de um formato de ER para dividir os arquivos gerados com base nos limites de tamanho de arquivo e quantidade de itens de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="db914-121">This task guide walks you through the process of configuring an ER format to split generated files based on limits on the file size and content item quantity.</span></span> <span data-ttu-id="db914-122">Para concluir o guia de tarefas, baixe os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="db914-122">To complete the task guide, you must download the following files:</span></span>

- [<span data-ttu-id="db914-123">Configuração do modelo de ER - XmlFilesSplittingModel.xml</span><span class="sxs-lookup"><span data-stu-id="db914-123">ER model configuration - XmlFilesSplittingModel.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)
- [<span data-ttu-id="db914-124">Configuração de formato de ER - XmlFilesSplittingFormat.xml</span><span class="sxs-lookup"><span data-stu-id="db914-124">ER format configuration - XmlFilesSplittingFormat.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a><span data-ttu-id="db914-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="db914-125">Additional resources</span></span>
[<span data-ttu-id="db914-126">Destinos de relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="db914-126">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)

[<span data-ttu-id="db914-127">Designer de fórmulas no relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="db914-127">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)