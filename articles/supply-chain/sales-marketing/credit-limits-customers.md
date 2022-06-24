---
title: Limites de crédito para clientes
description: Este artigo oferece uma visão geral sobre o funcionamento dos limites de crédito no Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7f15c0f15302c271fac7199b21b7bcd3dcfe88a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903859"
---
# <a name="credit-limits-for-customers"></a>Limites de crédito para clientes

[!include [banner](../includes/banner.md)]

A definição de um limite de crédito permite especificar o valor máximo de crédito a ser estendido aos seus clientes. Se um limite de crédito for especificado, ele será verificado automaticamente quando um usuário tentar atualizar um documento. Se o limite de crédito for excedido, uma mensagem será exibida ao usuário. Este artigo fornece uma visão geral de como os limites de crédito funcionam responde às seguintes perguntas:

-   Para quais documentos e processos posso verificar limites de crédito?

-   Onde configuro como o crédito restante do cliente é calculado?

-   Onde as informações sobre o crédito restante de um cliente são usadas?

-   Onde especifico se a identificação é necessária para que o crédito seja estendido para um cliente e também o valor do limite de crédito que requer identificação?

-   Onde especifico se desejo exibir um aviso ou uma mensagem de erro se o limite de crédito for excedido?

-   Como especifico o limite de crédito de um cliente específico?

-   Como verifico os limites de crédito manualmente nas ordens de venda?

**Para quais documentos e processos posso verificar limites de crédito?**

Use o formulário **Parâmetros de contas a receber** para especificar quais documentos usar para verificar os limites de crédito. Você deve ser membro da função de segurança Administrador do sistema (-SYSADMIN-) para fazer alterações neste formulário. Você pode verificar limites de crédito para os seguintes documentos e processos:

-   Faturas de ordens de venda, quando você lança as faturas

-   Guias de remessa de ordens de venda, quando você atualiza guias de remessa

-   Ordens de venda, quando você adiciona linhas no formulário **Ordem de venda**

-   Ordens de venda, quando elas são criadas com um serviço

-   Faturas de texto livre, quando você lança as faturas

Os limites de crédito serão verificados automaticamente se uma das opções a seguir for definida:

-   No formulário **Parâmetros de contas a receber**, o campo **Tipo de limite de crédito** é definido para qualquer coisa diferente de **Nenhum**. Os limites de crédito são verificados para todos os clientes.

-   No formulário **Parâmetros de contas a receber**, o campo **Tipo de limite de crédito** é definido como **Nenhum**, mas o **Limite de crédito obrigatório** é selecionado para um cliente no formulário **Clientes**. Os limites de crédito são verificados somente para clientes específicos.

Para verificar limites de crédito dos documentos a seguir, você deve especificar configurações adicionais.

|    Documento                                    |    Configuração adicional                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Fatura de texto livre                         |    No formulário Parâmetros de contas a receber, na área de classificação de crédito, selecione Verificar limite de crédito na fatura de texto livre.     |
|    Ordem de venda (inserida manualmente)            |    No formulário Parâmetros de contas a receber, na área de Classificação de crédito, selecione Verificar limite de crédito na ordem de venda.           |
|    Ordem de venda (recebida eletronicamente)     |    No formulário Parâmetros de contas a receber, na área AIF, selecione Verificar limite de crédito para ordens de venda.                     |

**Onde configuro como o crédito restante de um cliente é calculado?**

Você pode configurar o Dynamics 365 para calcular o crédito restante de um cliente de uma das maneiras a seguir:

-   Compare o limite de crédito com o saldo do cliente.

-   Compare o limite de crédito com o saldo do cliente e os valores da guia de remessa.

-   Compare o limite de crédito com o saldo do cliente e todas as atividades de transação abertas. Isso inclui os valores da guia de remessa e os valores da ordem de venda.

Use o formulário **Parâmetros de contas a receber** para especificar informações para a comparação. Você deve ser membro da função de segurança Administrador do sistema (-SYSADMIN-) para fazer alterações neste formulário. No campo **Tipo de limite de crédito**, selecione se deseja executar verificações de limite de crédito e quais informações sobre transação serão incluídas quando o limite de crédito for verificado. Selecione uma destas opções:

-   **Nenhum** – não verificar limites de crédito. Você pode substituir essa opção para um cliente específico ao marcar a caixa de seleção **Limite de crédito obrigatório** no formulário **Clientes**. Se fizer isso, o limite de crédito será verificado em relação ao saldo do cliente.

-   **Saldo** – o limite de crédito é comparado ao saldo do cliente.

-   **Saldo + guia de remessa ou recebimento de produtos** – O limite de crédito é verificado em relação ao saldo do cliente e entregas.

-   **Saldo+tudo** – o limite de crédito é verificado em relação ao saldo do cliente, entregas e ordens abertas.

**Onde as informações sobre o crédito restante de um cliente são usadas?**

As informações sobre um saldo e o valor de crédito restante de um cliente são calculadas e armazenadas quando você cria um instantâneo de classificação por vencimento e são exibidas no formulário **Cobranças** . Os valores que são exibidos no formulário **Cobranças** não podem incluir todas as atividades de transação até que um novo instantâneo de classificação por vencimento seja criado. Para obter mais informações, consulte [Cobranças e crédito em Contas a receber](/dynamicsax-2012/appuser-itpro/collections-and-credit-in-accounts-receivable).

