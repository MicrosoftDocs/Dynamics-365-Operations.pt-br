---
title: Editar e auditar transações da ordem do cliente assíncronas e ordem online
description: Este artigo descreve como editar e auditar transações da ordem do cliente assíncronas e ordem online no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/21/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dbeeff47446c1617da44f34ae56f333717f577a1
ms.sourcegitcommit: 18b7a02c497709e8d9c7b943d82f1fcc3dafa4cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9712098"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Editar e auditar transações da ordem do cliente assíncronas e ordem online

[!include [banner](../includes/banner.md)]

Este artigo descreve como editar e auditar transações da ordem do cliente assíncronas e ordem online no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Entre o Commerce versões 10.0.5 e 10.0.6, foi adicionado o suporte para editar transações cash and carry (como vendas e devoluções) e transações de gerenciamento de caixa (como entrada de flutuação e remoção de meio de pagamento). No Commerce versão 10.0.7, o suporte foi adicionado para editar transações da ordem online e transações assíncronas da ordem do cliente.

## <a name="edit-and-audit-order-transactions"></a>Editar e auditar transações da ordem

Para editar e auditar transações de ordem no Commerce headquarters, siga estas etapas:

1. Instale o [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Na página **Parâmetros do Commerce**, na guia **Ordens do cliente**, na Guia Rápida **Ordem**, especifique um código de bloqueio para **Código de bloqueio para erros de sincronização**.
2. Pause outros trabalhos de sincronização de ordem que entrarão em conflito com a realização da edição e da auditoria.
3. Abra o espaço de trabalho **Finanças da loja**. Os blocos **Erros de sincronização da ordem online** e **Erros de sincronização da ordem do cliente** fornecem uma exibição pré-filtrada da página de transação de varejo. Cada um deles mostra os registros de transação que falharam na sincronização do tipo de ordem correspondente.
4. Abra a página **Erros de sincronização da ordem online** ou a página **Erros de sincronização da ordem do cliente**. Selecione um registro para exibir os detalhes de erro de sincronização. A FastTab **Status de sincronização** fornece os seguintes detalhes de erro:

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
1. No arquivo do Excel, você modifica os campos apropriados e carrega os dados de volta no Commerce headquarters usando a funcionalidade de publicação do Dynamics Excel Add-in. Depois que os dados forem publicados, as alterações serão refletidas no sistema. Durante a publicação, nenhuma validação é feita nas alterações realizadas pelos usuários.
    > [!NOTE]
    > Se você não encontrar o campo que deve ser editado, siga as etapas abaixo para adicionar o campo ausente na planilha.
    >   1. Selecione **Design** no Conector de Dados.
    >   1. Selecione o ícone de lápis ao lado da tabela à qual você deseja adicionar um campo.
    >   1. Selecione o campo na seção **Campos disponíveis** e, em seguida, selecione **Adicionar**.
    >   1. Adicione quantos campos forem necessários e selecione **Atualizar**.
    >   1. Quando a atualização for concluída, talvez seja necessário selecionar **Atualizar** para atualizar os valores.

3. É possível exibir uma trilha de auditoria completa das alterações ao selecionar **Exibir trilha de auditoria** no cabeçalho **Transação de varejo** para as alterações no nível do cabeçalho e na seção e no registro relevantes na página de transação apropriada. Por exemplo, todas as alterações relacionadas às linhas de vendas serão mostradas na página **Transações de vendas** e todas as alterações relacionadas a pagamentos serão mostradas na página **Transações de pagamento**. Os seguintes detalhes de auditoria serão mantidos para as alterações:

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
