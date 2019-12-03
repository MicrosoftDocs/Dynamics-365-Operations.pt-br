---
title: Editar e auditar transações de loja de varejo
description: Este tópico descreve a funcionalidade para editar e auditar transações de loja de varejo.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: f53573b8afb2003f6796930f5877185e533a4715
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693057"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Editar e auditar transações de loja de varejo

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Os clientes do Dynamics 365 Retail usam aplicativos de ponto de venda (PDV) internos, bem como de terceiros. Com o aplicativo de ponto de venda (PDV) interno, as transações de loja de varejo são incluídas no Retail Headquarters a partir dos canais por meio de um processo em lote. Com aplicativos de terceiros, as transações são incluídas no Retail Headquarters por meio de integração. Em ambos os casos, depois que as transações são incluídas no Retail Headquarters, um processo de verificação de consistência que executa mais validações nas transações deve ser realizado, de forma que somente as transações validadas com êxito sejam incluídas no demonstrativo a ser lançado no Retail Headquarters. 

Há falha nas transações de varejo por vários motivos. Por exemplo, um bug no código de integração ou um bug no aplicativo de PDV podem causar dados inconsistentes ou, um erro de usuário, como a exclusão de um produto depois de que este for sincronizado com o canal ou o fechamento de um período fiscal sem o lançamento das transações de varejo para esse período.

Enquanto essas transações são sinalizadas e excluídas dos demonstrativos, as transações podem dificultar o processo diário de lançamento de vendas de varejo de um cliente para o financeiro.

No Retail, você pode editar as transações de varejo específicas com falha na validação enquanto mantém a auditoria de todas as alterações. 

## <a name="edit-and-audit-transactions"></a>Editar e auditar transações

No Retail versão 10.0.5, as transações cash and carry, como vendas e devoluções, são as únicas transações que podem ser editadas. Não há suporte à edição de ordens de cliente ou de ordens online. No Retail versão de 10.0.6 e posterior, também há suporte à edição de transações de gerenciamento de caixa.

1. Instale o suplemento Dynamics Excel.

2. Acesse o espaço trabalho **Finanças da loja de varejo**. O bloco **Falhas na validação de transações** fornece uma exibição pré-filtrada do formulário de transação do Retail com uma ou mais falhas nas regras de validação.
 
3. Abra o formulário. Clique no registro com falha na validação, clique em **Suplemento do Office** e clique em **Editar transação selecionada**. Um arquivo do Excel com os detalhes da transação selecionada será aberto, com as seguintes planilhas:

    - Linhas: essa planilha tem o cabeçalho, as linhas de produtos e os dados relacionados à transação.
    - Pagamentos: essa planilha tem os detalhes das linhas de pagamento para a transação.
    - Descontos: essa planilha tem os detalhes relacionados ao desconto para a transação.
    - Impostos: essa planilha tem os detalhes relacionados ao imposto para a transação.
    - Encargos: essa planilha tem os dados relacionados aos encargos para a transação.

4. No arquivo do Excel, você modifica os campos apropriados e carrega os dados de volta no Retail Headquarters usando a funcionalidade de publicação do suplemento Dynamics Excel. Depois de publicadas, as alterações serão refletidas no sistema. Durante a publicação, nenhuma validação é feita nas alterações feitas pelos usuários.

5. Uma trilha de auditoria completa das alterações pode ser exibida clicando-se em **Exibir trilha de auditoria** no cabeçalho **Transação de varejo** para as alterações no nível do cabeçalho e na seção e no registro relevantes na página de transação apropriada. Por exemplo, todas as alterações relacionadas às linhas de venda serão visíveis na página **Transações de vendas**, as alterações relacionadas aos pagamentos serão visíveis na página **Transações de pagamento**, etc. Os detalhes da auditoria mantidos para as alterações são os seguintes:

   - Data e hora da modificação
   - Campo 
   - Valor antigo
   - Novo valor
   - Modificação de

6. Depois que as alterações forem feitas e publicadas, execute e a opção **Validar transações de loja** novamente para validar que as alterações feitas sejam consistentes e válidas.

> [!NOTE]
> Só é possível editar as transações que tiveram falha na validação. Se quiser editar as transações que passaram na validação, altere o status da validação das transações que você deseja alterar para **Erro** ou **Nenhum** e então poderá editá-las. 


## <a name="bulk-edit-transactions"></a>Editar transações em massa

No Retail versão de 10.0.6 e posterior, há suporte à opção para editar transações de varejo em massa em nível de um demonstrativo. 

1. Use o suplemento do Excel para abrir um demonstrativo que tenha as transações que você deseja modificar usando as etapas 1 a 3 acima.

2. Escolha uma das opções abaixo.

    - **Editar transações cash and carry**. Essa opção permite editar todas as transações cash and carry incluídas no demonstrativo. As planilhas de Excel a seguir estão disponíveis.
    
       - **Transação**: essa planilha tem todas as informações em nível de cabeçalho para as transações de vendas.
       - **Transação de venda**: essa planilha tem todas as informações em nível de linha para as transações de vendas.
       - **Transações de pagamento**: essa planilha tem todas as informações das linhas de pagamento para as transações de vendas.
       - **Transações de desconto**: essa planilha tem todas as informações das linhas de desconto para as transações de vendas.
       - **Transação de imposto**: essa planilha tem todas as informações das linhas de imposto para as transações de vendas.
       - **Transações de encargos**: essa planilha tem todas as informações das linhas de encargos para as transações de vendas.

    - **Editar transações de gerenciamento de caixa**. Essa opção permite editar todas as transações de gerenciamento de caixa incluídas no demonstrativo. As planilhas de Excel a seguir estão disponíveis.
     
       - **Transação**: essa planilha tem todas as informações em nível de cabeçalho para as transações de gerenciamento de caixa.
       - **Transações de meio de pagamento bancário**: essa planilha tem todos os detalhes da transação de depósito bancário.
       - **Transações de meio de pagamento do cofre**: essa planilha tem todos os detalhes da transação de depósito no cofre.
       - **Declaração de meios de pagamento**: essa planilha tem todos os detalhes da transação de declaração de meios de pagamento.
       - **Transação de receita/despesa**: essa planilha tem todos os detalhes da linha de transação de receita/despesa.
       - **Transações de pagamento**: essa planilha tem todas as informações relacionadas ao pagamento para a operação **Pagar fatura**, bem como para a transação de receita/despesa.

3.  As validações não são executadas quando você publica transações editadas em massa. Você deve garantir que todas as edições estejam corretas e que a fidelidade de dados nas planilhas seja mantida. Por exemplo, se quiser alterar a data da transação para gerenciar os cenários em que o período fiscal ou o período de estoque para as transações de varejo abertas seja fechado, você deverá alterar a data em todas as planilhas do Excel que tenham a coluna **Data comercial**. Para validar as transações depois que elas forem editadas, você poderá usar **Revalidar transações** na página **Demonstrativos de varejo**.
