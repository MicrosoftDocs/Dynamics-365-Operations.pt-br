--- 
title: "Criar políticas de compras"
description: "Este procedimento mostra-lhe como criar políticas de compra para alinhar com seus processos de negócios de compra."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 51486712d732bba064fd6c9b64dbccb730603877
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-purchasing-policies"></a>Criar políticas de compras

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra-lhe como criar políticas de compra para alinhar com seus processos de negócios de compra. Para que você possa criar políticas de compras, você deve configurar os parâmetros da política de compras. É possível criar, alterar e aposentar uma política de compra, mas você não pode suprimir uma política de compra. Normalmente essa procedimento é realizado por um Gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.


## <a name="set-up-policy-parameters"></a>Configurar parâmetros de política
1. Vá para Políticas de compra.
2. Clique em Parâmetros.
    * As regras de precedência da política aplicam-se aos níveis diferentes em sua organização. As unidades de organização em que são mostrados dependem de sua hierarquia de organização, e em que níveis na hierarquia foram atribuídos a finalidade do controle interno da obtenção. Por exemplo, sua organização pode ter entidades legais, centros de custo, regiões e departamentos, mas pode ser que somente alguma destes tenha uma finalidade da hierarquia do controle interno da obtenção. Como padrão, a organização do tipo empresa está disponível.  
3. Clique na guia Parâmetros do tipo de regra de política.
4. Na árvore, selecione "política de compras/regra de controle de requisição de compra".
    * Você define a ordem de precedência da resolução da política no nível da política. No entanto, para alguns tipos de política, você pode substituir a ordem de precedência para tipos de regras de política individuais. Por exemplo, você definiu precedência de políticas de compras nesta ordem: centro de custo, departamento, empresa. Para a regra de política de catálogo, você deseja que a ordem de precedência esteja nesta ordem: departamento, centro de custo, empresa. Você pode alterar a ordem de precedência para a regra de política de catálogo. Quando um trabalhador cria uma requisição, o catálogo que é indicado está determinado pelas políticas que são associadas com o departamento do trabalhador, então seu centro de custo, e então sua empresa.  
    * Se há mais de um nível de organização alistado, você pode usar as setas para cima/baixo para ajustar a ordem de precedência para a regra do controle da requisição da compra.  
5. Feche a página.

## <a name="create-a-new-policy"></a>Criar uma nova política
1. Clique em Novo.
2. No campo Nome, digite um valor.
3. No campo Descrição, digite um valor.
    * Uma política de compras individual pode ser aplicada apenas a uma hierarquia da organização. Por exemplo, você poderia ter uma hierarquia chamada “geográfica” e uma chamada “departamento”, e uma política de compras diferente para cada uma.  
    * Selecione uma organização a que a política deva se aplicar.  
4. Clique na seta para adicionar a organização selecionada.
    * Você pode repetir este processo para adicionar mais organizações.  

## <a name="add-a-policy-rule"></a>Adicionar uma regra de política
1. Na lista Tipo de regra de política, selecione Regra de objetivo de requisição.
    * Você criará uma regra que ajuste a finalidade da requisição padrão para inserir Consumo, mas permite que o tipo do reabastecimento seja selecionado em vez disso.  
2. Clique em Criar regra de política.
3. Selecione Sim no campo Permitir substituição manual.
4. Clique em Fechar.
    * Agora você pode estabelecer outras regras da política para a política de compras.   Note que um tipo da regra da política não pode ter as regras de sobreposição que são ativas ao mesmo tempo dentro de uma única política de obtenção.  
5. Feche a página.
6. Feche a página.


