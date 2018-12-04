--- 
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: "Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Criar uma nomenclatura de produtos de grades de produto predefinidas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado. A empresa de dados demo usada para criar este procedimento é USMF. A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho. A tarefa geralmente seria realizada por um designer de produto.


## <a name="create-a-product-number-nomenclature"></a>Criar uma nomenclatura de número de produto
1. Clique em Definição de modelo de variante de produto.
2. Clique em Nomenclatura de produto.
3. Clique em Novo.
4. No campo Nome, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, ColorSize.
5. No campo Descrição, digite um valor.
6. Clique em Adicionar.
7. Clique em Número do produto mestre.
8. Clique em Adicionar.
9. Clique em Constante de texto.
10. No campo Texto, digite um valor.
11. Clique em Adicionar.
12. Clique em Cor.
13. Clique em Adicionar.
14. Clique em Constante de texto.
15. No campo Texto, digite um valor.
16. Clique em Adicionar.
17. Clique em Tamanho.
18. Feche a página.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Atribuir a nomenclatura a um produto mestre
1. Clique em Grupos de dimensões do produto.
2. Selecione o grupo de dimensões do produto SizeCol.
3. Clique em Editar.
4. Selecione Sim no campo Usar nomenclatura.
5. No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.
6. Feche a página.


