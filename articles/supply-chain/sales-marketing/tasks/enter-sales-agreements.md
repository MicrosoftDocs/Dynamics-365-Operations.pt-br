---
title: Inserir contratos de venda
description: Este artigo explica como criar um contrato de venda que compromete um de seus clientes a comprar um produto, com um valor acordado durante um período, em troca de descontos especiais.
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b3aa72057753a9592fd47275dc996a3a904d86b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897477"
---
# <a name="enter-sales-agreements"></a>Inserir contratos de venda

[!include [banner](../../includes/banner.md)]

Este artigo explica como criar um contrato de venda que compromete um de seus clientes a comprar um produto, com um valor acordado durante um período, em troca de descontos especiais. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-up-sales-agreement-header"></a>Configurar cabeçalho do contrato de venda
1. No Painel de Navegação, acesse **Módulos > Vendas e marketing > Contratos de venda > Contratos de venda**.
2. Selecione **Novo**.
3. No campo **Conta do cliente**, selecione o registro desejado no menu suspenso.
4. No campo **Classificação do contrato de venda**, selecione o registro desejado no menu suspenso.
5. Expanda a seção **Geral**.
6. No campo **Compromisso padrão**, selecione **Compromisso de valor do produto**. Um tipo compromisso é um critério obrigatório que você deve atribuir ao contrato para definir como o contrato do acordo será atendido. Os quatro tipos predefinidos permitem configurar o destino do compromisso do cliente, expresso como uma quantidade ou um valor. O tipo de compromisso de quantidade só pode ser aplicado a um produto específico, mas os tipos com base no valor são aplicáveis à vendas de produtos específicos e não específicos.  
7. No campo **Data de vencimento**, defina a data para uma data futura na qual você deseja que o contrato expire.
8. Selecione **OK**.

## <a name="set-up-product-value-commitment-lines"></a>Configurar linhas de compromisso com o valor do produto
1. Selecione **Adicionar linha**.
2. No campo **Número do item**, selecione o registro desejado no menu suspenso. O tipo de compromisso escolhido para o contrato afeta o tipo de informação que você pode inserir para as linhas do contrato. Por exemplo, para um contrato baseado em valor, especifique o valor líquido total (na moeda concordada) para o qual o cliente se compromete a comprar suas mercadorias. Neste exemplo, os campos **Quantidade** e **Unidade** na linha estão indisponíveis porque você está criando um acordo para que o cliente compre um valor específico de um produto.   
3. No campo **Valor líquido**, insira o valor monetário que o cliente confirmou para compra.
4. No campo **Percentual de desconto**, insira um valor percentual que se aplica às linhas da ordem de venda do cliente que estão associadas a esse contrato.
5. Expanda a seção **Detalhes da linha**.
6. Selecione **Sim** no campo **Imposição de valor máx**.
    - Selecionar **Imposição de valor máx.** significa que o valor total de todas as linhas da ordem de venda que usam os preços promocionais especiais do compromisso, descontos e/ou condições de pagamento não devem exceder o valor especificado no compromisso.  
    - Os valores mínimo e máximo especificam um intervalo de valores que deve ser vendido em cada ordem de venda que usa o contrato selecionado.   
7. Expanda a seção **Cabeçalho do contrato de venda**. A menos que o status do contrato seja definido como **Em vigor**, as ordens de venda não podem ser associadas ao contrato e, consequentemente, não podem contribuir para o atendimento desse contrato. Você pode alterar o status manualmente neste estágio. No entanto, o status normalmente é alterado quando você confirma o contrato para o cliente.  
8. No Painel de Ações, selecione **Contrato de venda**.
9. Selecione **Confirmação**. Certifique-se de que a opção **Marcar contrato como em vigor** está definida como **Sim**.  
10. Selecione **Sim** no campo **Imprimir relatório**.
11. Selecione **OK**.
12. Feche a página. O contrato agora está em vigor. Você pode começar a vincular as ordens do cliente ao contrato para deslocar em relação ao destino comprometido.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]