---
title: "Publicar linhas de diário e documentos do Excel"
description: "Este tópico explica como inserir e exibir linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que podem ser usados, dependendo do tipo de transação que você está inserindo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a43bf66de7602aa9fb47925996ec5b979e1f8dac
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


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

Quando as linhas são publicadas, foram validadas para garantir que elas são compatíveis com as regras definidas nos diários financeiros. Depois que as linhas são publicadas, os usuários podem editar ou lançar os comprovantes do Microsoft Dynamics 365 for Operations. 

Para adicionar dimensões financeiras a um modelo, alterações adicionais são necessárias. Para obter informações adicionais, consulte [Adicionar dimensões ao modelo do Microsoft Excel](/dynamics365/operations/dev-itpro/financial/add-dimensions-excel-templates). Depois que as dimensões são adicionadas à entidade, estarão disponíveis no designer do Excel e poderão ser adicionadas ao modelo.






