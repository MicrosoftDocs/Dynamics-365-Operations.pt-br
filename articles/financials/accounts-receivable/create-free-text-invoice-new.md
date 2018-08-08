--- 
title: Criar uma fatura de texto livre
description: Este artigo demonstra como criar uma fatura de texto livre.
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: pt-br
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

[!include [banner](../includes/banner.md)]

Este artigo demonstra como criar uma fatura de texto livre. Para este procedimento, use a empresa de demonstração USMF.

## <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

1. Vá para Contas recebíveis > Faturas > Todas faturas de texto livre.
2. Clique em Novo.
3. No campo Conta de cliente, selecione um valor.
    * A conta de fatura usará como padrão a mesma conta usada para a conta do cliente.   
    * O status contábil inicia com Em processo se a fatura não for lançada.   
    * O número da fatura será atribuído quando ela for lançada.  
    * Se você estiver usando cartas de ordem de SEPA, a carta da ordem de débito direto será preenchida automaticamente com uma carta da ordem quando você selecionar a conta do cliente.  
4. No campo Descrição, digite um valor.
5. No campo de conta principal, especifique um número de conta sem dimensões.
    * Você também pode inserir um ou mais caracteres para a conta principal e usar a pesquisa para localizar a conta. Insira dimensões posteriormente neste guia.  
6. Expanda a guia rápida Detalhes da linha para poder adicionar dimensões à sua conta principal.
7. Clique na guia Linha de dimensões financeiras.
    * As dimensões são somente para a linha selecionada.    
    * O grupo de impostos sobre vendas é preenchido pelo cliente. Se o cliente não tiver um grupo de impostos sobre vendas, o grupo de impostos sobre vendas da conta principal será usado.  
    * O grupo de impostos dos itens é preenchido pela conta principal. Se a conta principal não tiver um grupo de impostos do item, será usado o grupo de impostos do item nos parâmetros de impostos da Contabilidade.    
8. No campo Quantidade, insira um número.
    * A quantidade é opcional.  
9. No campo Preço unitário, insira um número.
    * O preço unitário é opcional.  
    * O valor é calculado como a quantidade vezes o preço unitário. No entanto, você pode substituir o cálculo e inserir um valor.  
10. Clique em Imposto para ver os impostos calculados para sua fatura.
    * Exiba os valores dos impostos nesta página ou substitua os valores na guia Ajuste.  
11. Clique em OK.
12. Clique em Encargos para adicionar um encargo a sua fatura. 
13. No campo Código de encargo, digite um valor.
14. No campo Valor de encargo, insira um número.
15. Feche a página.
16. Clique em Totais para ver o resumo dos detalhes da fatura e os totais.
17. Clique em Fechar.
18. Clique em Lançar para lançar a fatura. É possível cancelar antes de lançar.
    * Para alterar o cronograma de impressão de faturas: selecione Atual para imprimir cada fatura conforme elas são atualizadas ou selecione Depois para imprimir depois de todas as faturas serem atualizadas.  
    * Se desejar alterar como o limite de crédito do cliente será verificado antes de lançar, altere o tipo de limite de crédito.  
    * Se desejar imprimir a fatura, selecione Sim.  
    * Se desejar lançar a fatura, selecione Sim. Você pode imprimir a nota fiscal sem lançá-las.  
19. Clique em OK.

## <a name="copy-lines"></a>Copiar linhas
Para copiar linhas na fatura de texto livre, selecione uma ou mais linhas e clique em Copiar linhas selecionadas. Você pode especificar o número de cópias que deseja fazer e também pode copiar observações e anexos. Você pode copiar as distribuições ou permitir que sejam recriadas quando fizer o lançamento. Depois de copiar as linhas, você poderá editar as informações conforme necessário. 

## <a name="create-a-free-text-invoice-from-a-template"></a>Criar uma fatura de texto livre a partir de um modelo
Você pode criar uma fatura de texto livre a partir de um modelo. Quando selecionar Novo a partir do modelo na guia Fatura, selecione um nome de modelo e a conta do cliente para nova fatura de texto livre. Você também pode escolher os valores padrão, como as condições de pagamento e método de pagamento do cliente, ou usar os valores que foram salvos com o modelo. Uma nova fatura de texto livre será criada e você poderá editar os valores nela. 


