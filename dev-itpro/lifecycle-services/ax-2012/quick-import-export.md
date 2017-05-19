---
title: "Utilizar importação/exportação rápida"
description: "A finalidade da Importação/Exportação Rápida é permitir que você realize a importação ou exportação em menos etapas."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 2012 R3 CU8
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f35e7b7d987d6caa19a32460259f07322f2b85cb
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Execute a ferramenta de transferência de dados de teste (beta) para Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


A finalidade da Importação/Exportação Rápida é permitir que você realize a importação ou exportação em menos etapas.

Adicionamos o recurso Importação/Exportação Rápida para permitir que os usuários importem ou exportem trabalhos simples que desejam executar rapidamente. Idealmente, esse recurso é usado em cenários nos quais um arquivo se mapeia automaticamente ao sistema e o usuário não precisa passar pelo mapeamento avançado ou criar trabalhos repetidos de importação ou exportação.

-   Este recurso oferece suporte para trabalhar tanto com entidades fora-da-caixa, quanto personalizadas.
-   Você pode importar de arquivos, e se você estiver usando uma fonte de dados ODBC, você pode selecionar uma consulta a ser usada para definir sua importação.
-   Você deve ter formatos de dados fonte previamente definidos para ambos AX e Arquivo, e saber onde eles estão localizados.
-   Não é necessário criar um grupo de processamento para utilizar a importação/exportação rápida, ele será criado automaticamente pelo sistema durante a execução do trabalho de importação ou exportação. Você também pode escolher manter o histórico de dados importados pela importação/exportação rápida.

  Observe que a Importação/Exportação Rápida presume que você esteja familiarizado com os conceitos de DIXF.




