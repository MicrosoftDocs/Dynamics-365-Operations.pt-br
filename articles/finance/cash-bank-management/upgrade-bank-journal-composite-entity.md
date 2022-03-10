---
title: ​Atualizar a entidade composta de diário bancário​
description: Este tópico lista as etapas necessárias para incluir um campo adicional de BankTransactionType a BankJournalEntity composto.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0d4334e9aa333aad116f0a0291d9175268661f11
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595425"
---
# <a name="update-the-bank-journal-composite-entity"></a>​Atualizar a entidade composta de diário bancário​

[!include [banner](../includes/banner.md)]

Este tópico lista as etapas necessárias para incluir um campo adicional de BankTransactionType a BankJournalEntity composto.

Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

1.  Compilar e sincronize as entidades compostas o próximo diário bancárias, entidades, preparar e tabelas:
    -   Entidade Composta\\BankJournalEntity
    -   Entidade\\BankJournalHeaderEntity
    -   Entidade\\BankJournalLineEntity
    -   Tabela\\BankJournalHeaderStaging
    -   Tabela\\BankJournalLineStaging

2.  Gerenciamento de dados\\projetos de dados
    -   O tipo **Transação bancária** expõe o layout **Dados de origem**.
        -   Formato de dados fonte = elemento XML
        -   Nome da entidade = Diário bancário
        -   Baixar arquivo de dados = nova versão de SampleBankJournalCompositeEntity.xml
        -   Clique em **Sim** para substituir o arquivo existente.
        -   Clique em **Sim** para gerar um novo mapeamento.
        -   Verifique se o tipo de transação bancária está mapeado.
            -   Clique em **Exibir mapa** na linha Entidade.
            -   Verifique se o tipo de transação bancária está mapeado de origem para se preparar.

3.  Importe o novo demonstrativo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
