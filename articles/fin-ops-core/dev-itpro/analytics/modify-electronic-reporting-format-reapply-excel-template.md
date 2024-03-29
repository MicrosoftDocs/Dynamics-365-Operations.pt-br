---
title: Modificar formatos de Relatório eletrônico ao reaplicar modelos do Excel
description: Este artigo descreve como modificar o formato de relatório eletrônico (ER) usado para gerar documentos comerciais reaplicando um modelo Excel modificado.
author: kfend
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 02423a75d96bef0452b8555f8c7a9f0aca0b6771
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283518"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modificar formatos de relatório eletrônico ao reaplicar modelos do Excel

[!include [banner](../includes/banner.md)]

A ferramenta de relatório eletrônico (ER) é usada para gerar documentos comerciais em um formato eletrônico. Para gerar um documento comercial, crie um formato de ER e use o designer de ER para definir o layout do documento comercial e especificar os dados a serem incluídos nele. Você pode executar o formato de ER para gerar o documento comercial.

A ferramenta de ER pode ser usada para gerar documentos comerciais como arquivos do Microsoft Excel. Você pode usar um documento Excel como um modelo para esses documentos. Para definir o layout do documento no designer de ER, você pode importar o conteúdo do documento em Excel a ser usado como um modelo no formato de ER definido. Para obter detalhes e praticar este cenário, reproduza a guia de tarefas **Criar uma configuração ER para gerar relatórios no formato OPENXML** (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)). Na etapa do guia de tarefas em que você importa um modelo do Excel, use o modelo inicial do arquivo Excel de relatório de pagamento: [SampleVendPaymWsReport](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx).

Se você editar o documento do Excel usado como um modelo para um documento comercial, a nova funcionalidade de ER permitirá reaplicar o modelo atualizado ao formato de ER. O formato de ER é atualizado de modo que adote o modelo atualizado. Para obter mais detalhes sobre essa funcionalidade, reproduza a guia de tarefas **ER Modificar um formato ao reaplicar um modelo do Excel** (parte do processo comercial Adquirir/Desenvolver componentes de solução/serviço de TI (10683)). Na etapa do guia de tarefas em que você importa um modelo atualizado, use o modelo modificado do arquivo Excel de relatório de pagamento: [SampleVendPaymWsReport2](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx).

## <a name="additional-resources"></a>Recursos adicionais

[Atualize um modelo](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
