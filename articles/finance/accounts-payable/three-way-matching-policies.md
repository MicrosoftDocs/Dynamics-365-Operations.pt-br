---
title: Políticas de conciliação tripla
description: Este tópico oferece exemplos da conciliação tripla.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cffdc06216ce8ab1bfb79265f265bec1aee334c5
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109984"
---
# <a name="three-way-matching-policies"></a>Políticas de conciliação tripla

[!include [banner](../includes/banner.md)]

Este tópico oferece exemplos da conciliação tripla.

## <a name="example-three-way-matching-for-items"></a>exemplo: conciliação tripla para itens

**Resumo**: Ken é o controlador em sede corporativa de uma entidade legal denominada Fabrikam. Ken decide que todas as faturas de fornecedor que foram com base em ordens de compra deve ser correspondidas com linhas da ordem de compra (conciliação dupla). Para compras de itens que serão usados como ativos fixos, as faturas devem ser correspondidas com as linhas da ordem de compra e linhas do recebimento de produtos (conciliação tripla).

A Fabrikam opera com vários entidade legal e funcionários em todas as partes do mundo. Como o volume de transações aumenta, as discrepâncias entre recebimentos e faturas também serão entrega. Isso resultará em ativos que estão sendo dados baixa. As faturas de fornecedores estão sendo pagas, mas ele não inclui identificação de discrepâncias quando menos itens são recebidos do que foram encomendados, ou quando os itens não são recebidos de todo. Gastar também aumenta como os funcionários ainda precisam ferramentas e outros materiais de realizar seus trabalhos. Ken deseja verificar se os fornecedores são enviando as mercadorias que foram encomendados e os itens estão sendo recebidos por funcionários da Fabrikam leste. Portanto, Ken requer em bidirecional e a conciliação tripla para todas as entidade legal na organização. Ajuda da conciliação de faturas certifique-se de que os problemas com itens que desapareceram ou recebidas podem ser rastreados e resolvido. 

As políticas de conciliação de faturas neste exemplo ajudam as pessoas nas funções a seguir a atenderem estes objetivos:

-   Ken é o controlador para a empresa da Fabrikam leste. Ken pode ajudar as pessoas na empresa a identificar e solucionar problemas no pedido, no recebimento e no pagamento de itens (produtos e serviços) de fornecedores.
-   Phyllis e abril são gerentes de contabilidade no departamento de contas a pagar para divisão dos Estados Unidos da Fabrikam leste. Podem ou não aplicar a política corporativa e garantir que as faturas sejam pagas apenas depois de serem conciliadas com a ordem de compra e recebimentos de bens e serviços, onde aplicável.
-   Tony é o gerente de produção para divisão dos Estados Unidos da Fabrikam leste. Tony e outros funcionários de produção podem ter certeza de que os itens são recebidos como foram pedidos de fornecedores, e esclarecidos de modo que os funcionários tenham o necessário para realizar seus trabalhos.

### <a name="prerequisites"></a>Pré-requisitos

-   Ken define a **Política de conciliação** no nível de entidade legal para a **Conciliação tripla**.
-   Ken define a opção **Atualizar automaticamente o status de conciliação** do cabeçalho na entidade legal como **Sim**.
-   Ken define o campo **Conciliar totais de preço** para a entidade legal como **Porcentagem** e insere 15% como a **Porcentagem de tolerância**.
-   Ken define a política de conciliação no nível do item para o item 1500 – computador do CNC Milicron como **Conciliação tripla**. Esse item for um item de ativo fixo que será usado para a produção na Fabrikam compras. As faturas para esse item são correspondidas com linhas da ordem de compra de preços e com recebimentos de produtos para quantidades.
-   Tony inserir uma requisição para cinco máquinas de CNC Milicron. Alicia, um vendedor da ordem de compra na Fabrikam, emite uma ordem de compra para uma entidade legal denominadas Contoso para fornecer os itens.

    | Nº do item                 | Quantidade | Preço unitário | Valor líquido | Código de encargos        | Valor dos encargos |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 - Computador do CNC Milicron | 5        | 8.000,00   | 40.000,00  | Remessa e manuseio | 3.000,00      |

-   Arnie, um vendedor de contas a receber na Contoso, analise as remessas para a semana. Arnie selecionar as transações de remessa para faturar a Fabrikam para a entrega dos computadores do CNC Milicron. Arnie inclui um encargo para enviar e ao manuseio. A Fabrikam considerará o encargo parte do custo do ativo.

### <a name="scenario"></a>Cenário

