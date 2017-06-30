---
title: "Atualizar a entidade composta do diário de banco"
description: Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 43413aad9d537e518f7276ccab11ce01d23cf13f
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="update-the-bank-journal-composite-entity"></a>Atualizar a entidade composta do diário de banco

[!include[banner](../includes/banner.md)]


Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

1.  Compilar e sincronize as entidades compostas o próximo diário bancárias, entidades, preparar e tabelas:
    -   Entidade Composta\\BankJournalEntity
    -   Entidade\\BankJournalHeaderEntity
    -   Entidade\\BankJournalLineEntity
    -   Tabela\\BankJournalHeaderStaging
    -   Tabela\\BankJournalLineStaging

2.  Gerenciamento de dados\\projetos de dados
    -   O tipo **Transação bancária**expõe o layout **Dados de origem**.
        -   Formato de dados fonte = elemento XML
        -   Nome da entidade = Diário bancário
        -   Baixar arquivo de dados = nova versão de SampleBankJournalCompositeEntity.xml
        -   Clique em **Sim** para substituir o arquivo existente.
        -   Clique em **Sim** para gerar um novo mapeamento.
        -   Verifique se o tipo de transação bancária está mapeado.
            -   Clique em **Exibir mapa** na linha Entidade.
            -   Verifique se o tipo de transação bancária está mapeado de origem para se preparar.

3.  Importe o novo demonstrativo.