Dependendo dos documentos selecionados, as informações sobre o saldo e o valor do crédito restante de um cliente são calculadas quando ordens de venda, guias de remessa e faturas de cliente são atualizadas. Se o valor do documento com o qual você está trabalhando fizer com que o limite de crédito seja excedido, uma mensagem será exibida.

**Onde especifico se a identificação é necessária para que o crédito seja estendido para um cliente e também o limite de crédito que requer identificação?**

Use o formulário **Parâmetros de contas a receber** para especificar se deseja exigir a identificação e o valor do limite de crédito que requer identificação.
Você deve ser membro da função de segurança Administrador do sistema (-SYSADMIN-) para fazer alterações neste formulário.

|    Campo                                    |    descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Exigir identificação com crédito     |    Selecione o tipo de identificação que deverá ser inserido para clientes aos quais a sua entidade legal estende o crédito. A opção selecionada neste campo determinará quando e que tipo de informação será necessária no campos de Identificação do governo no formulário Clientes:        Nenhum – Nenhum governo-a identificação emitida é necessária, independentemente do limite de crédito do cliente.     Sim – um número de licença emitido pelo governo ou outra identificação emitida pelo governo será necessária, caso o limite de crédito do cliente seja maior ou igual a zero.     Limite mínimo – um número de licença emitido pelo governo ou outra identificação emitida pelo governo será necessária, caso o limite de crédito do cliente seja maior ou igual ao limite inserido no campo Limite desse formulário.        |
|    Limite                                    |    Insira o limite de crédito no qual um número de licença emitido pelo governo ou outra identificação seja exigida dos clientes.    Por exemplo, digite 2000 para exigir que um número de identificação, como o número da carteira de motorista, seja inserido para clientes que tenham um limite de crédito de 2.000 ou superior.    Este campo só estará disponível se tiver selecionado Limite mínimo no campo Exigir identificação com crédito.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Onde especifico se desejo exibir um aviso ou uma mensagem de erro se o limite de crédito for excedido?**

Use o formulário **Parâmetros de contas a receber** para especificar se deseja exibir um aviso ou erro, caso o limite de crédito seja excedido. Esse aviso ou erro é exibido quando um usuário está inserindo ou lançando informações, ou será incluído em um log se os documentos estiverem sendo processados por um serviço eletrônico. Você deve ser membro da função de segurança Administrador do sistema (-SYSADMIN-) para fazer alterações neste formulário.

|    Campo                                                               |    descrição                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Mensagem quando o limite de crédito for excedido (na área Avaliação de crédito)     |    Selecione como as mensagens sobre limites de crédito que estão sendo excedidos serão exibidas aos usuários. Selecionar as seguintes opções:        Erro – uma mensagem de erro será exibida. Isso geralmente interrompe a operação atual e o conflito deve ser resolvido para que o processo possa continuar.     Aviso – uma mensagem de aviso é exibida, mas o processo pode continuar.                     |
|    Mensagem quando o limite de crédito for excedido (na área AIF)               |    Selecione como as mensagens sobre limites de crédito que estão sendo excedidos são fornecidas em um log. Selecione uma das seguintes opções:        Erro – Uma mensagem de erro é exibida no form Exceções e o documento não será processado até o erro ser resolvido.     Aviso – uma mensagem de aviso é exibida no formulário Exceções, mas o processo pode continuar.        |

**Como especifico o valor do limite de crédito de um cliente específico?**

Use o formulário **Clientes** para especificar o valor do limite de crédito de um cliente específico. Você deve ser membro de uma função de segurança que tenha os direitos Manter cliente mestre (CustCustomersMaintain) atribuídos a ela para fazer alterações nesse formulário.

1.  Clique em **Contas a receber** \> **Comum** \> **Clientes** \> **Todos os clientes**. Clique duas vezes em uma conta de cliente.

2.  No formulário **Clientes** , no painel de ações, clique em **Editar**.

3.  Insira um valor de moeda no campo **Limite de crédito**. Esse valor deve ser maior que zero (0) e será usado como valor de limite de crédito.

4.  Se necessário, insira um número de licença ou outra identificação emitida pelo governo no campo **Identificação do governo**.

> [!NOTE]
> No formulário **Parâmetros de contas a receber** , um tipo de limite de crédito normalmente é selecionado. No entanto, se o tipo de limite de crédito for definido como **Nenhum**, você também deverá marcar a caixa de seleção **Limite de crédito obrigatório** no formulário **Clientes** para verificar o limite de crédito do cliente em relação ao saldo do cliente. Para obter mais informações sobre tipos de limite de crédito, consulte "Para quais documentos e processos posso verificar limites de crédito?" neste artigo. 

**Como verifico os limites de crédito manualmente nas ordens de venda?**

Às vezes, você terá que verificar manualmente o limite de crédito de um cliente. Por exemplo, você pode verificar manualmente o limite de crédito de um cliente antes de começar a inserir uma ordem de venda. É possível usar o formulário **Ordem de venda** para verificar manualmente os limites de crédito. Você deve ser membro de uma função de segurança que tenha os direitos Manter ordem de venda (SalesOrderMaintain) atribuídos a ela para fazer alterações nesse formulário.

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**. Clique duas vezes em uma ordem de venda.

2.  No formulário **Ordem de venda** , no painel de ação, na guia **Gerenciar** , clique em **Verificar limite de crédito**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]