1.  Sammy, um funcionário no departamento de remessa na Fabrikam recebe, a quantidade total de computadores que são enviados da Contoso. Sammy insere uma quantidade de 5 computadores no recibo de um produto. Como a ordem de compra foi totalmente recebida, o status da ordem de compra será alterado para Recebida.
2.  Abril, coordenada de contas a pagar, na Fabrikam insere e verifica a fatura que é enviada por Contoso. Verifica as seguintes informações:
    -   Para os itens que exigem a conciliação tripla, a quantidade na linha da fatura corresponde à quantidade que foi recebida. A quantidade recebida é indicado no recibo de bens que corresponde à fatura.
    -   Para os itens que exigem uma correspondência de duas ou três vias, os preços da linha da fatura estão dentro de tolerâncias definidas no Microsoft Dynamics 365 Finance. Isso inclui os seguintes tipos de correspondência de preço:
        -   Correspondência de preço unitário líquido – O preço unitário líquido da linha da fatura corresponde ao preço unitário líquido da linha da ordem de compra, na porcentagem de tolerância. Em este exemplo, a tolerância de preço líquido da unidade é +8%.
        -   Preços totais de correspondência – O valor líquido em correspondências da linha da fatura o valor líquido da linha da ordem de compra, na porcentagem de tolerância, o valor ou a porcentagem e o valor. Em este exemplo, os totais de preços que correspondem a tolerância são +15%.

A fatura em papel da Contoso contém as seguintes informações.

| Item                        | A quantidade | Preço unitário | Valor líquido |
|-----------------------------|----------|------------|------------|
| 1500 - Computador do CNC Milicron | 5        | 8.100,00   | 40,500.00  |
| Remessa e manuseio       |          |            | 4,000.00   |
| Imposto                         |          |            | 0,00       |
| Total                       |          |            | 44,500.00  |

A linha da fatura contém as seguintes informações.

| Nº de itens                 | Quantidade | Preço unitário | Valor líquido da linha | Política de conciliação    | Correspondência de quantidade de recebimento de produtos | Conciliação de preço | Conciliação de total de preço |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 - Computador do CNC Milicron | 5        | 8.100,00   | 40.500,00       | Conciliação tripla | Aprovado                         | Aprovado      | Aprovado            |

Porque a linha passa o processo de conciliação de faturas, a fatura pode ser lançada.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>exemplo: Conciliação tripla para combinações de item e fornecedor
resumo: Ken é o controlador em sede corporativa de uma entidade legal denominadas Fabrikam compras. Ken decide que todas as faturas de fornecedor que foram com base em ordens de compra deve ser correspondidas com linhas da ordem de compra (conciliação dupla). Cassie é contadora na divisão Malásia da Fabrikam leste. Ela especifica que os itens selecionados encomendados de certos fornecedores na Malásia devem corresponder às linhas da ordem de compra e às linhas do recebimento de produtos (conciliação tripla). Ela também pode substituir a política de conciliação por um nível mais alto de correspondência para ordens de compra específicas. 

O volume e os valores são baixos, e houve um problemas com entrega de alguns fornecedores na Malásia. Por esse motivo, Cassie define o nível de combinações de item e fornecedor de controle para determinadas que são obtidas na Malásia a conciliação tripla. 

As políticas de conciliação de faturas neste exemplo ajudam as pessoas nas funções a seguir a atenderem estes objetivos:
-   Ken é o controlador para a empresa da Fabrikam leste. Ken pode ajudar as pessoas na empresa a identificar e solucionar problemas no pedido, no recebimento e no pagamento de itens (produtos e serviços) de fornecedores.
-   Cassie é contadora na divisão Malásia da Fabrikam leste. Ela pode ou não aplicar a política corporativa e garantir que as faturas sejam pagas apenas depois de serem conciliadas com linhas da ordem de compra e recebimentos de produtos que representam o recebimento de bens e serviços. Também pode aumentar o nível de controle na conciliação tripla para itens específicos aos custos operacionais de controle.

### <a name="prerequisites"></a>Pré-requisitos

