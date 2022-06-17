---
title: Editar e auditar transações cash and carry e de gerenciamento de caixa
description: Este artigo descreve como editar e auditar transações cash and carry e de gerenciamento de caixa no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: cab28dee425110f47a4e2ec5a737778dd567d786
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873320"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Editar e auditar transações cash and carry e de gerenciamento de caixa

[!include [banner](../includes/banner.md)]

Este artigo descreve como editar e auditar transações cash and carry e de gerenciamento de caixa no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os clientes do Dynamics 365 Commerce usam aplicativos de ponto de venda (PDV) próprios, bem como de terceiros. No caso de aplicativo de ponto de venda (PDV) próprio, as transações da loja são extraídas para a matriz do Commerce pelos canais por meio de um processo em lote. No caso de aplicativos de terceiros, as transações são extraídas para a matriz do Commerce por meio da integração. Em ambos os casos, após a extração das transações para a matriz do Commerce, um processo de verificação de consistência deve ser realizado. Esse processo executa várias validações nas transações e somente as transações validadas com sucesso serão extraídas para o demonstrativo para que possam ser lançadas na matriz do Commerce.

Pode haver falha na validação das transações do Commerce por vários motivos. Um bug no código de integração ou no aplicativo DE PDV pode causar inconsistência nos dados. Alternativamente, um erro do usuário pode causar inconsistência nos dados. Por exemplo, um usuário exclui um produto depois que ele foi sincronizado com o canal, ou um usuário fecha um período fiscal sem lançar transações durante esse período. Embora essas transações sejam sinalizadas e excluídas dos demonstrativos, as transações elas podem dificultar o processo diário de lançamento de vendas de um cliente para o financeiro. No Commerce, você pode editar as transações com falha na validação enquanto também mantém uma auditoria de todas as alterações.

## <a name="edit-transactions"></a>Editar transações

No Commerce versão 10.0.5, as únicas transações que podem ser editadas são as transações cash and carry, como vendas e devoluções. As ordens do cliente e as ordens online não podem ser editadas. No Commerce versão 10.0.6 e posterior, as transações de gerenciamento de caixa também podem ser editadas.

Para editar transações na matriz do Commerce, siga estas etapas:

