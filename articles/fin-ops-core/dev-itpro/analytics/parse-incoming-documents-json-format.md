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
# <a name="parse-incoming-documents-in-json-format"></a>Analisar documentos de entrada no formato JSON

[!include[banner](../includes/banner.md)]

Você pode criar formatos de relatórios eletrônicos (ER) para analisar documentos eletrônicos de entrada que representam dados em um formato do texto com base em JavaScript (ou seja, arquivos no formato de Notação de Objeto de JavaScript \[JSON\]).

Para saber mais sobre este recurso, baixe arquivos na tabela a seguir e execute o ER Criar uma configuração de formato para importar dados de uma guia externa de tarefas de arquivo JSON. Este guia de tarefas mostra como um formato ER pode ser usado para analisar um arquivo de entrada JSON para atualizar dados de aplicativo.

| Cargo                                  | Nome do arquivo |
|----------------------------------------|-----------|
| Configuração de formato ER                | [Formatar para importar trans_JSON.xml de fornecedores](https://go.microsoft.com/fwlink/?linkid=874111) |
| Amostra de arquivo de entrada no formato .csv | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Requisitos

Antes de concluir o ER Criar uma configuração de formato para importar dados de uma guia externa de tarefas de arquivo JSON, é necessário atender ao seguinte requisito:

- Elementos pai no arquivo JSON só podem ser elementos de objeto.
- Elementos aninhados para um objeto devem ser elementos de propriedade, de forma que uma estrutura JSON válida seja criada.
- Matrizes JSON só podem ser elementos aninhados dos elementos de propriedade de um objeto.
- Matrizes JSON só podem conter objetos JSON. Elas não podem conter cadeias de caracteres diretas/valores numéricos e matrizes aninhadas. Os elementos nessas matrizes serão analisados em ordem, como são especificados no formato. As configurações de multiplicidade em cada objeto JSON serão consideradas.

Além disso, você deverá concluir o guia de tarefas [ER Criar as configurações necessárias para importar dados de um arquivo externo](tasks/er-required-configurations-import-data.md) se ele ainda não tiver sido concluído. Baixe o arquivo a seguir para concluir o guia de tarefas.

| Cargo                  | Nome do arquivo |
|------------------------|-----------|
| Configuração de modelo ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
