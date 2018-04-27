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
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 14b4a56a229a2e1eb15c29eb7a89a89ac31e58db
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Execute a ferramenta de transferência de dados de teste (beta) para Dynamics AX (AX 2012)

[!INCLUDE [banner](../../includes/banner.md)]

A finalidade da Importação/Exportação Rápida é permitir que você realize a importação ou exportação em menos etapas.

Adicionamos o recurso Importação/Exportação Rápida para permitir que os usuários importem ou exportem trabalhos simples que desejam executar rapidamente. Idealmente, esse recurso é usado em cenários nos quais um arquivo se mapeia automaticamente ao sistema e o usuário não precisa passar pelo mapeamento avançado ou criar trabalhos repetidos de importação ou exportação.

- Este recurso oferece suporte para trabalhar tanto com entidades fora-da-caixa, quanto personalizadas.
- Você pode importar de arquivos, e se você estiver usando uma fonte de dados ODBC, você pode selecionar uma consulta a ser usada para definir sua importação.
- Você deve ter formatos de dados fonte previamente definidos para ambos AX e Arquivo, e saber onde eles estão localizados.
- Não é necessário criar um grupo de processamento para utilizar a importação/exportação rápida, ele será criado automaticamente pelo sistema durante a execução do trabalho de importação ou exportação. Você também pode escolher manter o histórico de dados importados pela importação/exportação rápida.

  Observe que a Importação/Exportação Rápida presume que você esteja familiarizado com os conceitos de DIXF.




