---
title: "Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta"
description: "Necessidades de uma sequência numérica de ser adicionada à entidade de extrato bancário para oferecer suporte ao formato MT940."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 672697254c1bf06e193a51c5c7c83c467a220ce8
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta

[!include[banner](../includes/banner.md)]


Necessidades de uma sequência numérica de ser adicionada à entidade de extrato bancário para oferecer suporte ao formato MT940. 

Siga as etapas abaixo para adicionar a entidade de extrato bancário para oferecer suporte ao formato MT940.

1.  Compilar e sincronizar o seguinte:
    -   Entidade composta\\BankStatementImportEntity
    -   Entidade\\BankStatementBalanceEntity
    -   Entidade\\BankStatementDocumentEntity
    -   Entidade\\BankStatementEntity
    -   Entidade\\BankStatementLineEntity
    -   Tabelas\\BankStatementStaging

2.  Projetos de dados\\gerenciamento de dados.
    1.  Projetos de importação de carga MT940
        1.  Alterar XSLT.
            -   Clique em **Exibir mapa**.
            -   Clique **Mapa de exibição** sobre o documento do extrato bancário.
            -   Clique em **Transformações**
            -   Exclua o arquivo de BankReconiliation-to-Composite.xslt.
            -   Adicionar a nova versão de BankReconiliation-to-Composite.xsl.

        2.  Exponha o layout **Número de sequência** em **Dados fonte**.
            1.  Formato de dados fonte = elemento XML.
            2.  Nome da entidade = Extratos bancários.
            3.  Baixar arquivo de dados = nova versão de SampleBankCompositeEntity.xml.
            4.  Clique em **Sim** para substituir o arquivo existente.
            5.  Clique em **Sim** para gerar um novo mapeamento.
            6.  Verifique se S**equenceNumber** está mapeado.
                -   Clique **Mapa de exibição** sobre a entidade do extrato.
                -   Verifique se **SequenceNumber** está mapeado de origem para se preparar.

3.  Importe o novo demonstrativo.