-   Ken define a **Política de conciliação** no nível da entidade legal como **Conciliação dupla**.
-   Ken define o campo **Conciliar totais de preço** para a entidade legal como **Porcentagem** e insere **10%** como **Porcentagem de tolerância**.
-   Ken define o limite do preço unitário para todos os itens para 2%.
-   Cassie define a **Política de conciliação** no nível da combinação de item e fornecedor para o item PH2500 – Computador e fornecedor Contoso como **Conciliação tripla**.
-   Alicia, uma funcionária de ordens de compra na divisão da Fabrikam na Malásia, emite ordens de compra para a Contoso fornecer três itens, como mostra a tabela a seguir. Ao criar a ordem de compra, ela substitui a **Política de conciliação** para que o mouse sem fio seja conciliação tripla em vez de conciliação dupla.

    | Nº do item           | Quantidade | Preço unitário | Valor líquido | Política de conciliação (entrada padrão) | Política de conciliação (na linha da ordem de compra) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 - Computador     | 2        | 2.500,00   | 5.000,00   | Conciliação tripla              | Conciliação tripla                           |
    | MM01 - o mouse sem fio | 2        | 40,00      | 80,00      | Conciliação dupla                | Conciliação tripla                           |
    | Unidade USB             | 200      | 10,00      | 2.000,00   | Conciliação dupla                | Conciliação dupla                             |

### <a name="scenario"></a>Cenário

1.  Os itens chegarem. Sammy, um funcionário no departamento de recebimento de divisão Malásia da Fabrikam, é interrompido e não lançar o recebimento de produtos imediatamente.
2.  Abril, coordenada de contas a pagar, na Fabrikam insere e verifica a fatura que é enviada por Contoso. Verifica as seguintes informações:
    -   Para os itens que exigem a conciliação tripla, a quantidade na linha da fatura corresponde à quantidade que foi recebida. A quantidade recebida é indicado no recibo de bens que corresponde à fatura.
    -   Para os itens que exigem uma correspondência de duas ou três vias, os preços da linha da fatura estão dentro de tolerâncias definidas no aplicativo. Isso inclui os seguintes tipos de correspondência de preço:
        -   Correspondência de preço unitário líquido – O preço unitário líquido da linha da fatura corresponde ao preço unitário líquido da linha da ordem de compra, na porcentagem de tolerância. Em este exemplo, a tolerância de preço líquido da unidade é +2%.
        -   Preços totais de correspondência – O valor líquido em correspondências da linha da fatura o valor líquido da linha da ordem de compra, na porcentagem de tolerância, o valor ou a porcentagem e o valor. Em este exemplo, os totais de preços que correspondem a tolerância são +10%.

A fatura em papel da Contoso contém as seguintes informações.

| Item                  | A quantidade | Preço unitário | Valor líquido |
|-----------------------|----------|------------|------------|
| PH2500 - Computador     | 2        | 2.500,00   | 5.000,00   |
| MM01 - o mouse sem fio | 2        | 41.00      | 82.00      |
| Unidade USB             | 200      | 10.05      | 2,010.00   |
| Total da fatura         |          |            | 7,092.00   |

A linha da fatura contém as seguintes informações.

| Nº de itens           | Quantidade | Preço unitário | Valor líquido da linha | Política de conciliação    | Correspondência de quantidade de recebimento de produtos | Conciliação de preço | Conciliação de total de preço |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 - Computador     | 2        | 2.500,00   | 5.000,00        | Conciliação tripla | Falhou                         | Aprovado      | Aprovado            |
| MM01 - o mouse sem fio | 2        | 41,00      | 82,00           | Conciliação tripla | Falhou                         | Falhou      | Aprovado            |
| Unidade USB             | 200      | 10,05      | 2.010,00         | Conciliação dupla   |                                | Aprovado      | Aprovado            |

Observe os seguintes itens:
-   Para a linha PH2500 – Computador, a coluna Conciliação de quantidade de recebimento de produto tem um ícone de aviso porque a linha da fatura não é conciliada com um recebimento de produtos.
-   Para a linha MM01 – Mouse Sem Fio, a coluna Conciliação de quantidade de recebimento de produto tem um ícone de aviso porque a linha da fatura não é conciliada com um recebimento de produtos. A coluna de Conciliação de preço unitário tem um ícone de aviso porque a tolerância de preço 2% líquida da unidade é excedido.
-   Para a linha Unidade USB, a coluna Conciliação de quantidade de recebimento de produtos está em branco porque a conciliação dupla não faz correspondência com a linha da fatura e quantidades de linhas de recebimento de produtos.

Se a aprovação for necessária para o qual as faturas são lançadas com discrepâncias de conciliação de faturas, a opção **Aprovar lançamento com discrepâncias de conciliação** na página **Detalhes de conciliação de faturas** deve ser selecionada antes da fatura pode ser lançada com erros de conciliação de preço e erros na conciliação de quantidade. Se a aprovação não é necessária, o processamento da fatura pode continuar se não houver nenhum outro erro de lançamento.


Para obter mais informações, consulte [Visão geral de conciliação de faturas de Contas a pagar](accounts-payable-invoice-matching.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
