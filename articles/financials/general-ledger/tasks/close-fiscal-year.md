---
title: Fechar o ano fiscal
description: Este procedimento aborda o processo de fechamento do exercício que transfere saldos para um novo ano fiscal.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c12f0842f6e8edf3b51d12d0e008eb09acf8c374
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834917"
---
# <a name="close-the-fiscal-year"></a>Fechar o ano fiscal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento aborda o processo de fechamento do exercício que transfere saldos para um novo ano fiscal.


## <a name="validate-year-end-close-parameters"></a>Valide os parâmetros próximos de final de ano
1. Vá para **Painel de navegação > Módulos> Contabilidade > Configuração do razão > Parâmetros da contabilidade**.
2. Expandir a seção **Fechamento do ano fiscal**.
3. Selecione 'Sim' ou 'Não' para a opção **Excluir transações de fechamento de ano durante a transferência**.
    
    Se o ano fiscal tiver sido fechado e o fechamento de fim de ano estiver sendo executado novamente, essa configuração é importante. Se definido para Sim, o comprovante do fechamento anterior de final de ano será excluído, e um novo comprovante será criado para todas as contas que iniciam saldos. Se definido para Não, nenhum comprovante anterior permanecerá e um novo comprovante será criada apenas para as entradas de ajuste lançadas após o fechamento do final do ano.

4. Selecione 'Sim' ou 'Não' para a opção **Criar transações de fechamento durante a transferência**.

    Se definido como Sim, duas transações são criadas. Um comprovante é criado no ano fiscal que está sendo fechado para reduzir os saldos de contas contábeis de P&L a zero, e um segundo comprovante é criado no próximo ano fiscal para os saldos iniciais. Se definido para Não, um único comprovante é criado no próximo ano fiscal para o início dos saldos.  

5. Selecione 'Sim' ou 'Não' para a opção **Definir status de ano fiscal como permanentemente fechado**.

    Se estiver definido para Sim, o status do ano fiscal será definido como Permanentemente fechado.  Como um ano permanentemente fechado não pode ser reaberto, é uma prática recomendada definir esta opção como não.  

6. Selecione 'Sim' ou 'Não' para a opção **Número de comprovante deve ser preenchido durante o fechamento do exercício**.

    Se definido como Sim, um número de comprovante deverá ser inserido manualmente durante o processo de fechamento do ano. Uma sequência numérica não será usada para gerar esse número de comprovante. É uma melhor prática defini-lo para Sim.  

7. Feche a página.
8. Vá para **Contabilidade > Fechamento de período > Fechamento do exercício**.
9. Clique em **Novo** para criar um modelo de fechamento do exercício.

    Um modelo podem ser criados para um grupo de entidades legais em que executa o fechamento de fim de ano. Esse método pode ser reutilizado todos os anos.  

10. No campo **Nome do grupo**, insira um nome do modelo de fechamento do exercício.
11. No campo **Calendário fiscal**, selecione o ano fiscal para o qual o modelo será criado.

    Apenas as entidades legais que usam o mesmo ano fiscal podem ser agrupadas no modelo de fechamento de fim de ano. Isso porque o fechamento de anos é feito por um ano fiscal, sem uma data.  

12. No **Painel de ação**, clique em **Salvar**.
13. Na seção **Entidades legais**, clique em **Adicionar** para selecionar as entidades legais para este modelo.
    
    As entidades legais podem ser adicionadas às entidades legais ou selecionando uma hierarquia organizacional.  Apenas as entidades legais com a hierarquia organizacional com o mesmo calendário fiscal selecionado serão adicionadas.  

14. Selecione as entidades legais ou a hierarquia organizacional.
15. Clique em **OK**.
16. Selecione 'Sim' ou 'Não' em **Transferir dimensão de balanço**.

    É uma prática recomendada definir esta opção como Sim para Contas de balanço. Isso manterá abertas as dimensões financeiras em transações lançadas quando criar o saldo inicial para as contas de balanço. Para contas de lucros e perdas, pode optar por manter dimensões financeiras (Fechar tudo) quando os saldos serão movidos a ganhos retidos ou selecionar para que as dimensões financeiras substituir por um valor diferente de dimensão (Fechar único) Se você optar fechamento único, defina um valor de dimensão específico para cada dimensão ou mesmo escolha para deixá-la em branco.  

17. Clique em **Salvar**.
18. Inicie o fechamento do exercício escolhendo **Executar fechamento de ano fiscal** no **Painel de Ação**. O prazo final de ano será executado para o modelo selecionado.  
19. Selecione tudo ou um subgrupo de entidades legais do modelo em que executa o fechamento de fim de ano.

    Ao executar pela primeira vez o fechamento do exercício, para obter saldos iniciais, a maioria das organizações podem optar por executar o fechamento do exercício para todas as entidades legais no modelo. Se as entradas de ajuste são realizadas após isso, selecione executar o final do ano seguinte para apenas as entidades legais com ajustes.  

20. Clique em **OK**.
21. Selecione o ano fiscal para o qual executar o fechamento de fim de ano.
22. No **campo Comprovante**, digite um valor. É uma prática recomendada incluir o ano fiscal no número de comprovante para facilitar a localização do comprovante de fechamento do exercício que é criado.  
23. O fechamento do ano final padrão para executar o lote. É uma prática recomendada executar processos longos no modo de lote. Geralmente é um desses processos, por isso o padrão é usar o modo de lote.  
24. Clique em **OK**.

