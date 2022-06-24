---
title: Criar uma fatura de texto livre
description: Este artigo explica como criar faturas de texto livre.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 87dc6334baa83ace23b77d94da4d1e464cb0b574
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878150"
---
# <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

[!include [banner](../includes/banner.md)]

Este artigo explica como criar faturas de texto livre. Para o procedimento, use a empresa de demonstração **USMF**.

## <a name="create-a-free-text-invoice"></a>Criar uma fatura de texto livre

1. Acesse **Contas a receber (ou Razão de Vendas) \> Faturas \> Todas as faturas de texto livre**.
2. Selecione **Novo**.
3. No campo **Conta de cliente**, selecione um valor.

    * Por padrão, a conta selecionada como a conta do cliente é usada como a conta da fatura.
    * Se a fatura não for lançada, o status contábil inicia com **Em processo**.
    * O número da fatura será atribuído quando ela for lançada.
    * Se você estiver usando cartas de ordem de Área Única de Pagamentos em Euros (SEPA), a carta da ordem de débito direto será inserida automaticamente quando você selecionar a conta do cliente.

4. No campo **Descrição**, insira um valor.
5. No campo **Conta principal**, especifique um número de conta sem dimensões. As dimensões serão inseridas posteriormente neste artigo.

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
    * Você pode optar por interromper o lançamento da fatura de texto livre quando ocorrer um erro na guia **Atualizações** na página **Parâmetros de contas a receber** (**Contas a receber > Configuração > Parâmetros de contas a receber**). Selecione **Sim** para o parâmetro **Interromper o lançamento de faturas de texto livre no primeiro erro** para interromper o lançamento de faturas de texto livre quando ocorrer um erro. Se o lançamento for em lote, um erro interromperá o processo de lançamento e o status do lote será definido como **Erro**. Se esta opção não for selecionada, o processo de lançamento ignorará uma fatura com um erro de lançamento e continuará a lançar faturas adicionais. Se o lançamento for em lote, um erro de lançamento não impedirá que outras faturas sejam lançadas. O status do lote será **Terminado**. Um relatório detalhado do processo de lançamento estará disponível para revisão no histórico de trabalhos em lote.
    * Para imprimir a fatura, defina a opção como **Sim**.
    * Para lançar a fatura, defina a opção como **Sim**. Você pode imprimir a fatura sem lançá-la.

19. Selecione **OK**.

## <a name="copy-lines"></a>Copiar linhas
Para copiar linhas em uma fatura de texto livre, selecione uma ou mais linhas e depois selecione **Copiar linhas selecionadas**. Você pode especificar o número de cópias a serem feitas e também pode copiar observações e anexos. Você pode copiar as distribuições ou permitir que sejam recriadas quando fizer o lançamento.

Depois de copiar as linhas, você poderá editar as informações conforme necessário.

## <a name="create-a-free-text-invoice-from-a-template"></a>Criar uma fatura de texto livre a partir de um modelo
Você pode criar uma fatura de texto livre a partir de um modelo. Quando selecionar **Novo a partir do modelo** na guia **Fatura**, selecione um nome de modelo e a conta do cliente para nova fatura de texto livre. Os valores padrão, como as condições de pagamento e método de pagamento, podem ser preenchidos automaticamente ou você pode usar os valores que foram salvos no modelo.

Uma nova fatura de texto livre é criada e você pode editar os valores conforme necessário.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>Redefinindo o status do fluxo de trabalho de faturas de texto livre de Irrecuperável para Rascunho
Uma instância de fluxo de trabalho que foi interrompida por causa de um erro irrecuperável terá um status de fluxo de trabalho de **Irrecuperável**. Quando o status de um fluxo de trabalho de fatura de texto livre de cliente for **Irrecuperável**, você poderá redefini-lo como **Rascunho** selecionando **Cancelar** nas ações do fluxo de trabalho. Em seguida, você poderá editar a fatura de texto livre do cliente. Esse recurso estará disponível se o parâmetro **Redefinindo o status do fluxo de trabalho de faturas de texto livre de Irrecuperável para Rascunho** na página **Gerenciamento de recursos** estiver ativado.

Você pode usar a página **Histórico do fluxo de trabalho** para redefinir o status do fluxo de trabalho como **Rascunho**. Você pode abrir essa página em **Fatura de texto livre** ou em **Comum > Consultas > Fluxo de trabalho**. Para redefinir o status de fluxo de trabalho como **Rascunho**, selecione **Cancelar**. Você também pode redefinir o status do fluxo de trabalho como **Rascunho** selecionando a ação **Cancelar** na página **Fatura de texto livre** ou na página **Todas as faturas de texto livre**. Depois que o status do fluxo de trabalho for redefinido como **Rascunho**, ele fica disponível para edição na página **Fatura de texto livre**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
