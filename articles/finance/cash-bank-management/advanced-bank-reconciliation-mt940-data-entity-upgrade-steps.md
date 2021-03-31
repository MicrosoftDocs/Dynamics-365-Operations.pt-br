---
title: Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta
description: Necessidades de uma sequência numérica de ser adicionada à entidade de extrato bancário para oferecer suporte ao formato MT940.
author: panolte
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ee5ad476b10077592c61f6827b5596a1b3e66cd6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217425"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta

[!include [banner](../includes/banner.md)]

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
            6.  Verifique se S **equenceNumber** está mapeado.
                -   Clique **Mapa de exibição** sobre a entidade do extrato.
                -   Verifique se **SequenceNumber** está mapeado de origem para se preparar.

3.  Importe o novo demonstrativo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]