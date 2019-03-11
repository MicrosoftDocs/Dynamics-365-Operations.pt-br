---
title: Criar uma sequência de cartas de cobrança
description: Use esta guia para criar uma tarefa de sequência de cartas de cobrança.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db5264f6d8d7723ff01d13e99728c2bfebcb4515
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311556"
---
# <a name="create-a-collection-letter-sequence"></a>Criar uma sequência de cartas de cobrança

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use esta guia para criar uma tarefa de sequência de cartas de cobrança. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Crédito e coleções > Configuração > Configurar sequência de carta de coleção.
2. Clique em Novo.
3. No campo de sequência de cartas de cobrança, insira uma ID de sequência que represente a sequência. Será usada ao configurar um perfil de lançamento.
4. No campo Descrição, digite um valor.
    * As condições de pagamento são opcionais. Se você inserir um valor aqui, a nota fiscal da taxa de carta de cobrança usará essas condições de pagamento em vez das condições de pagamento estocadas com o cliente.  
5. No campo código da carta de cobrança, selecione o código para a primeira carta de cobrança que você deseja remeter.
    * A primeira carta de cobrança é criada de acordo com a data de vencimento na fatura, o valor inserido para o período de carência no campo Dias nessa linha e outras informações inseridas nessa linha.  
6. No campo Descrição, digite um valor.
    * A moeda da taxa padrão para a moeda do cliente. O código da moeda pode ser diferente da moeda da nota fiscal.  
7. Clique em Adicionar para adicionar a carta de cobrança seguinte que será enviada na sequência
    * Em muitos casos, a primeira carta de cobrança é apenas um aviso. Você pode adicionar taxas, se necessário.  
8. No campo código da carta de cobrança, selecione o próximo código que será enviado na sequência.
9. No campo Descrição, digite um valor.
10. No campo de conta principal, selecione a conta de receita que será usada para taxas.
11. Digite a taxa que será carregada quando esta carta de cobrança é lançada.
12. No campo Grupo de imposto sobre vendas do item, clique no botão suspenso para abrir a pesquisa.
    * Selecione um grupo de impostos sobre vendas do item se o imposto sobre vendas deve ser calculado na taxa.  
13. Na lista, clique no link na linha selecionada.
14. Insira o saldo atrasado mínimo necessário antes de uma carta de coleção ser enviada.
15. Insira o número de dias de carência que você permitirá.
    * Esse é o número de dias após a data de vencimento que uma carta de cobrança pode ser produzida. A data de vencimento que é usada para o cálculo depende da posição da carta de cobrança na sequência de cartas de cobrança:   ⦁    O período de carência para a carta de cobrança 1 é relativo à data de vencimento da fatura.  ⦁ O período de carência para as cartas de cobrança 2 e posteriores estão em relação à data em que a carta de cobrança anterior é lançada ou impressa, dependendo da seleção no campo código da carta de Cobrança atualização da página Parâmetro de contas a receber.  
16. Clique em Adicionar para adicionar a última carta de cobrança na sequência.
    * Você poderá adicionar até cinco códigos de carta de cobrança para uma sequência de cartas de cobrança.  
17. No campo código da carta de cobrança, selecione o próximo código que será enviado na sequência.
18. No campo Descrição, digite um valor.
19. No campo Conta principal, especifique os valores desejados.
20. No campo Taxa em moeda, insira um número.
21. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
22. Na lista, clique no link na linha selecionada.
23. No campo Saldo vencido mínimo, insira um número.
24. No campo Dias, insira um número.
25. Marque a caixa de seleção para fazer com que o cliente pare de receber entregas e notas fiscais.
    * Para desbloquear a conta, selecione Não no campo Faturamento e entrega em espera na página Clientes.  
26. Expanda guia rápida Nota.
27. Digite o texto a ser exibido na carta de cobrança para o código de carta de cobrança selecionado.
    * Você pode traduzir esse texto nos vários idiomas usando o menu das traduções acima da caixa da nota.  

