---
title: Registros derivados
description: "Este artigo oferece uma visão geral da funcionalidade de registro derivado."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3cf2f1143837a35a41b12ef566743aefd90fc462
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="derived-books"></a>Registros derivados

[!include[banner](../includes/banner.md)]


Este artigo oferece uma visão geral da funcionalidade de registro derivado.

A finalidade dos registros de depreciações derivados é simplificar o lançamento de transações do registro de ativo fixo planejadas para intervalos regulares.  Você escolhe um registro como o principal. Esse geralmente é o registro usado para depreciação contábil. Você o associa a outros registros configurados para lançar transações nos mesmos intervalos do registro principal. Os registros do imposto costumam ser definidos como sendo registros derivados. 

As transações mais comuns a serem definidas para o lançamento nos registros derivados são aquisições, ajustes de aquisição e alienações. 

## <a name="example"></a>Exemplo

Registro B e registro C são definidos como registros derivados para registro A para o tipo de transação de aquisição. No registro A, insira uma transação de aquisição para o ativo 123 de 1.500,00. 

Quando a transação é lançada, uma transação de aquisição é gerada e lançada no ativo 123 para o registro B e no ativo 123 para o método de depreciação C em 1.500,00. Quando você prepara as transações do registro primário para o lançamento no diário de ativo fixo, também é possível exibir e modificar as transações dos registros de depreciações derivados. Caso você prepare as transações do registro principal em outro diário, as transações do método derivado não serão exibidas. No entanto, são lançadas nas contas e nos níveis de lançamento apropriados quando você lança as transações do registro principal.

> [!NOTE]                                                                                                                               
> Os registros definidos para o lançamento das transações em intervalos que não sejam os do registro principal devem ser anexados ao ativo fixo como registros separados, e não derivados.  

Para obter mais informações, consulte [Lançar com registros de depreciações derivados](post-derived-value-models.md).




