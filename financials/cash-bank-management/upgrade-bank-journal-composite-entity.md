---
title: "Atualizar a entidade de composição operações bancárias diárias"
description: Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 14d58604f5c0aaa4725345f58982387ad0a23205
ms.lasthandoff: 03/31/2017


---

# <a name="update-the-bank-journal-composite-entity"></a>Atualizar a entidade de composição operações bancárias diárias

Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

1.  Compilar e sincronize as entidades compostas o próximo diário bancárias, entidades, preparar e tabelas:
    -   Entidade composta BankJournalEntity\\
    -   Entidade BankJournalHeaderEntity\\
    -   Entidade BankJournalLineEntity\\
    -   Tabela\\BankJournalHeaderStaging
    -   Tabela\\BankJournalLineStaging

2.  Projetos de dados\\de gerenciamento de dados
    -   O tipo **Transação bancária **expõe o layout **Dados de origem **.
        -   Formato de dados fonte = elemento XML
        -   Nome da entidade = Diário bancário
        -   Baixar arquivo de dados = nova versão de SampleBankJournalCompositeEntity.xml
        -   Clique em **Sim** para substituir o arquivo existente.
        -   Clique em **Sim** para gerar um novo mapeamento.
        -   Verifique se o tipo de transação bancária está mapeado.
            -   Clique em **Exibir mapa** na linha Entidade.
            -   Verifique se o tipo de transação bancária está mapeado de origem para se preparar.

3.  Importe o novo demonstrativo.



