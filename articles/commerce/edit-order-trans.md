---
title: Editar e auditar transações da ordem do cliente assíncronas e ordem online
description: Este tópico descreve como editar e auditar transações da ordem do cliente assíncronas e ordem online no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99ad5be36587a3f726f5b40cccfdd30ab0ef48e1a87563a884f83264f40842fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765281"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Editar e auditar transações da ordem do cliente assíncronas e ordem online

[!include [banner](../includes/banner.md)]

Este tópico descreve como editar e auditar transações da ordem do cliente assíncronas e ordem online no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Entre o Commerce versões 10.0.5 e 10.0.6, foi adicionado o suporte para editar transações cash and carry (como vendas e devoluções) e transações de gerenciamento de caixa (como entrada de flutuação e remoção de meio de pagamento). No Commerce versão 10.0.7, o suporte foi adicionado para editar transações da ordem online e transações assíncronas da ordem do cliente.

## <a name="edit-and-audit-order-transactions"></a>Editar e auditar transações da ordem

Para editar e auditar transações na matriz do Commerce, siga estas etapas:

1. Instalar o [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Na página **Parâmetros reais**, na guia **Ordens do cliente**, na FastTab **Ordem**, especifique um código de bloqueio para **Código de bloqueio para erros de sincronização da ordem**.
1. Abra o espaço de trabalho **Finanças da loja**. Os blocos **Erros de sincronização da ordem online** e **Erros de sincronização da ordem do cliente** fornecem uma exibição pré-filtrada da página de transação de varejo. Cada um deles mostra os registros de transação que falharam na sincronização do tipo de ordem correspondente.
1. Abra a página **Erros de sincronização da ordem online** ou a página **Erros de sincronização da ordem do cliente**. Selecione um registro para exibir os detalhes de erro de sincronização. A FastTab **Status de sincronização** fornece os seguintes detalhes de erro:

    - Status da ordem pendente
    - Detalhes do erro da ordem
    - Data e hora da modificação
    - Número de tentativas

1. Se os detalhes do erro indicarem que o registro deve ser corrigido, selecione **Office Add in** e selecione **Editar transação selecionada**. Um arquivo Excel que mostra os detalhes da transação selecionada é aberto.

    - Se a transação que está sendo editada for uma transação da ordem online, o arquivo Excel conterá as seguintes planilhas:

        - **Transação** – essa planilha tem os detalhes do cabeçalho da transação.
        - **Transação de vendas** – essa planilha tem os detalhes da linha da transação.
        - **Transações de pagamento** – essa planilha tem os detalhes das linhas de pagamento da transação.
        - **Transações de desconto** – essa planilha tem os detalhes relacionados ao desconto da transação.
        - **Transações de imposto** – essa planilha tem os detalhes relacionados ao imposto da transação.
        - **Transações de cobrança** – essa planilha tem os dados relacionados aos encargos da transação.

    - Se a transação que está sendo editada for uma transação assíncrona da ordem do cliente, o arquivo Excel conterá as seguintes planilhas:

        - **Linhas** – essa planilha tem os detalhes do cabeçalho e da linha da transação.
        - **Pagamentos** – essa planilha tem os detalhes das linhas de pagamento da transação.
        - **Descontos** – essa planilha tem os detalhes relacionados ao desconto da transação.
        - **Impostos** – essa planilha tem os detalhes relacionados ao imposto da transação.
        - **Encargos** – essa planilha tem os dados relacionados aos encargos da transação.

1. No arquivo Excel, no campo **Status da ordem pendente**, insira **Edição** e publique a alteração. Dessa forma, você impede que o trabalho **Sincronizar ordem** sendo executado no modo de lote ignore esse registro durante o processamento.
1. No arquivo do Excel, você modifica os campos apropriados e carrega os dados de volta na matriz do Commerce usando a funcionalidade de publicação do Dynamics Excel Add-in. Depois que os dados forem publicados, as alterações serão refletidas no sistema. Durante a publicação, nenhuma validação é feita nas alterações feitas pelos usuários.
1. É possível exibir uma trilha de auditoria completa das alterações pode ser exibida ao selecionar **Exibir trilha de auditoria** no cabeçalho **Transação de varejo** para as alterações no nível do cabeçalho e na seção e no registro relevantes na página de transação apropriada. Por exemplo, todas as alterações relacionadas às linhas de vendas serão mostradas na página **Transações de vendas** e todas as alterações relacionadas a pagamentos serão mostradas na página **Transações de pagamento**. Os seguintes detalhes de auditoria serão mantidos para as alterações:

    - Data e hora da modificação
    - Campo
    - Valor antigo
    - Novo valor
    - Modificação de

1. Depois de fazer e publicar as alterações, selecione **Sincronizar ordem** para iniciar o processo de sincronização imediatamente. Como alternativa, você pode aguardar o processo de sincronização em execução no modo de lote para processar a transação.

Por padrão, após as ordens serem sincronizadas com sucesso, elas são colocadas no status de suspensão, com base no código de bloqueio definido nos parâmetros do Commerce. O bloqueio das ordens deve ser removido antes que elas possam ser processadas posteriormente para cumprimento ou outras operações.

## <a name="additional-resources"></a>Recursos adicionais

[Editar e auditar transações cash and carry e de gerenciamento de caixa](edit-cash-trans.md)

[Editar dimensões financeiras para transações de varejo](edit-financial-dim.md)

[Criar uma pasta de trabalho do Excel para editar transações de varejo](create-excel-edit.md)

[Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]