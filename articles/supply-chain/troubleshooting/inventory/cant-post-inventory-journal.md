---
title: O fluxo de trabalho do diário de estoque nunca é concluído e o diário não pode ser processado
description: Após o envio de um fluxo de trabalho de aprovação de diário, o processamento do fluxo de trabalho para de responder e não é possível editar ou processar os diários.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 5e8168a20a1fa4f52d28129eebb9931b31157ced
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2022
ms.locfileid: "8488957"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>O fluxo de trabalho do diário de estoque nunca é concluído e o diário não pode ser processado

## <a name="symptoms"></a>Sintomas

Após o envio de um fluxo de trabalho de aprovação de diário, o processamento do fluxo de trabalho para de responder e não é possível editar ou processar os diários.

## <a name="resolution"></a>Resolução

Há vários motivos pelos quais o processamento do fluxo de trabalho pode não ser concluído. Verifique se há os seguintes problemas:

- Acesse **Gerenciamento de estoque &gt; Configuração &gt; Fluxos de trabalho de gerenciamento de estoque** e revise a configuração do fluxo de trabalho afetado. Para obter mais informações, consulte [Fluxos de trabalho de aprovação de diário de estoque](../../inventory/inventory-journal-workflow.md).
- O fluxo de trabalho pode estar encontrando uma exceção ou um erro. Analise o histórico do item de trabalho do fluxo de trabalho afetado para ver se ele inclui um erro de aplicativo que encerra o fluxo de trabalho.
- O diário de estoque pode ser atualizado ou editado somente se for aprovado. Se o cancelamento estiver ativo, você poderá tentar cancelar o diário. A execução do trabalho em lotes do fluxo de trabalho pode ser suspensa por vários motivos. Alguns desses motivos podem ser causados pelo problema de estrutura do fluxo de trabalho.
