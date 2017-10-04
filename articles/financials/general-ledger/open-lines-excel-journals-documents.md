---
title: "Publicar linhas de diário e documentos do Excel"
description: "Este tópico explica como inserir e exibir linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que podem ser usados, dependendo do tipo de transação que você está inserindo."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1fed8d162a37736883365fa765a059e5beff06be
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicar linhas de diário e documentos do Excel

[!include[banner](../includes/banner.md)]


Este tópico explica como inserir e exibir linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que podem ser usados, dependendo do tipo de transação que você está inserindo.

Os usuários podem inserir e publicar linhas para diários financeiros do Microsoft Excel. Depois que um usuário cria um diário, o botão **Abrir linhas no Excel** exibe modelos que estão disponíveis. Os modelos são criados para oferecer suporte a cenários específicos, porém nem todas combinações de tipo de conta são suportadas no diário. A tabela a seguir mostra os modelos disponíveis e os tipos de conta às quais oferecem suporte.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Modelo**             | **Tipos de conta compatíveis**                                                                                             | **Como acessar o modelo**                                                          |
| Linhas do diário-razão     | Conta: razão, cliente, fornecedor, contrapartida do banco: razão, cliente, fornecedor, intercompanhia de banco é suportada.       | Diário geral                                                                         |
| Registro de fatura         | Contas: Contrapartida de fornecedor: Razão intercompanhia não é suportada.                                                    | Registro de fatura AP                                                                     |
| Diário de faturas          | Contas: Contrapartida de fornecedor: Razão intercompanhia é suportada.                                                      | Diário de faturas AP                                                                      |
| Fatura de fornecedor           |                                                                                                                         | Fatura de fornecedor                                                                          |
| Diário de faturas de clientes | Conta: Contrapartida de cliente: Razão intercompanhia é suportada.                                                     | Diário geral                                                                         |
| Fatura de texto livre        |                                                                                                                         | Na página **Fatura de texto livre**, clique em **Abrir no Excel** (o ícone do Microsoft Office). |
| Diário de ativos fixos     | Ativo fixo para o razão, banco, cliente ou fornecedor. A intercompanhia não é aceita.                                               | Diário de ativo fixo                                                                     |
| Diário de pagamentos do fornecedor   | Conta: Contrapartida de fornecedor: Intercompanhia de banco é suportada.                                                 | Diário de pagamentos do fornecedor                                                                  |
| Diário de pagamentos do cliente | Conta: Contrapartida de cliente: Razão, banco intercompanhia é suportado.                                               | Diário de pagamentos do cliente                                                                |
| Diário de despesas de projeto  | Conta: projeto, razão, cliente, contrapartida de fornecedor: projeto, razão, cliente, intercompanhia de fornecedor é suportada. | Despesas gerais de diários (em gerenciamento de projetos e contabilidade)                       |

Quando as linhas são publicadas, foram validadas para garantir que elas são compatíveis com as regras definidas nos diários financeiros. Depois que as linhas são publicadas, os usuários podem editar ou lançar os comprovantes do Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. 

Para adicionar dimensões financeiras a um modelo, alterações adicionais são necessárias. Para obter informações adicionais, consulte [Adicionar dimensões ao modelo do Microsoft Excel](/dynamics365/unified-operations/dev-itpro/financial/add-dimensions-excel-templates). Depois que as dimensões são adicionadas à entidade, estarão disponíveis no designer do Excel e poderão ser adicionadas ao modelo.





