--- 
title: "Configurar a validação de conciliação de faturas de contas a pagar"
description: "Este registro usa a empresa de dados de demonstração USMF."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9bf83269c34133509734691fd018ee703c40626
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Configurar a validação de conciliação de faturas de contas a pagar

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este registro usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas. Antes de começar, verifique se a configuração conciliação de faturas está marcada. Se sua entidade legal acompanha os gastos, como fretes, usando encargos, verifique se a tecla de configuração Cobranças está selecionada.  A conciliação de faturas de contas a pagar é o processo de conciliar as informações da fatura do fornecedor e do recebimento do produto. As diferenças entre esses documentos são chamadas discrepâncias de conciliação. As discrepâncias de conciliação são comparadas com as tolerâncias especificadas. Se uma discrepância de conciliação exceder a porcentagem ou valor de tolerância, os ícones de variação na correspondência são exibidos no formulário de Fatura de fornecedor e no formulário Detalhes de conciliação de faturas.

1. Ir para Contas a pagar > Configuração > Parâmetros de contas a pagar.
2. Clique na guia Validação de fatura.
3. Marque ou desmarque a caixa de seleção Habilitar validação de conciliação de nota fiscal.
    * Selecione se deseja exigir aprovação antes que uma fatura que contém discrepâncias na conciliação de faturas seja lançada. Se ele for configurado para permitir o aviso, a indicação visual será exibida quando uma discrepância na conciliação de notas fiscais exceder a tolerância. No entanto, você poderá lançar a nota fiscal. Para usar fluxos de trabalho junto com a validação de conciliação de nota fiscal, verifique se o campo Lançar nota fiscal com discrepâncias está configurado para permitir o aviso evitar ter que aprovar várias vezes.  
    * Automaticamente no campo status de correspondência do cabeçalho da nota fiscal de atualização, selecione se os correspondentes serão executado automaticamente durante a entrada de dados da nota fiscal pelo sistema. A configuração recomendada é Sim, a menos que você tenha preocupações com o desempenho de entrada de dados. Desabilitar as atualizações automáticas pode habilitar o desempenho do sistema mais rápido porque a validação de conciliação de nota fiscal será ignorada durante a entrada de dados. O vendedor de entrada de dados precisa atualizar manualmente o status de conciliação de nota fiscal para ver os resultados de validação de conciliação de nota fiscal quando este não for definido como.  
4. Alternar a expansão da seção Correspondência total de fatura.
5. Marque ou desmarque a caixa de seleção dos totais de notas fiscais de correspondência para coincidir com os totais de notas fiscais atuais com totais previstos.
    * Selecione se um ícone será exibido se uma discrepância da conciliação de faturas exceder a tolerância. Você pode exibir o ícone quando uma discrepância positiva exceder a tolerância ou quando uma discrepância positiva ou negativa exceder a tolerância.  
    * Por exemplo, a tolerância é 5 e o valor total da fatura da ordem de compra é 100,00. Portanto, um ícone de conciliação do preço será exibido se o valor total da fatura na fatura exceder 105,00. Se você selecionar Se maior que ou menor que a tolerância, um ícone também será mostrado se o valor da fatura for menor que 95,00.  
6. No campo Tolerância de totais de fatura, insira um número.
7. Alternar a expansão da seção Correspondência de preço e quantidade.
    * No campo Política de conciliação de linha, selecione um valor a ser usado como política padrão para a entidade legal com a qual você está trabalhando. “Não necessário“ significa que não há verificação de preços de linha de fatura individual para preço de ordem de compra ou quantidades de fatura para quantidades de guia de remessa necessárias. “Correspondência bidirecional” significa que a verificação das linhas da nota fiscal é necessária mas apenas a ordem de compra e documentos de nota fiscal do fornecedor estão envolvidos no cheque. O recebimento de produtos não é faturado nas validações de conciliação. “Correspondência tripartido“ significa que o preço unitário líquido da nota fiscal será comparado com o preço unitário líquido da ordem de compra correspondente e a quantidade de recebimento de produto será comparada com a quantidade da nota fiscal.  
    * Se você usar uma diretiva de conciliação da linha de correspondência ou da conciliação tripla em bidirecional, você pode configurar percentuais de tolerância de preços para a pessoa jurídica, itens e fornecedores, na página de tolerância de preços de item. Quando as faturas são comparadas com as informações em ordens de compra, a porcentagem da tolerância de preço aplicável é procurada.  
8. No campo da diretiva de conciliação de linha, selecione uma opção.
    * Para permitir que um nível diferente de correspondência seja aplicado a um item, fornecedor, combinação de fornecedor e item ou linha da ordem de compra, selecione um valor no campo Permitir sobreposição de política de conciliação. A política de conciliação da entidade legal pode ser sobrescrita por um fornecedor, item ou combinação de fornecedor e item específicos na página de Política de conciliação.  
    * Para conciliar os totais de preço por itens de linha ou faturas, selecione um valor no campo Totais de preço de correspondência. Esse tipo de correspondência é útil quando o fornecedor envia várias notas fiscais para a mesma linha da ordem de compra. Você pode comparar as informações de preço para o valor líquido de cada linha da fatura e todas as linhas na fatura pendentes e lançadas anteriormente, com o valor líquido da linha da ordem de compra correspondente.  
9. No campo Totais de preço de correspondência, selecione uma opção.
10. No campo Tolerância total de preço de compra, insira um número.
11. Alternar a expansão da seção Correspondência de cobrança.
12. Para conciliar os encargos reais com os encargos esperados, com base nas informações nas ordens de compra, selecione a caixa de seleção Corresponder cobranças.
13. Feche a página.


