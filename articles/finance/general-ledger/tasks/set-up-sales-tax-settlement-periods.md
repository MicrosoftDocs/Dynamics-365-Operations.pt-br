---
title: Configurar períodos de liquidação do imposto
description: Este artigo explica como configurar períodos de liquidação de códigos de imposto no Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f8514494b5d3534fc236def817df0d58fe80d70
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846673"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidação do imposto

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar períodos de liquidação do imposto. Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos. Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico. Todos os códigos de imposto associados ao período de liquidação serão liquidados. Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.

Esta tarefa usa a empresa de demonstração USMF.

1. Vá para **Imposto > Impostos indiretos > Imposto > Períodos de liquidação de imposto**.
2. Selecione **Novo**.
3. No campo de **Período de liquidação**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Autoridade**, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.
6. Na lista, localize e selecione o registro desejado.
7. No campo **Termos de pagamento**, selecione o registro desejado no menu suspenso. A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta. Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.  
8. Selecione o tipo de intervalos de período de liquidação.
9. Insira o número das Unidades de intervalo de período por período. Por exemplo, um trimestre tem 3 meses.
10. Marque ou desmarque o **Usar processamento em lotes para liquidação de imposto**. O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo. Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.
11. Marque ou desmarque a caixa de seleção **Impedir a geração de transações de impostos de contrapartida**. Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período. Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.
12. Expanda a guia **Intervalos de períodos**.
13. Selecione **Adicionar**.
14. No campo **Data inicial** na nova linha, insira uma data.
15. No campo **Data final**, insira uma data.
16. Selecione **Novo intervalo do período**. Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente. Você pode voltar e adicionar novos intervalos de período conforme necessário.  
17. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