1. Instalar o [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Na matriz do Commerce, abra o espaço de trabalho **Finanças da loja**. O bloco **Falhas na validação de transações** fornece uma exibição pré-filtrada da página da transação com uma ou mais falhas nas regras de validação.
1. Abra a página da transação, selecione o registro que teve falha na validação, selecione **Office Add in** e selecione **Editar transação selecionada**. Um arquivo Excel que mostra os detalhes da transação selecionada é aberto. Este arquivo contém as seguintes planilhas:

    - **Linhas** – essa planilha tem o cabeçalho, as linhas de produtos e os dados relacionados à transação.
    - **Pagamentos** – essa planilha tem os detalhes das linhas de pagamento da transação.
    - **Descontos** – essa planilha tem os detalhes relacionados ao desconto da transação.
    - **Impostos** – essa planilha tem os detalhes relacionados ao imposto da transação.
    - **Encargos** – essa planilha tem os dados relacionados aos encargos da transação.

1. No arquivo do Excel, você modifica os campos apropriados e carrega os dados de volta na matriz do Commerce usando a funcionalidade de publicação do Dynamics Excel Add-in. Depois que os dados forem publicados, as alterações serão refletidas no sistema. Durante a publicação, nenhuma validação é feita nas alterações feitas pelos usuários.
1. É possível exibir uma trilha de auditoria completa das alterações pode ser exibida ao selecionar **Exibir trilha de auditoria** no cabeçalho **Transação de varejo** para as alterações no nível do cabeçalho e na seção e no registro relevantes na página de transação apropriada. Por exemplo, todas as alterações relacionadas às linhas de vendas serão mostradas na página **Transações de vendas** e todas as alterações relacionadas a pagamentos serão mostradas na página **Transações de pagamento**. Os seguintes detalhes de auditoria serão mantidos para as alterações:

    - Data e hora da modificação
    - Campo
    - Valor antigo
    - Novo valor
    - Modificação de

1. Depois que você fizer as alterações e publicá-las, execute e a opção **Validar transações de loja** para validar as alterações consistentes e válidas.

> [!NOTE]
> Só é possível editar as transações que tiveram falha na validação. Se quiser editar uma transação que passou na validação, altere o status da validação da transação para **Erro** ou **Nenhum** e publique a alteração. Em seguida, você poderá editar os dados no cabeçalho ou em qualquer outro registro filho da transação e publicar o cabeçalho ou os registros.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Transações de edição em massa que estão vinculadas a um demonstrativo

No Commerce versão de 10.0.6 e posterior, há suporte à opção para editar transações em massa no nível do demonstrativo.

Para editar em massa transações vinculadas a um demonstrativo na matriz do Commerce, siga estas etapas:

1. Abra a página **Demonstrativos** e selecione o demonstrativo que contém as transações que devem ser editadas.
1. Selecione o botão **Abrir no Microsoft Office**.
1. Dependendo do que deve ser editado, selecione uma das seguintes opções:

    - **Editar transações cash and carry** – essa opção permite que você edite todas as transações cash and carry que estão incluídas no demonstrativo. As planilhas de Excel a seguir estão disponíveis:

        - **Transação** – essa planilha tem todas as informações em nível de cabeçalho para as transações de vendas.
        - **Transação de venda** – essa planilha tem todas as informações em nível de linha para as transações de vendas.
        - **Transações de pagamento** – essa planilha tem todas as informações da linha de pagamento para as transações de vendas.
        - **Transações de desconto** – essa planilha tem todas as informações da linha de desconto para as transações de vendas.
        - **Transação de imposto** – essa planilha tem todas as informações da linha de imposto para as transações de vendas.
        - **Transações de encargos** – essa planilha tem todas as informações da linha de encargos para as transações de vendas.

    - **Editar transações de gerenciamento de caixa** – essa opção permite que você edite todas as transações de gerenciamento que estão incluídas no demonstrativo. As planilhas de Excel a seguir estão disponíveis:

        - **Transação** – essa planilha tem todas as informações em nível de cabeçalho para as transações de gerenciamento de caixa.
        - **Transações de meio de pagamento bancário** – essa planilha tem todos os detalhes da transação de depósito bancário.
        - **Transações de meio de pagamento do cofre** – essa planilha tem todos os detalhes da transação de depósito no cofre.
        - **Declaração de meios de pagamento** – essa planilha tem todos os detalhes da transação de declaração de meios de pagamento.
        - **Transação de receita/despesa**: essa planilha tem todos os detalhes da linha de transação de receita/despesa.
        - **Transações de pagamento** – essa planilha tem todas as informações relacionadas ao pagamento para a operação **Pagar fatura**, bem como para a transação de receita/despesa.

1. Edite as transações necessárias.

    > [!NOTE]
    > As validações não são feitas quando você publica transações editadas em massa. Você deve certificar-se de que todas as edições estejam corretas e que a fidelidade de dados nas planilhas seja mantida. Por exemplo, se quiser alterar a data da transação para que possa gerenciar os cenários em que o período fiscal ou o período de estoque para as transações abertas seja fechado, você deverá alterar a data em todas as planilhas do Excel que tenham a coluna **Data comercial**. Para validar as transações depois que elas forem editadas, você poderá selecionar **Revalidar transações** na página **Demonstrativos**. Aguarde até a conclusão da execução do trabalho de validação antes de lançar o demonstrativo.

1. Se a agregação já tiver sido gerada, abra a página **Transações agregadas** e selecione **Gerar novamente o xml da ordem de venda**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Transações de edição em massa que não estão vinculadas a um demonstrativo

No Commerce versão 10.0.10 e posterior, há suporte à opção de editar transações em massa que tiveram falha na validação, mas que não estão vinculadas a um demonstrativo.

Para editar em massa transações que não estão vinculadas a um demonstrativo na matriz do Commerce, siga estas etapas:

1. Abra a página **Todas as lojas** e selecione a loja na qual as transações devem ser editadas.
1. Selecione o botão **Abrir no botão Microsoft Office** e selecione **Editar transações cash and carry**.
1. Edite as transações necessárias e publique-as.

## <a name="additional-resources"></a>Recursos adicionais

[Editar e auditar transações da ordem do cliente assíncronas e ordem online](edit-order-trans.md)

[Editar dimensões financeiras para transações de varejo](edit-financial-dim.md)

[Criar uma pasta de trabalho do Excel para editar transações de varejo](create-excel-edit.md)

[Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]