---
title: Configurar períodos de liquidação do imposto
description: Este tópico explica como configurar períodos de liquidação de imposto no Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5972c44261a6ebd49df0fcbcef9a8c60aaa487e2
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144711"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidação do imposto

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar períodos de liquidação do imposto. Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos. Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico. Todos os códigos de imposto associados ao período de liquidação serão liquidados. Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.

Esta tarefa usa a empresa de demonstração USMF.

1. No painel de navegação, acesse **Módulos > Imposto > Impostos indiretos > Impostos > Períodos de liquidação de imposto**.
2. Selecione **Novo**.
3. No campo de **Período de liquidação**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Autoridade**, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.
6. Na lista, localize e selecione o registro desejado.
7. No campo **Termos de pagamento**, selecione o registro desejado no menu suspenso. A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta. Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.  
8. Selecione o tipo de intervalos de período de liquidação.
9. Insira o número das Unidades de intervalo de período por período. Por exemplo, um trimestre tem 3 meses.
10. Marque ou desmarque o **Usar processamento em lotes para liquidação de imposto**. O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo. Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.  
    > [!NOTE]
    > No momento, isso não tem suporte na Espanha, no Japão e nos Países Baixos.
11. Marque ou desmarque a caixa de seleção **Impedir a geração de transações de impostos de contrapartida**. Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período. Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.
12. Expanda a guia **Intervalos de períodos**.
13. Selecione **Adicionar**.
14. No campo **Data inicial** na nova linha, insira uma data.
15. No campo **Data final**, insira uma data.
16. Selecione **Novo intervalo do período**. Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente. Você pode voltar e adicionar novos intervalos de período conforme necessário.  
17. Feche a página.

