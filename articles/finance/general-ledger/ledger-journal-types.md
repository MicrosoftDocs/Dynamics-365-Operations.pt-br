---
title: Tipos de diário-razão
description: Este artigo descreve os tipos de diário que você pode configurar para diários financeiros.
author: kweekley
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 883c54b84ed31384a28c31c8b814c75d340d020e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901303"
---
# <a name="ledger-journal-types"></a>Tipos de diário-razão

[!include [banner](../includes/banner.md)]

Este artigo descreve os tipos de diário que você pode configurar para diários financeiros. Use a página **Nomes de diário** para configurar os diários que você pode usar em todo o Dynamics 365 Finance.

| Tipo de diário                      | Finalidade                       | Inserir transações nesta página                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Alocação                        | Criar transações de alocação em um diário de alocações. Antes de criar um diário de alocações, você deve criar uma regra de alocação na página **Regra de alocação do razão**.      | Processar solicitação de alocação             |
| Aprovação                          | Lance faturas de fornecedor que tiverem sido aprovadas para as contas contábeis apropriadas.  | Diário de aprovações de fatura                                       |
| Estorno de cheque bancário               | Reverter um cheque lançado. Para usar esse tipo de diário, selecione a opção **Usar processo de revisão para estornos de pagamento** na página **Parâmetros de gerenciamento de caixa e bancos**.   | Estornos de cheques, Estorno de pagamento                   |
| Cancelamento de guia de Depósito bancário    | Cancelar uma guia de depósito. Para usar esse tipo de diário, selecione a opção **Usar processo de revisão para cancelamentos de pagamento de guia de depósito** na página **Parâmetros de gerenciamento de caixa e bancos**.   | Cancelamento de pagamentos de guias de depósito            |
| Orçamento                            | Processar apropriações de orçamento. Para usar esse tipo de diário, selecione a opção **Habilitar apropriação de orçamento** na página **Parâmetros da contabilidade**. As entradas no diário de orçamento incluirão informações baseadas nas contas contábeis que são definidas na página **Definições de lançamento**.                                                        |                                                                |
| Aceitação de letra de câmbio pelo cliente  | Criar transações de aceitação do cliente para letras de câmbio.             | Emitir diário de letras de câmbio, Reemitir diário de letras de câmbio. |
| Remessa bancária de cliente          | Criar um arquivo de remessa de letra de câmbio que possa ser enviado para o banco da sua organização. Para usar este tipo de diário, desmarque a opção **Liquidação automática** na página **Parâmetros** **de contas a receber**.            | Remessa                                                     |
| Letra de câmbio emitida por cliente    | Criar transações de letra de câmbio emitida de cliente. Para usar esse tipo de diário, desmarque a opção **Criar e lançar o diário emitido automaticamente ao lançar faturas** na página **Métodos de pagamento - clientes**.   | Emitir diário de letras de câmbio                                  |
| Pagamento de cliente                  | Criar transações de pagamento de cliente.                             | Diário de pagamentos             |
| Letra de câmbio protestada por cliente | Criar transações de letra de câmbio protestada por cliente.                    | Diário de protesto de letras de câmbio                               |
| Letra de câmbio reemitida por cliente  | Criar transações de letra de câmbio reemitida do cliente.                     | Reemitir diário de letras de câmbio                                |
| Letra de câmbio liquidada por cliente  | Criar transações de letra de câmbio liquidada do cliente.                       | Liquidar diário de letras de câmbio                                |
| Diariamente                             | Criar transações diárias em um diário geral.                          | Diário geral                                                |
| Eliminação                       | Criar transações de eliminação em um diário de eliminações. Para usar esse tipo de diário, selecione as opções **Usar para o processo de eliminação financeira** e **Usar para processo de consolidação financeira** na página **Entidades legais**. Para usar este tipo de diário, crie uma regra de eliminação do razão na página **Regra de eliminação do razão**. | Eliminação                                                    |
| Orçamento de ativo fixo                | Criar entradas de registro de orçamento de ativo fixo.                                                                                                                                                                                                                                                                                                                 | Orçamento de ativo fixo                                             |
| Registro de fatura                  | Registre informações básicas sobre faturas de fornecedor.                                                                                                                                                                                                                                                                                                           | Registro de fatura                                               |
| Pagamento de folha de pagamento              | Emitir pagamentos que se baseiam em demonstrativos de pagamento da Folha de Pagamento. Não é possível inserir transações manualmente neste diário. Você deve gerar demonstrativos de pagamento e então enviar esses demonstrativos para pagamento.                                                                                                                                                              |                                                                |
| Periódico                          | Criar transações periódicas para o diário periódico.                                                                                                                                                                                                                                                                                                      | Diários periódicos                                              |
| Lançar ativos fixos                 | Lançar transações de ativo fixo.                                                                                                                                                                                                                                                                                                                              | Ativos fixos                                                   |
| Projeto - Despesas                | Criar transações de despesas do projeto.                                                                                                                                                                                                                                                                                                                        | Expense                                                        |
| Ajuste de moeda de relatório     | Criar ajustes na moeda de relatório para saldos de contas contábeis.               | Diários de ajuste de moeda de relatório                         |
| Transações estatísticas            | Criar transações estatísticas.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Remessa bancária de fornecedor            | Criar um arquivo de remessa de nota promissória que possa ser enviado para o banco da sua organização.                                                                                                                                                                                                                                                                      | Diário de remessas                                             |
| Pagamento de fornecedor               | Criar transações de pagamento do fornecedor.                                                                                                                                                                                                                                                                                                                    | Diário de pagamentos                                                |
| Nota promissória emitida para fornecedor       | Emitir notas promissórias do fornecedor como um método de pagamento. Para usar esse tipo de diário, desmarque a opção **Criar e lançar o diário emitido automaticamente ao lançar faturas** na página **Métodos de pagamento - fornecedores**.                                                                                                                                          | Emitir diário de notas promissórias                                   |
| Grupo de faturas do fornecedor excluindo os lançamentos | Criar transações de fatura de fornecedor que ainda não tenham sido lançadas em uma conta de entrada temporária.                                                                                                                                                                                                                                                             | Grupo de faturas de fornecedor excluindo detalhes de lançamento                  |
| Grupo de faturas de fornecedor               | Criar transações de grupo de fatura de fornecedor.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Registro de fatura de fornecedor          | Lance faturas de fornecedor que estejam em um diário.                                                                                                                                                                                                                                                                                                                 | Diário de faturas                                                |
| Nota promissória reemitida por fornecedor     | Reemitir uma nota promissória que foi liquidada anteriormente pelo banco da sua organização.                                                                                                                                                                                                                                                                      | Reemitir diário de notas promissórias                                 |
| Nota promissória liquidada por fornecedor     | Criar transações de nota promissória liquidada pelo fornecedor.                                                                                                                                                                                                                                                                                                          | Liquidar diário de notas promissórias                                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
