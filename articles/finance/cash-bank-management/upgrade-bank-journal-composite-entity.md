---
title: Atualizar a entidade composta de diário bancário
description: Este artigo lista as etapas necessárias para incluir um campo adicional de BankTransactionType a BankJournalEntity composto.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: db5f01af6b21b4dc5ff633ee9c11bb6ed41df048
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868537"
---
# <a name="update-the-bank-journal-composite-entity"></a>Atualizar a entidade composta de diário bancário

[!include [banner](../includes/banner.md)]

Este artigo lista as etapas necessárias para incluir um campo adicional de BankTransactionType a BankJournalEntity composto.

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
