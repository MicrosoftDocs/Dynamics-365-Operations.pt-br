---
title: Analise documentos de entrada no formato Excel
description: Este tópico fornece informações sobre como criar formatos de Relatórios eletrônicos (ER) para analisar o conteúdo contido em arquivos de entrada do Microsoft Excel.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0c41a062d817307adb2889d3678764f1ea4066e2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755171"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Analisar documentos de entrada no formato Excel

[!include[banner](../includes/banner.md)]

Você pode criar formatos de relatórios eletrônicos (ER) para analisar arquivos de entrada do Microsoft Excel que representam dados nas pastas de trabalho do Microsoft Excel (arquivos no formato XLSX). Você pode usar o conteúdo desses arquivos para atualizar dados do aplicativo. Isso será útil se você:

- Criar um novo modelo e formato e testá-los em tempo de execução. Nesse caso, o Excel simulará os dados reais do aplicativo.
- Gerenciar dados além do aplicativo no Excel e desejar importar esses dados para enviar um relatório específico.

Para saber mais sobre esse recurso, execute as guias de tarefa **ER Importar dados de um arquivo do Microsoft Excel (Parte 1: Criar formato)** e **Importar dados de ER de um arquivo do Microsoft Excel (Parte 2: Importar dados)** (partes do processo comercial 7.5.4.3 Adquirir/desenvolver serviço de TI/componentes de solução (10677)). Essas guias de tarefas mostram como o arquivo de entrada do Excel pode ser analisado usando o formato de ER para importar informações de documentos de entrada e atualizar dados do aplicativo. É possível baixar os arquivos da guia de tarefas no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).

Baixe os arquivos a seguir para concluir as guias de tarefas mencionadas anteriormente.

| Descrição do conteúdo                         | Arquivo                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| Arquivo de entrada no formato .XLSX - modelo    | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| Arquivo de entrada no formato .XLSX - dados de exemplo | [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Se você ainda não tiver reproduzido este guia de tarefas, [ER Criar configurações necessárias para importar dados de um arquivo externo](./tasks/er-required-configurations-import-data.md) no aplicativo atual do Finance and Operations, baixe o arquivo a seguir.

| Descrição do conteúdo    | Arquivo                                                            |
|------------------------|-----------------------------------------------------------------|
| Configuração de modelo ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]