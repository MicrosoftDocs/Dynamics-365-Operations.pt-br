---
title: Atualizar a entidade composta do diário de banco
description: Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6c990208f26dde26b7adc306198f7cd16e0e69b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978905"
---
# <a name="update-the-bank-journal-composite-entity"></a>Atualizar a entidade composta do diário de banco

[!include [banner](../includes/banner.md)]

Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.

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




