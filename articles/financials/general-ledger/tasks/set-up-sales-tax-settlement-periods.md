--- 
title: "Configurar períodos de liquidação do imposto"
description: "Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos."
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 81214cc52b1488bb70ac5fd6ccc817f6f979163d
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.contentlocale: pt-br
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidação do imposto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos. Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico. Todos os códigos de imposto associados ao período de liquidação serão liquidados. Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.



Esta tarefa usa a empresa de demonstração USMF.



1. Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Períodos de liquidação de impostos sobre vendas.
2. Clique em Novo.
3. No campo de Período de liquidação, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Autoridade, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Termos de pagamento, clique no botão suspenso para abrir a pesquisa.
    * A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta. Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.  
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. Selecione o tipo de intervalos de período de liquidação.
12. Insira o número das Unidades de intervalo de período por período. Por exemplo, um trimestre tem 3 meses.
13. Marque ou desmarque o processamento em lotes de uso da caixa de seleção de liquidação do imposto sobre vendas.
    * O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo. Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.  
14. Marque ou desmarque a caixa de seleção Impedir a geração de transações de impostos de contrapartida.
    * Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período. Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.
15. Expanda a guia dos intervalos de períodos.
16. Clique em Adicionar.
17. Na lista, marque a linha selecionada.
18. No campo De data, insira uma data.
19. No campo Para data, insira uma data.
20. Clique em Novo intervalo do período.
    * Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente. Você pode voltar e adicionar novos intervalos de período conforme necessário.  
21. Feche a página.


