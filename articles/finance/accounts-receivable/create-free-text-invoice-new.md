---
title: Criar uma fatura de texto livre
description: Este tópico explica como criar faturas de texto livre.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 726d4979059417871a00626c55da32fa4286cb53
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991108"
---
# <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

[!include [banner](../includes/banner.md)]

Este tópico explica como criar faturas de texto livre. Para o procedimento, use a empresa de demonstração **USMF**.

## <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

1. Acesse **Contas a receber (ou Razão de Vendas) \> Faturas \> Todas as faturas de texto livre**.
2. Selecione **Novo**.
3. No campo **Conta de cliente**, selecione um valor.

    * Por padrão, a conta selecionada como a conta do cliente é usada como a conta da fatura.
    * Se a fatura não for lançada, o status contábil inicia com **Em processo**.
    * O número da fatura será atribuído quando ela for lançada.
    * Se você estiver usando cartas de ordem de Área Única de Pagamentos em Euros (SEPA), a carta da ordem de débito direto será inserida automaticamente quando você selecionar a conta do cliente.

4. No campo **Descrição**, insira um valor.
5. No campo **Conta principal**, especifique um número de conta sem dimensões. As dimensões serão inseridas posteriormente neste tópico.

    Você também pode inserir um ou mais caracteres para a conta principal e usar a pesquisa para localizar a conta.

6. Selecione a Guia Rápida **Detalhes da linha** para adicionar dimensões à conta principal.
7. Selecione a guia **Linha de dimensões financeiras**.

    * As dimensões são somente para a linha selecionada.
    * O grupo de impostos é preenchido pelo cliente. Se o cliente não tiver um grupo de impostos, o grupo de impostos da conta principal será usado.
    * O grupo de impostos dos itens é preenchido pela conta principal. Se a conta principal não tiver um grupo de impostos dos itens, o grupo de impostos dos itens especificado nos parâmetros de impostos na Contabilidade será usado.

8. Opcional: no campo **Quantidade**, insira um número.
9. Opcional: no campo **Preço unitário**, insira um número.

    O valor é calculado como a quantidade vezes o preço unitário. No entanto, você pode substituir o cálculo inserindo um valor.

10. Selecione **Imposto** para ver os impostos calculados para a fatura.

    É possível exibir os valores dos impostos nesta página ou substitua os valores na guia **Ajuste**.

11. Selecione **OK**.
12. Selecione **Encargos** para adicionar um encargo à fatura.
13. No campo **Código de encargo**, insira um valor.
14. No campo **Valor de encargo**, insira um número.
15. Feche a página.
16. Selecione **Totais** para ver um resumo dos detalhes da fatura e os totais.
17. Selecione **Fechar**.
18. Selecione **Lançar** para lançar a fatura. Você ainda terá a oportunidade de cancelar antes de lançar.

    * Você pode alterar a hora da impressão da fatura. Selecione **Atual** para imprimir cada fatura, conforme for atualizada. Selecione **Depois** para imprimir depois todas as faturas que foram atualizadas.
    * Para alterar como o limite de crédito do cliente é verificado antes de a fatura ser lançada, altere o valor no campo **Tipo de limite de crédito**.
    * Para imprimir a fatura, defina a opção como **Sim**.
    * Para lançar a fatura, defina a opção como **Sim**. Você pode imprimir a fatura sem lançá-la.

19. Selecione **OK**.

## <a name="copy-lines"></a>Copiar linhas
Para copiar linhas em uma fatura de texto livre, selecione uma ou mais linhas e depois selecione **Copiar linhas selecionadas**. Você pode especificar o número de cópias a serem feitas e também pode copiar observações e anexos. Você pode copiar as distribuições ou permitir que sejam recriadas quando fizer o lançamento.

Depois de copiar as linhas, você poderá editar as informações conforme necessário.

## <a name="create-a-free-text-invoice-from-a-template"></a>Criar uma fatura de texto livre a partir de um modelo
Você pode criar uma fatura de texto livre a partir de um modelo. Quando selecionar **Novo a partir do modelo** na guia **Fatura**, selecione um nome de modelo e a conta do cliente para nova fatura de texto livre. Os valores padrão, como as condições de pagamento e método de pagamento, podem ser preenchidos automaticamente ou você pode usar os valores que foram salvos no modelo.

Uma nova fatura de texto livre é criada e você pode editar os valores conforme necessário.
