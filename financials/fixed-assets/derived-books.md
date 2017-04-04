---
title: Registros derivados
description: "Este artigo oferece uma visão geral da funcionalidade de registro derivado."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 9319fe95a25b38ca12cbc8633763b042e4086aea
ms.lasthandoff: 03/31/2017


---

# <a name="derived-books"></a>Registros derivados

Este artigo oferece uma visão geral da funcionalidade de registro derivado.

A finalidade de livros derivados é de simplificar a postagem formulário transações de registro de ativos que estão planejadas para intervalos regulares.  Escolher um registro como o principal. Esse geralmente é o registro usado para depreciação contábil. Você o associa a outros registros configurados para lançar transações nos mesmos intervalos do registro principal. Os registros do imposto costumam ser definidos como sendo registros derivados. 

As transações mais comuns a serem definidas para o lançamento nos registros derivados são aquisições, ajustes de aquisição e alienações. 

## <a name="example"></a>Exemplo

Registro B e registro C são definidos como registros derivados para registro A para o tipo de transação de aquisição. No registro A, insira uma transação de aquisição para o ativo 123 de 1.500,00. 

Quando a transação é lançada, uma transação de aquisição é gerada e lançada no ativo 123 para o registro B e no ativo 123 para o método de depreciação C em 1.500,00. Quando você prepara as transações do registro primário para o lançamento no diário de ativo fixo, também é possível exibir e modificar as transações dos registros de depreciações derivados. Caso você prepare as transações do registro principal em outro diário, as transações do método derivado não serão exibidas. No entanto, são lançadas nas contas e nos níveis de lançamento apropriados quando você lança as transações do registro principal.

> [!NOTE]                                                                                                                               
> Os registros definidos para o lançamento das transações em intervalos que não sejam os do registro principal devem ser anexados ao ativo fixo como registros separados, e não derivados.  

Para obter mais informações, consulte [postagem com livros derivados (post-derived-value-models.md]).


