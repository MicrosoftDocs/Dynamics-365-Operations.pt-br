---
title: Publicar linhas e documentos do Excel
description: "Este tópico explica como inserir e exibir linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que pode ser usado, dependendo do tipo de transação que você está inserindo."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicar linhas e documentos do Excel

Este tópico explica como inserir e exibir linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que pode ser usado, dependendo do tipo de transação que você está inserindo.

Os usuários podem inserir e publicar linhas para diários financeiros do Microsoft Excel. Depois que um usuário cria um diário, ** linhas abertas Excel ** o botão exibir os métodos disponíveis. Os modelos criados para oferecer suporte cenários específicos, porém não cada combinação de tipo de conta é suportada no diário. A tabela mostra os modelos disponíveis e os tipos de conta que oferece suporte.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | ** Tipos de conta com suporte **                                                                                             | ** O modelo como acessar **                                                          |
| Linhas do diário-razão     | Conta: Motivo, cliente, fornecedor, contrapartida do banco: O motivo, cliente, fornecedor, deposita intercompanhia é suportada.       | Diário geral                                                                         |
| Registro de fatura         | Conta: Contrapartida de fornecedor: A razão intercompanhia não está suportada.                                                    | Registro de nota fiscal DE CR                                                                     |
| Diário de faturas          | Contas: Contrapartida de fornecedor: O motivo é suportada intercompanhia.                                                      | Diário de faturas AP                                                                      |
| Fatura de fornecedor           |                                                                                                                         | Fatura de fornecedor                                                                          |
| Diário de faturas de clientes | Conta: Contrapartida do cliente: O motivo é suportada intercompanhia.                                                     | Diário geral                                                                         |
| Fatura de texto livre        |                                                                                                                         | ** Nota fiscal de texto livre ** na página, clique ** abra Excel ** (ícone do Microsoft Office). |
| Diário de ativos fixos     | Ativo fixo para o razão, ao banco, o cliente, ou ao fornecedor. A intercompanhia não é aceito.                                               | Diário de ativo fixo                                                                     |
| Diário de pagamentos do fornecedor   | Conta: Contrapartida de fornecedor: O motivo, banco é suportada intercompanhia.                                                 | Diário de pagamentos do fornecedor                                                                  |
| Diário de pagamentos do cliente | Conta: Contrapartida do cliente: O motivo, banco é suportada intercompanhia.                                               | Diário de pagamentos do cliente                                                                |
| Diário de despesas de projeto  | Conta: Projeto, cliente, razão, a contrapartida do fornecedor: O projeto, em, cliente, fornecedor intercompanhia é suportado. | Despesas gerais de diários (em gerenciamento de projetos e a contabilidade)                       |

Quando as linhas são publicadas, forem validadas para garantir subseqüentes às regras configuradas diários financeiros. Depois que as linhas são publicadas, os usuários podem editar ou lançar os comprovantes do Microsoft Dynamics 365 para as operações. 

Adicionar dimensões financeiras a um modelo, alterações adicionais forem necessárias. Para obter mais informações, consulte adicionar dimensões [modelo do Microsoft Excel (colaborador] - itpro \ \ \ modelos dimensões financeiras). Depois que as dimensões são adicionadas à entidade, estarão disponíveis no excel e designers podem ser adicionadas ao modelo.




